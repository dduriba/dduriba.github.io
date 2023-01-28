---
title:  "스프라이트 정렬"
excerpt: "sprite sorting"
categories: unity2d
tag: [unity, 2d]
classes: wide
---

# 1.정렬 축을 Y로 변경
{: .notice--warning .text-center}

<img src="/img/unity2d/2023-01-26-sprite-sorting-project-settings.png"/>

- Edit-Project Settings-Graphics
  * Transparency Sort Mode : Custom Axis
  * Transparency Sort Axis : X = 0, Y = 1, Z = 0

<div class="notice">
게임 오브젝트의 Y 값이 높을수록 우선 렌더링
</div>

# 2.Sprite Renderer 컴포넌트 세부 설정
{: .notice--warning .text-center}

<img src="/img/unity2d/2023-01-26-sprite-renderer.png"/>

1. Additional Settings-Sorting Layer-Add Sorting Layer... 에서 Sorting Layer 를 추가
2. 
  * Sprite Sort Point : Pivot
  * Additional Settings-Sorting Layer : `1.` 에서 추가한 Sorting Layer 선택
  * Additional Settings-Order in Layer : 우선 렌더링 할 게임 오브젝트부터 1, 2, 3, ... 입력 (body : 1, hair : 2, ...)

<div class="notice">
Sprite Sort Point 를 Pivot 으로 뒀을 때 Sprite 의 Pivot 이 최하단으로 설정되어 있는지 확인
</div>

# 3.
{: .notice--warning .text-center}

<img src="/img/unity2d/2023-01-26-sorting-group.png"/>

# 4.
{: .notice--warning .text-center}

<img src="/img/unity2d/2023-01-26-other-sprite-objects.png"/>

[FROM THE TOP](#){: .btn .btn--info}