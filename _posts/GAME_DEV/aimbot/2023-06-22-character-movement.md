---
title:  "1.캐릭터 이동, 회전, 카메라"
excerpt: "character movement, rotation, camera"
categories: aimbot
tag: [unreal, aimbot]
classes: wide
---

# 1.프로젝트 세팅 인풋에 맵핑할 키 바인드
{: .notice--warning .text-center}

Project Settings >Engine-Input >Bindings >Axis Mappings

<img src="/img/unreal/aimbot/1_movement/axis_mappings.PNG"/>

# 2.플레이어 C++ 클래스 생성
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

# 3.플레이어 C++ 클래스 기반 BP 클래스 생성
{: .notice--warning .text-center}

<img src="/img/unreal/aimbot/1_movement/mesh.PNG"/>

0. 파라곤 레이스 캐릭터 애셋 임포트
1. 플레이어 BP 클래스의 mesh >skeletal mesh에 지정
2. 발끝을 캡슐콜라이더의 하단에 위치
3. 캐릭터의 정면이 front를 향하도록 회전

<img src="/img/unreal/aimbot/1_movement/camera.png"/>

0. SpringArm 컴포넌트 생성, 하위에 Camera 종속 생성
1. SpringArm Detials
	1. Camera Settings >Use Pawn Control Rotation = true
	2. Camera >Socket Offset 값 조절
	3. Transform 값 조절

# 4.게임모드베이스 클래스 기반 BP 클래스 생성
{: .notice--warning .text-center}

<img src="/img/unreal/aimbot/1_movement/gamemode.PNG"/>

C++ 폴더에 생성된 (ProjectName)GameModeBase 기반 BP 클래스 생성

Project Settings >Maps & Modes
1. Default GameMode에 만든 게임모드 BP 클래스 지정
2. Default Pawn Class에 만든 플레이어 BP 클래스 지정

Window >Place Actors >Player Start 를 월드에 생성

[FROM THE TOP](#){: .btn .btn--info}