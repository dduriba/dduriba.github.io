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

<details>
<summary>1) State {R Click} -> Make Transition -> (Up) Base Layer {L Click} -> States...</summary>
<div markdown="1">

<img src="/img/unity2d/stardewValley/2023-02-05-animator-make-transition-1.png"/>

<img src="/img/unity2d/stardewValley/2023-02-05-animator-make-transition-2.png"/>

- Idle 의 4개의 State 마다 Run, Walk 의 8개의 State 로의 Transition 을 추가
- Run, Walk 에선 같은 방향의 Idle State 로의 동일한 Transition 을 두 개씩 추가

</div>
</details>

<details>
<summary>2) Transition 설정</summary>
<div markdown="1">

<img src="/img/unity2d/stardewValley/2023-02-05-animator-transition-edit.png" style="zoom:50%;"/>

Has Exit Time : false
<br>Transition Duration in seconds : 0
<br> Conditions :
<table border="1">
    <tr align="center">
	    <th>from Idle</th>
	    <th>Up</th>
        <th>Down</th>
        <th>Right</th>
        <th>Left</th>
    </tr>
	<tr align="center">
	    <th>to Run</th>
	    <td>isRunning : true <br> yInput : Greater 0.01</td>
        <td>isRunning : true <br> yInput : Less -0.01</td>
        <td>isRunning : true <br> xInput : Greater 0.01</td>
        <td>isRunning : true <br> xInput : Less -0.01</td>
	</tr>
	<tr align="center">
	    <th>to Walk</th>
	    <td>isWalking : true <br> yInput : Greater 0.01</td>
        <td>isWalking : true <br> yInput : Less -0.01</td>
        <td>isWalking : true <br> xInput : Greater 0.01</td>
        <td>isWalking : true <br> xInput : Less -0.01</td>
	</tr>
</table>
    <table border="1">
	<th>to Idle</th>
	<th>Up</th>
    <th>Down</th>
    <th>Right</th>
    <th>Left</th>
	<tr>
	    <td>from Run</td>
	    <td>isRunning : false <br> yInput : Less 0.01</td>
        <td>isRunning : false <br> yInput : Greater -0.01</td>
        <td>isRunning : false <br> xInput : Less 0.01</td>
        <td>isRunning : false <br> xInput : Greater -0.01</td>
	</tr><!-- 첫번째 줄 끝 -->
	<tr><!-- 두번째 줄 시작 -->
	    <td>from Walk</td>
	    <td>isWalking : false <br> yInput : Less 0.01</td>
        <td>isWalking : false <br> yInput : Greater -0.01</td>
        <td>isWalking : false <br> xInput : Less 0.01</td>
        <td>isWalking : false <br> xInput : Greater -0.01</td>
	</tr><!-- 두번째 줄 끝 -->
</table>

</div>
</details>

# 3.
{: .notice--warning .text-center}