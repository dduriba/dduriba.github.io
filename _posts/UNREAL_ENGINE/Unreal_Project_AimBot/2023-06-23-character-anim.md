---
title:  "2.캐릭터 이동 애니메이션"
excerpt: "character movement animation"
categories: Unreal_Project_AimBot
tag: [Unreal, Project, AimBot]
classes: wide
---

# 1.Blend Space 생성
{: .notice--warning .text-center}

레이스 캐릭터의 스켈레톤으로 Blend Space 생성

<img src="/img/unreal/aimbot/2_anim/locomotion.png"/>

1. Asset Details >Axis Settings
    1. Horizontal Axis에 값 할당(Name, Min value, Max value)
    2. Vertical Axis에 값 할당(Name, Min value, Max value)
2. Blend Space에 애니메이션 할당

# 2.Animation BP 생성
{: .notice--warning .text-center}

레이스 캐릭터의 스켈레톤으로 Animation BP 생성

<img src="/img/unreal/aimbot/2_anim/abpAnimGraph.png"/>

1. 변수 생성
    1. float Angle
    2. float Speed
2. AnimGraph 편집
    1. 만들어놓은 BlendSpace Player를 호출
    2. 만들어놓은 변수를 BlendSpace Player에 연결
    3. anim out을 output pose에 연결

<img src="/img/unreal/aimbot/2_anim/abpEventGraph.png"/>

EventGraph 편집, 변수 Set

# 3.플레이어 BP 클래스에 Animation BP 연결
{: .notice--warning .text-center}

mesh >Animation >Anim Class

<img src="/img/unreal/aimbot/2_anim/animClass.png"/>