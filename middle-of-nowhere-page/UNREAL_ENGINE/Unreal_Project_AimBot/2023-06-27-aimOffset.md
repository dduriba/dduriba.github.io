---
title:  "6.에임 오프셋"
excerpt: "aim offset"
categories: Unreal_Project_AimBot
tag: [Unreal, Project, AimBot]
classes: wide
---

# 1.Animation BP 편집
{: .notice--warning .text-center}

Pitch값을 담을 변수를 만들어주고 애님 그래프에서 AimOffset Player함수를 호출해 다음과 같이 연결

<img src="/img/unreal/aimbot/6_aimOffset/AnimGraph.png"/>

AimOffset이 없을 경우 적절한 애니메이션이 있다면 직접 만들어준다

<img src="/img/unreal/aimbot/6_aimOffset/aimOffset.png"/>

기존 이벤트 그래프의 Try Get Pawn Owner를 제외한 나머지 액션들을 함수로 합쳐준다

<img src="/img/unreal/aimbot/6_aimOffset/EventGraphLocomotion.png"/>

sequence를 사용해 첫번째 실행핀에는 기존 액션들의 함수를 연결, Aim Pitch값을 받아올 함수는 두번째 실행핀에 연결해준다

<img src="/img/unreal/aimbot/6_aimOffset/EventGraph.png"/>

<img src="/img/unreal/aimbot/6_aimOffset/EventGraphAimPitch.png"/>