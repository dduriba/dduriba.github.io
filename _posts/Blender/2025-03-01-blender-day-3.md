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

<span class="block-lightgreen">Levels Viewport</span>의 값을 조절해 나눌 정도를 조절할 수 있습니다.

## Mirror Modifier
{: .notice--success}

📢 오브젝트를 특정 축 기준으로 대칭 복사해주는 기능입니다. Origin이 그 중심이 됩니다.

<span class="block-lightgreen">Clipping</span> 대칭되는 중심에서 Vertex가 겹쳐 붙습니다. 중앙선이 찢어지는 걸 방지할 수 있습니다.

<span class="block-lightgreen">Merge</span> 대칭 복사된 Vertex가 일정 거리(Merge Distance) 이내에 있을 경우 자동 병합됩니다.

📝 <span class="block-lightgreen">Clipping, Merge</span> 기능을 동시에 적절히 사용해 미러 모디파이어를 사용하면서 모델을 늘리고 싶을 때 중앙선이 찢어지지 않게 자연스럽게 적용할 수 있습니다.

# Dissolve
{: .notice--warning}

📢 주변 메시를 최대한 유지하면서 선택한 메시를 삭제(용해)합니다. Delete와는 다르게 모델링을 유지하면서 지오메트리를 정리할 때 유용합니다.

<span class="block-darkgrey">Edit Mode</span> ➡️ <span class="block-darkgrey">Mesh</span> 👆 ➡️ <span class="block-darkgrey">X</span> ➡️ <span class="block-darkgrey">Dissolve Vertices, Edges, Faces</span>