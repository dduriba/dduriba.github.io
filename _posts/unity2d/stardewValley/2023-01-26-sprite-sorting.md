---
title:  "2.스프라이트 정렬"
excerpt: "sprite sorting"
categories: stardewValley
tag: [unity, 2d, stardewValley]
classes: wide
---

# 1.정렬 축을 Y로 변경
{: .notice--warning .text-center}

<img src="/img/unity2d/stardewValley/2023-01-26-sprite-sorting-project-settings.png"/>

- Edit-Project Settings-Graphics
  * Transparency Sort Mode : Custom Axis
  * Transparency Sort Axis : X = 0, Y = 1, Z = 0

<div class="notice">
게임 오브젝트의 Y 값이 높을수록 우선 렌더링
</div>

# 2.Sprite Renderer 컴포넌트 추가 및 설정
{: .notice--warning .text-center}

<img src="/img/unity2d/stardewValley/2023-01-26-sprite-renderer.png"/>

1. Additional Settings-Sorting Layer-Add Sorting Layer... 에서 Sorting Layer 를 추가
2. 
  * Sprite Sort Point : Pivot
  * Additional Settings-Sorting Layer : `1.` 에서 추가한 Sorting Layer 선택
  * Additional Settings-Order in Layer : 우선 렌더링 할 게임오브젝트부터 1, 2, 3, ... 입력 (body : 1, hair : 2, ...)

<div class="notice">
Sprite Sort Point 를 Pivot 으로 뒀을 때 Sprite 의 Pivot 이 최하단으로 설정되어 있는지 확인
</div>

# 3.Sorting Group 컴포넌트 추가 및 설정
{: .notice--warning .text-center}

<img src="/img/unity2d/stardewValley/2023-01-26-sorting-group.png"/>

* Sorting Layer : [2-1.](#2sprite-renderer-컴포넌트-설정) 에서 추가한 Sorting Layer 선택
* Order in Layer : 0

<div class="notice">
Sprite Renderer 컴포넌트를 가진 게임오브젝트들을 Sorting Group 컴포넌트를 가진 게임오브젝트의 하위 게임오브젝트로 구성
<br>(그룹화하면 Sprite Renderer 를 가진 하위 게임오브젝트들끼리의 스프라이트 정렬은 Sprite Renderer 의 Order in Layer 값에 따라 결정되고 다른 게임오브젝트들과의 스프라이트 정렬은 Sotring Group 의 Order in Layer 값에 따라 결정돼 하나의 스프라이트 처럼 동작)
</div>

# 4.다른 게임오브젝트들에 적용
{: .notice--warning .text-center}

<img src="/img/unity2d/stardewValley/2023-01-26-other-sprite-objects.png"/>

* Sprite Sort Point : Pivot
* Sorting Layer : [2-1.](#2sprite-renderer-컴포넌트-설정) 에서 추가한 Sorting Layer 선택
* Order in Layer : 0

<div class="notice">
게임오브젝트가 하나의 Sprite Renderer 만 가질 경우 Sorting Group 없이 위의 값 세개로 설정
</div>

[FROM THE TOP](#){: .btn .btn--info}