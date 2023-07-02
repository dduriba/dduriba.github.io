---
title:  "4.라인 트레이스, 이미터"
excerpt: "line trace, emitter"
categories: aimbot
tag: [unreal, aimbot]
classes: wide
---

# 0.프로젝트 세팅 콜리전 채널 편집
{: .notice--warning .text-center}

Trace Channel을 Name=Bullet, Default Response=Block으로 하나 만들어주고 Preset에서 Bullet을 편집:<br>
NoCollision=Ignore<br>
BlockAll=block<br>
OverlapAll=Overlap<br>
InvisibleWall=Ignore<br>
InvisibleWallDynamic=Ignore

<img src="/img/unreal/aimbot/4_lineTrace/collisionChannel.png"/>

<details>
<summary>DefaultEngine.ini 에서 콜리전 채널 넘버 확인(ECC_GameTraceChannel)</summary>
<div markdown="1">

```ini
+DefaultChannelResponses=(Channel=ECC_GameTraceChannel1,DefaultResponse=ECR_Block,bTraceType=True,bStaticObject=False,Name="Bullet")
```

</div>
</details>

# 1.프로젝트 세팅 인풋에 맵핑할 키 바인드
{: .notice--warning .text-center}

<img src="/img/unreal/aimbot/4_lineTrace/bind.png"/>

# 2.머즐 소켓 확인
{: .notice--warning .text-center}

총 스켈레톤 트리의 Muzzle 본 네임 확인, 없는 경우 소켓을 생성해 총구에 위치시켜준다

<img src="/img/unreal/aimbot/4_lineTrace/muzzleSocket.png"/>

# 3.총 C++ 클래스 코드 추가
{: .notice--warning .text-center}

<details>
<summary>Rifle.h</summary>
<div markdown="1">

```cpp
public:	
	void PullTrigger();

private:
	UPROPERTY(EditAnywhere)
	UParticleSystem* ImpactEffect;

	UPROPERTY(EditAnywhere)
	UParticleSystem* MuzzleEffect;

	UPROPERTY(EditAnywhere)
	float MaxRange = 10000;

	bool LineTrace(FHitResult& Hit, FVector& ShotDirection);

	AController* GetOwnerController() const;
```
</div>
</details>

<details>
<summary>Rifle.cpp</summary>
<div markdown="1">

```cpp
#include "Kismet/GameplayStatics.h"

void ARifle::PullTrigger()
{
	UGameplayStatics::SpawnEmitterAttached(MuzzleEffect, Mesh, TEXT("Muzzle"));

	FHitResult Hit;
	FVector ShotDirection;
	bool bSuccess = LineTrace(Hit, ShotDirection);
	if (bSuccess)
	{
		UGameplayStatics::SpawnEmitterAtLocation(GetWorld(), ImpactEffect, Hit.Location, ShotDirection.Rotation());
	}
}

bool ARifle::LineTrace(FHitResult& Hit, FVector& ShotDirection)
{
	AController* OwnerController = GetOwnerController();
	if (OwnerController == nullptr) return false;

	FVector Location;
	FRotator Rotation;
	OwnerController->GetPlayerViewPoint(Location, Rotation);
	ShotDirection = -Rotation.Vector();

	FVector End = Location + Rotation.Vector() * MaxRange;
	FCollisionQueryParams Params;
	Params.AddIgnoredActor(this);
	Params.AddIgnoredActor(GetOwner());
	return GetWorld()->LineTraceSingleByChannel(Hit, Location, End, ECollisionChannel::ECC_GameTraceChannel1, Params);
}

AController* ARifle::GetOwnerController() const
{
	APawn* OwnerPawn = Cast<APawn>(GetOwner());
	if (OwnerPawn == nullptr) return nullptr;
	return OwnerPawn->GetController();
}
```

</div>
</details>

# 4.플레이어 C++ 코드 추가
{: .notice--warning .text-center}

<details>
<summary>AimBotPlayer.h</summary>
<div markdown="1">

```cpp
public:	
	void Shoot();
```

</div>
</details>

<details>
<summary>AimBotPlayer.cpp</summary>
<div markdown="1">

```cpp
void AAimBotPlayer::SetupPlayerInputComponent(UInputComponent* PlayerInputComponent)
{
	Super::SetupPlayerInputComponent(PlayerInputComponent);

	PlayerInputComponent->BindAction(TEXT("Shoot"), EInputEvent::IE_Pressed, this, &AAimBotPlayer::Shoot);
}

void AAimBotPlayer::Shoot()
{
	Rifle->PullTrigger();
}
```

</div>
</details>

# 5.총 BP 클래스에 이미터 연결
{: .notice--warning .text-center}

<img src="/img/unreal/aimbot/4_lineTrace/emitter.png"/>