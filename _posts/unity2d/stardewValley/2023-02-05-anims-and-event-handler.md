---
title:  "4.애니메이션/애니메이터와 이벤트 핸들러"
excerpt: "animation, animator and event handler"
categories: stardewValley
tag: [unity, 2d, stardewValley]
classes: wide
---

# 1.Animation (Clip), Animator Controller 생성
{: .notice--warning .text-center}

<img src="/img/unity2d/stardewValley/2023-02-05-create-clips-and-controller.png" style="zoom:50%;"/>

# 2.Animator Contoller 설정 (Animator window)
{: .notice--warning .text-center}

## 2-1 Parameter 추가
{: .notice--success}

<img src="/img/unity2d/stardewValley/2023-02-05-animator-parameters.png" style="zoom:50%;"/>

## 2-2 State 추가 및 설정
{: .notice--success}

<details>
<summary>1) Create Sub-State Machine -> Idle, Run, Walk</summary>
<div markdown="1">

<img src="/img/unity2d/stardewValley/2023-02-05-animator-sub-state-machine.png"/>

</div>
</details>

<details>
<summary>2) Create State -> Empty -> IdleUp, IdleDown, IdleLeft, IdleRight, RunUp...</summary>
<div markdown="1">

<img src="/img/unity2d/stardewValley/2023-02-05-animator-state.png"/>

</div>
</details>

<details>
<summary>3) 각 State에 맞는 Animation Clip(Motion) 연결</summary>
<div markdown="1">

<img src="/img/unity2d/stardewValley/2023-02-05-animator-state-motion.png" style="zoom:50%;"/>

</div>
</details>

## 2-3 Transition 추가 및 설정
{: .notice--success}