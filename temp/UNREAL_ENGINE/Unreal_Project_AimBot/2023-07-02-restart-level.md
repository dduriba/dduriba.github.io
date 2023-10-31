---
title:  "12.RestartLevel"
excerpt: "RestartLevel"
categories: Unreal_Project_AimBot
tag: [Unreal, Project, AimBot]
classes: wide
---

# 1.C++ 클래스 편집
{: .notice--warning .text-center}

<details>
<summary>AimBotGameModeBase.h</summary>
<div markdown="1">

```cpp
#pragma once

#include "CoreMinimal.h"
#include "GameFramework/GameModeBase.h"
#include "AimBotGameModeBase.generated.h"

UCLASS()
class AIMBOT_API AAimBotGameModeBase : public AGameModeBase
{
	GENERATED_BODY()
	
public:
	void PawnKilled(APawn* PawnKilled);
	
private:
	void EndGame(bool bIsPlayerWinner);
};
```

</div>
</details>

<details>
<summary>AimBotGameModeBase.cpp</summary>
<div markdown="1">

```cpp
#include "AimBotGameModeBase.h"
#include "EngineUtils.h"
#include "GameFramework/Controller.h"
#include "AimBotAIController.h"

void AAimBotGameModeBase::PawnKilled(APawn* PawnKilled)
{
    APlayerController* PlayerController = Cast<APlayerController>(PawnKilled->GetController());
    if (PlayerController != nullptr)
    {
        EndGame(false);
    }

    for (AAimBotAIController* Controller : TActorRange<AAimBotAIController>(GetWorld()))
    {
        if (!Controller->IsDead()) return;
    }
    
    EndGame(true);
}

void AAimBotGameModeBase::EndGame(bool bIsPlayerWinner)
{
    for (AController* Controller : TActorRange<AController>(GetWorld()))
    {
        bool bIsWinner = Controller->IsPlayerController() == bIsPlayerWinner;
        Controller->GameHasEnded(Controller->GetPawn(), bIsWinner);
    }
}
```

</div>
</details>

<details>
<summary>AimBotPlayer.cpp</summary>
<div markdown="1">

```cpp
#include "AimBotGameModeBase.h"

float AAimBotPlayer::TakeDamage(float DamageAmount, struct FDamageEvent const& DamageEvent, class AController* EventInstigator, AActor* DamageCauser)
{
	float DamageToApply = Super::TakeDamage(DamageAmount, DamageEvent, EventInstigator, DamageCauser);
	DamageToApply = FMath::Min(Health, DamageToApply);
	Health -= DamageToApply;

	if (IsDead())
	{
		AAimBotGameModeBase* GameMode = GetWorld()->GetAuthGameMode<AAimBotGameModeBase>();
		if (GameMode != nullptr)
		{
			GameMode->PawnKilled(this);
		}
		
		DetachFromControllerPendingDestroy();
		GetCapsuleComponent()->SetCollisionEnabled(ECollisionEnabled::NoCollision);
	}

	return DamageToApply;
}
```

</div>
</details>

<details>
<summary>AimBotPlayerController.h</summary>
<div markdown="1">

```cpp
public:
	virtual void GameHasEnded(class AActor* EndGameFocus = nullptr, bool bIsWinner = false) override;

protected:
	virtual void BeginPlay() override;

private:
	UPROPERTY(EditAnywhere)
	TSubclassOf<class UUserWidget> WinScreenClass;
	UPROPERTY(EditAnywhere)
	TSubclassOf<class UUserWidget> LoseScreenClass;

	UPROPERTY(EditAnywhere)
	float RestartDelay = 5;

	FTimerHandle RestartTimer;
```

</div>
</details>

<details>
<summary>AimBotPlayerController.cpp</summary>
<div markdown="1">

```cpp
#include "TimerManager.h"

void AAimBotPlayerController::GameHasEnded(class AActor* EndGameFocus, bool bIsWinner)
{
    Super::GameHasEnded(EndGameFocus, bIsWinner);

    HUD->RemoveFromViewport();

    if (bIsWinner)
    {
        UUserWidget* WinScreen = CreateWidget(this, WinScreenClass);
        if (WinScreen != nullptr)
        {
            WinScreen->AddToViewport();
        }
    }
    else
    {
        UUserWidget* LoseScreen = CreateWidget(this, LoseScreenClass);
        if (LoseScreen != nullptr)
        {
            LoseScreen->AddToViewport();
        }
    }

    GetWorldTimerManager().SetTimer(RestartTimer, this, &APlayerController::RestartLevel, RestartDelay);
}
```

</div>
</details>

# 2.PlayerController BP 클래스에 Widget BP 연결
{: .notice--warning .text-center}

Widget BP로 Win Screen과 Lose Screen을 만들어 연결

<img src="/img/unreal/aimbot/12_restartLevel/connectWBP.png"/>