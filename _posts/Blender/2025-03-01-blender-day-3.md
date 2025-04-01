---
title: "블렌더 3일차"
categories: Blender
excerpt: "모디파이어 프로퍼티"
---

<span style="color:gray">blender version 3.0.0</span>

# Modifier Properties
{: .notice--warning}

📢 블렌더 오른쪽 프로퍼티 에디터 창에서 <span class="block-lightgreen">스패너 아이콘</span>을 통해 사용할 수 있습니다. <span class="block-lightgreen">Add Modifier</span>를 선택해 모디파이어를 추가합니다.

해당 프로퍼티의 장점으로는

1️⃣ <span class="block-lightgreen">비파괴적(Non-destructive) 모델링</span> 원본 지오메트리를 직접 수정하지 않고 유연한 작업이 가능합니다.

2️⃣ <span class="block-lightgreen">Stacking</span> 하나의 오브젝트에 여러 개의 모디파이어를 쌓아서 사용할 수 있습니다. 상단에 있는 모디파이어부터 우선 적용됩니다.

📝 모디파이어 프로퍼티 창을 선택하고 <span class="block-darkgrey">Ctrl</span> ➕ <span class="block-darkgrey">A</span>를 통해 오브젝트에 <span class="block-lightgreen">Apply</span> 할 수 있습니다. Edit Mode에선 적용이 안되며 <span class="block-lightgreen">Object Mode</span>에서 적용할 수 있습니다.

📝 모디파이어 프로퍼티 창에서 Edit Mode, Realtime 등의 토글 아이콘을 통해 뷰포트에서 미리 오브젝트에 적용되어 보여지는 상태를 제어할 수 있습니다.

## Subdivision Surface Modifier
{: .notice--success}

📢 표면을 나누어 부드럽게 다듬는 기능입니다.

<span class="block-lightgreen">Levels Viewport</span> 값을 조절해 표면을 나눌 정도를 조절합니다.

## Mirror Modifier
{: .notice--success}

📢 오브젝트를 특정 축 기준으로 대칭 복사해주는 기능입니다. Origin이 그 중심이 됩니다. 대칭인 모델을 작업할 때 유용합니다.

<span class="block-lightgreen">Clipping</span> 대칭되는 중심에서 Vertex가 겹쳐 붙습니다. 중앙선이 찢어지는 걸 방지할 수 있습니다.

<span class="block-lightgreen">Merge</span> 대칭 복사된 Vertex가 일정 거리(Merge Distance) 이내에 있을 경우 자동 병합됩니다.

📝 <span class="block-lightgreen">Clipping, Merge</span> 기능을 동시에 적절히 사용해 미러 모디파이어를 사용하면서 모델을 늘리고 싶을 때 중앙선이 찢어지지 않게 자연스럽게 적용할 수 있습니다.

<img src="/img/Blender/Mirror.png"/>

🔍 Mirror Modifier를 사용해 기둥을 만드는 예시, 내부 기둥을 만드는 방법으로

1️⃣ <span class="block-lightgreen">Inset을 사용한 방법</span> <span class="block-darkgrey">I(Inset)</span> ➡️ <span class="block-darkgrey">I(Individual) = Off</span> ➡️ <span class="block-darkgrey">B(Boundary) = Off</span> ➡️ 🖱️

2️⃣ <span class="block-lightgreen">Extrude를 사용한 방법</span> 3D 커서를 World Origin에 두고 ➡️ Transform Pivot Point를 3D 커서로 설정 ➡️ <span class="block-darkgrey">E(Extrude)</span> ➡️ <span class="block-darkgrey">S(Scale)</span> ➡️ <span class="block-darkgrey">Shift</span> ➕ <span class="block-darkgrey">Z</span>로 <span class="block-lightgreen">Z축을 제외한 스케일 조절</span> ➡️ 🖱️

## Boolean Modifier
{: .notice--success}

📢 다른 오브젝트(B)가 현재 오브젝트(A)에 영향을 주어 모델링을 합치거나 겹치는 부분만 남기거나 절단하는 기능입니다. 현재 오브젝트(A)의 불린 모디파이어 프로퍼티의 Ojbect 속성에 다른 오브젝트(B)를 지정해 사용합니다.

<span class="block-lightgreen">Intersect</span> 두 오브젝트가 겹치는 부분만 남깁니다.

<span class="block-lightgreen">Union</span> 두 오브젝트가 겹치는 부분을 없애고 하나의 오브젝트로 만듭니다.

<span class="block-lightgreen">Difference</span> 현재 오브젝트에서 대상이 된 오브젝트와 겹치는 부분을 잘라냅니다.

## Array Modifier
{: .notice--success}

📢 오브젝트를 여러 개 복사해 일정한 패턴으로 배열하는 기능입니다.

- [X] <span class="block-lightgreen">Fit Type</span> 배열 개수를 설정합니다.

  + [ ] <span class="block-lightgreen">Fixed Count</span> 고정된 수만큼 복사합니다.

  + [ ] <span class="block-lightgreen">Fit Length</span> 지정한 길이 내에서 최대한 복사합니다.

- [X] <span class="block-lightgreen">Relative Offset</span> 오브젝트 크기(Scale)를 기준으로 배열 간격을 조절합니다.

- [X] <span class="block-lightgreen">Constant Offset</span> 고정된 간격으로 배열 간격을 조절합니다.

- [X] <span class="block-lightgreen">Object Offset</span> 특정 오브젝트를 기준으로 배열 간격을 조절합니다.

📝 Offset은 동시에 여러 개 설정할 수 있습니다.

<img src="/img/Blender/ObjectOffset.png"/>

🔍 링 형태 배열을 만드는 예시입니다. <span class="block-darkgrey">Shift</span> ➕ <span class="block-darkgrey">C</span>를 사용해 <span class="block-lightgreen">World Origin에 3D Cursor</span>를 두고 <span class="block-darkgrey">Shift</span> ➕ <span class="block-darkgrey">A</span> ➡️ <span class="block-darkgrey">Empty</span> ➡️ <span class="block-darkgrey">Plane Axes</span>로 생성된 대상이 될 오브젝트를 Array Modifier가 적용된 기준 오브젝트의 <span class="block-lightgreen">Object Offset</span>에 설정합니다. 기준 오브젝트를 <span class="block-lightgreen">World Origin</span>으로부터 거리를 둔 채 <span class="block-darkgrey">Ctrl</span> ➕ <span class="block-darkgrey">A</span> ➡️ <span class="block-darkgrey">Location</span>을 통해 모델의 위치는 유지하며 오브젝트의 위치 값을 <span class="block-lightgreen">World Origin</span>으로 초기화 시킵니다. 끝으로 대상이 된 Empty(Plane Axes) 오브젝트를 회전 시킵니다.

# Dissolve
{: .notice--warning}

📢 주변 메시를 최대한 유지하면서 선택한 메시를 삭제(용해)합니다. Delete와는 다르게 모델링을 유지하면서 지오메트리를 정리할 때 유용합니다.

<span class="block-darkgrey">Edit Mode</span> ➡️ <span class="block-darkgrey">Mesh</span> 👆 ➡️ <span class="block-darkgrey">X</span> ➡️ <span class="block-darkgrey">Dissolve Vertices, Edges, Faces</span>