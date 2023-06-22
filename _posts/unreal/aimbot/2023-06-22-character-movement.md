---
title:  "1.캐릭터 무브먼트"
excerpt: "character movement"
categories: aimbot
tag: [unreal, aimbot]
classes: wide
---

# 1.프로젝트 세팅 인풋에 바인드
{: .notice--warning .text-center}

Project Settings >Engine >Input >Bindings >Axis Mappings

<img src="/img/unreal/aimbot/1_movement/axis_mappings.PNG"/>

# 2.캐릭터 C++ 클래스 생성
{: .notice--warning .text-center}

parent class: character

<details>
<summary>AimBotPlayer.h</summary>
<div markdown="1">

```cpp
#pragma once

#include "CoreMinimal.h"
#include "GameFramework/Character.h"
#include "AimBotPlayer.generated.h"

UCLASS()
class AIMBOT_API AAimBotPlayer : public ACharacter
{
	GENERATED_BODY()

public:
	AAimBotPlayer();

protected:
	virtual void BeginPlay() override;

public:	
	virtual void Tick(float DeltaTime) override;

	virtual void SetupPlayerInputComponent(class UInputComponent* PlayerInputComponent) override;

private:
	void MoveForward(float AxisValue);
	void MoveRight(float AxisValue);
};
```

</div>
</details>

<details>
<summary>AimBotPlayer.cpp</summary>
<div markdown="1">

```cpp
#include "AimBotPlayer.h"

AAimBotPlayer::AAimBotPlayer()
{
	PrimaryActorTick.bCanEverTick = true;
}

void AAimBotPlayer::BeginPlay()
{
	Super::BeginPlay();
}

void AAimBotPlayer::Tick(float DeltaTime)
{
	Super::Tick(DeltaTime);
}

void AAimBotPlayer::SetupPlayerInputComponent(UInputComponent* PlayerInputComponent)
{
	Super::SetupPlayerInputComponent(PlayerInputComponent);

	PlayerInputComponent->BindAxis(TEXT("MoveForward"), this, &AAimBotPlayer::MoveForward);
	PlayerInputComponent->BindAxis(TEXT("MoveRight"), this, &AAimBotPlayer::MoveRight);
	PlayerInputComponent->BindAxis(TEXT("LookUp"), this, &APawn::AddControllerPitchInput);
	PlayerInputComponent->BindAxis(TEXT("LookRight"), this, &APawn::AddControllerYawInput);
}

void AAimBotPlayer::MoveForward(float AxisValue)
{
	AddMovementInput(GetActorForwardVector() * AxisValue);
}

void AAimBotPlayer::MoveRight(float AxisValue)
{
	AddMovementInput(GetActorRightVector() * AxisValue);
}
```

</div>
</details>

# 3.캐릭터 C++ 클래스 기반 BP 클래스 생성
{: .notice--warning .text-center}

<img src="/img/unreal/aimbot/1_movement/mesh.PNG"/>

파라곤 레이스 캐릭터 어셋을 받아 캐릭터 블루프린트 클래스의 mesh >skeletal mesh에 지정, 발끝을 캡슐콜라이더의 하단에 위치시키고 캐릭터의 앞이 front를 보게 회전

# 4.게임모드베이스 클래스 기반 BP 클래스 생성
{: .notice--warning .text-center}

Project Settings >Maps & Modes
Default GameMode 에 만든 게임모드 BP 클래스 지정
Default Pawn Class 에 만든 캐릭터 BP 클래스 지정

Window >Place Actors >Player Start 를 월드에 생성

[FROM THE TOP](#){: .btn .btn--info}