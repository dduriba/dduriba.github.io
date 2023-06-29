---
title:  "8.HUD 조준점"
excerpt: "HUD crosshair"
categories: aimbot
tag: [unreal, aimbot]
classes: wide
---

# 1.플레이어 컨트롤러 C++ 클래스 생성
{: .notice--warning .text-center}

parent class: playerController

<details>
<summary>AimBotPlayerController.h</summary>
<div markdown="1">

```cpp
#pragma once

#include "CoreMinimal.h"
#include "GameFramework/PlayerController.h"
#include "AimBotPlayerController.generated.h"

UCLASS()
class AIMBOT_API AAimBotPlayerController : public APlayerController
{
	GENERATED_BODY()

protected:
	virtual void BeginPlay() override;

private:
	UPROPERTY(EditAnywhere)
	TSubclassOf<class UUserWidget> HUDClass;

	UPROPERTY()
	UUserWidget* HUD;
};
```

</div>
</details>

<details>
<summary>AimBotPlayerController.cpp</summary>
<div markdown="1">

```cpp
#include "AimBotPlayerController.h"
#include "Blueprint/UserWidget.h"

void AAimBotPlayerController::BeginPlay()
{
    Super::BeginPlay();

    HUD = CreateWidget(this, HUDClass);
    if (HUD != nullptr)
    {
        HUD->AddToViewport();
    }
}
```

</div>
</details>

<details>
<summary>AimBot.Build.cs (퍼블릭 모듈 종속성에 "UMG" 추가)</summary>
<div markdown="1">

```cs
using UnrealBuildTool;

public class AimBot : ModuleRules
{
	public AimBot(ReadOnlyTargetRules Target) : base(Target)
	{
		PCHUsage = PCHUsageMode.UseExplicitOrSharedPCHs;
	
		PublicDependencyModuleNames.AddRange(new string[] { "Core", "CoreUObject", "Engine", "InputCore", "UMG" });

		PrivateDependencyModuleNames.AddRange(new string[] {  });
	}
}
```

</div>
</details>

# 2.Widget BP(User Widget) 생성
{: .notice--warning .text-center}

Canvas Panel이 없으면 생성 후 하위에 Image를 생성, Anchors를 중앙에 맞춰주고 Size To Content = true, 적절한 이미지를 찾아 넣어주고 이미지 사이즈 조절을 해준다

<img src="/img/unreal/aimbot/8_crosshair/wbp.png"/>

# 3.플레이어 컨트롤러 C++ 기반 BP 클래스 생성
{: .notice--warning .text-center}

만든 Widget BP를 연결

<img src="/img/unreal/aimbot/8_crosshair/controllerBP.png"/>

# 4.프로젝트 세팅(GameModeBase)에서 Player Controller Class 지정
{: .notice--warning .text-center}

<img src="/img/unreal/aimbot/8_crosshair/projectSettings.png"/>