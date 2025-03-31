---
title: "블렌더 2일차"
categories: Blender
excerpt: "에딧 모드에서의 간단한 메시 편집 배우기"
---

<span style="color:gray">blender version 3.0.0</span>

# Transform Pivot Point
{: .notice--warning}

📢 뷰포트 상단 중앙의 두 번째 아이콘에 위치해있습니다.

<span class="block-lightgreen">Bounding Box Center</span> 선택된 오브젝트의 외곽을 감싸는 최소한의 박스의 중심이 Pivot이 됨

<span class="block-lightgreen">3D Cursor</span> 현재 3D Cursor가 Pivot이 됨

<span class="block-lightgreen">Individual Origins</span> Origin이 Pivot이 됨, 여러 오브젝트를 선택할 때 각각의 오브젝트가 자기 자신의 Origin을 Pivot으로 가짐

<span class="block-lightgreen">Median Point</span> 여러 오브젝트를 선택할 때 오브젝트들의 Origin의 중앙점이 Pivot이 됨

<span class="block-lightgreen">Active Element</span> 여러 오브젝트를 선택할 때 Active(마지막으로 선택된) 오브젝트의 Origin이 Pivot이 됨 

# Local View Mode
{: .notice--warning}

📢 선택한 개체만 볼 수 있게 해주는 모드입니다.

<span class="block-darkgrey">Object</span> 👆 ➡️ <span class="block-darkgrey">/</span>

# R-epeat Last
{: .notice--warning}

📢 마지막으로 사용한 작업을 반복합니다.

<span class="block-darkgrey">Shift</span> ➕ <span class="block-darkgrey">R</span>

# Edit Mode
{: .notice--warning}

<span class="block-darkgrey">Object</span> 👆 ➡️ <span class="block-darkgrey">Tab</span>

🚨 <span class="block-lightgreen">Edit Mode</span>에서 생성한 오브젝트(개체, 메시)는 <span class="block-lightgreen">Edit Mode</span>로 진입할 때 선택한 오브젝트의 메시로 취급되어 개체를 생성할 때는 <span class="block-lightgreen">Object Mode</span>인지 확인해야 합니다. <span class="block-lightgreen">Edit Mode</span>에서 메시를 오브젝트로 분리해야 할 상황이 온다면 분리할 <span class="block-darkgrey">Mesh</span> 👆 ➡️ <span class="block-darkgrey">P(Separate)</span> ➡️ <span class="block-darkgrey">Selection</span> 선택을 통해 별개의 오브젝트로 분리할 수 있습니다.

📝 Edit Mode에서 A(Select All)를 누르면 해당 오브젝트의 모든 Mesh를 선택합니다.

# Origin 설정(Pivot 잡기)
{: .notice--warning}

<span class="block-darkgrey">Edit Mode</span> ➡️ <span class="block-darkgrey">Mesh</span> 👆 ➡️ <span class="block-darkgrey">Shift</span> ➕ <span class="block-darkgrey">S</span> ➡️ <span class="block-darkgrey">Cursor to Selected</span> <span class="block-lightgreen">3D 커서 위치 설정</span>

⬇️

<span class="block-darkgrey">Object Mode</span> ➡️ <span class="block-darkgrey">Object</span> 👆 ➡️ <span class="block-darkgrey">RMB</span> ➡️ <span class="block-darkgrey">Set Origin</span> ➡️ <span class="block-darkgrey">Origin to 3D Cursor</span> <span class="block-lightgreen">3D 커서 위치로 Origin 설정</span>

📝 두 개 이상의 Vertex를 선택 후 <span class="block-darkgrey">Cursor to Selected</span>를 사용하면 그 중간에 3D 커서를 위치시킬 수 있습니다.

📝 <span class="block-darkgrey">Origin to Geometry</span>를 사용할 경우 메시의 중심에 Origin이 설정됩니다.

📝 <span class="block-lightgreen">주황색 점</span>은 현재 오브젝트의 Origin(Pivot)을 의미합니다.

📝 Origin을 <span class="block-lightgreen">World Origin(0, 0, 0)</span>에 두면 게임 엔진에서 사용할 때 편할 수 있습니다. 오브젝트 작업 시 Mesh의 끝을 Z=0에 두고 World Origin에 Origin을 설정하고 작업하는 습관을 들여보는 것도 좋습니다.

<img src="/img/Blender/SetOrigin.png"/>

🔍 Edge를 선택하고 Cursor to Selected를 사용해 두 Vertex 사이에 3D 커서를 위치시킨 후 Origin to 3D Cursor를 사용해 Origin(주황색 점)을 설정한 예시 💡 안쪽에 파인 Face는 Scale을 조금 줄여 평면에서 볼 때 더 자연스럽게 보이도록 설정했습니다.

# Reset Vectors
{: .notice--warning}

📢 커스텀 노멀 데이터를 삭제하고, 기본 노멀로 재계산합니다. Auto Smooth과 충돌하는 커스텀 노멀 데이터로 인해 셰이딩이 깨질 때 사용할 수 있습니다.

<span class="block-darkgrey">Edit Mode</span> ➡️ <span class="block-darkgrey">Mesh</span> 👆 ➡️ <span class="block-darkgrey">Alt</span> ➕ <span class="block-darkgrey">N</span> ➡️ <span class="block-darkgrey">Reset Vectors</span>

# Sidebar
{: .notice--warning}

📢 Vertex의 Location 등을 볼 수 있는 사이드 바를 엽니다.

<span class="block-darkgrey">N</span>

# Select Tool
{: .notice--warning}

<span class="block-darkgrey">W</span>

# Snap
{: .notice--warning}

📢 뷰포트 상단의 <span class="block-lightgreen">자석 모양 아이콘</span>입니다. 바로 우측에 있는 Snapping 아이콘을 눌러 Snap To를 Increment로 설정하면 Transform을 수정할 때 Grid(격자) 단위로 수정할 수 있습니다.(🚨Snapping의 Affect 설정 확인)

<span class="block-darkgrey">Shift</span> ➕ <span class="block-darkgrey">Tab</span> Snap Toggle

# X-Ray Mode
{: .notice--warning}

📢 X-Ray 모드로 Edit 모드에서 Orthographic viewpoint 일 때 드래그로 뒤쪽 vertex도 선택할 수 있는 장점이 있습니다.

<span class="block-darkgrey">Alt</span> ➕ <span class="block-darkgrey">Z</span>

# Viewport Shading Mode
{: .notice--warning}

<span class="block-darkgrey">Z</span>

➡️ <span class="block-darkgrey">Solid</span> 기본 솔리드(흰색) 모드

➡️ <span class="block-darkgrey">Wireframe</span> 와이어프레임(격자) 모드 <span class="block-darkgrey">Shift</span> ➕ <span class="block-darkgrey">Z</span> 숏컷

➡️ <span class="block-darkgrey">Rendered</span> 렌더링된 모습

➡️ <span class="block-darkgrey">Material Preview</span> 재질 미리보기 모드(라이팅 적용)

# Select -L-inked
{: .notice--warning}

📢 해당 Mesh와 연결된 Mesh를 전체 선택합니다.

<span class="block-darkgrey">Edit Mode</span> ➡️ <span class="block-darkgrey">Mesh</span> 👆 ➡️ <span class="block-darkgrey">L</span>

# Vertex, Edge, Face select
{: .notice--warning}

<span class="block-darkgrey">Edit Mode</span>

➡️ <span class="block-darkgrey">Number Row 1</span> Vertex select

➡️ <span class="block-darkgrey">Number Row 2</span> Edge select

➡️ <span class="block-darkgrey">Number Row 3</span> Face select

🚨 텐키리스 키보드의 경우 <span class="block-darkgrey">Edit</span> ➡️ <span class="block-darkgrey">Preferences</span> ➡️ <span class="block-darkgrey">Input</span> ➡️ <span class="block-darkgrey">Keyboard</span> ➡️ <span class="block-darkgrey">Emulate Numpad</span> 가 <span class="block-lightgreen">true</span>로 되어있을 수 있습니다. 이 경우 <span class="block-lightgreen">Number Row</span>가 <span class="block-lightgreen">Numpad</span>로 작동함에 주의해야 합니다. 텐키리스 키보드는 <span class="block-lightgreen">Orthographic viewpoint</span>의 경우 <span class="block-darkgrey">`(Backtick)</span> 키로 선택할 수 있습니다.

# E-xtrude
{: .notice--warning}

📢 Mesh를 복제해 확장하는 기능입니다.

<span class="block-darkgrey">Edit Mode</span> ➡️ <span class="block-darkgrey">Mesh</span> 👆 ➡️ <span class="block-darkgrey">E</span> ➡️ 🖱️

🚨 Extrude 후 우클릭으로 취소해도 Mesh는 복제되어 있음에 주의해야 합니다.

# I-nset
{: .notice--warning}

📢 Face를 복제해 안쪽으로 확장하는 기능입니다.

<span class="block-darkgrey">Edit Mode</span> ➡️ <span class="block-darkgrey">Face</span> 👆 ➡️ <span class="block-darkgrey">I</span> ➡️ 🖱️

# M-erge
{: .notice--warning}

📢 여러 개의 Vertex를 하나로 병합하는 기능입니다.

<span class="block-darkgrey">Edit Mode</span> ➡️ <span class="block-darkgrey">Vertex</span> 👆 ➡️ <span class="block-darkgrey">M</span>

➡️ <span class="block-darkgrey">At Center</span> 선택한 Vertex를 중앙 지점으로 병합합니다.

➡️ <span class="block-darkgrey">At Cursor</span> 선택한 Vertex를 3D 커서 위치로 병합합니다.

➡️ <span class="block-darkgrey">At First</span> 첫 번째로 선택한 Vertex 위치로 병합합니다.

➡️ <span class="block-darkgrey">At Last</span> 마지막으로 선택한 Vertex 위치로 병합합니다.

➡️ <span class="block-darkgrey">By Distance</span> 중복된(겹쳐져 있는) Vertex를 병합합니다.

# F-ill
{: .notice--warning}

📢 선택한 Vertex, Edge 사이를 Edge, Face로 채우는 기능입니다.

<span class="block-darkgrey">Edit Mode</span> ➡️ <span class="block-darkgrey">Vertex or Edge</span> 👆 ➡️ <span class="block-darkgrey">F</span>

# Connect
{: .notice--warning}

📢 선택한 두 Vertex 사이에 Edge를 생성해 Face를 분리하는 기능입니다.

<span class="block-darkgrey">Edit Mode</span> ➡️ <span class="block-darkgrey">Vertex</span> 👆 ➡️ <span class="block-darkgrey">Shift</span> ➕ <span class="block-darkgrey">Vertex</span> 👆 ➡️ <span class="block-darkgrey">J</span>

# Loop Cut
{: .notice--warning}

📢 엣지 루프를 추가하거나 세분화할 때 사용합니다.

<span class="block-darkgrey">Edit Mode</span> ➡️ <span class="block-darkgrey">Ctrl</span> ➕ <span class="block-darkgrey">R</span> ➡️ 🖱️

➡️ <span class="block-lightgreen">Loop Cut and Slide Panel</span> 을 통해 Number of Cuts, Smoothness 등을 조절합니다.

📝 노란 선일 때 휠 스크롤을 통해 컷 개수(Number of Cuts)를 정할 수 있습니다.

📝 우클릭으로 취소하면 중앙에 생성됩니다.

📝 일정하게 바로 컷 하고 싶다면 <span class="block-darkgrey">Edge, Face</span> 👆 ➡️ <span class="block-darkgrey">RMB</span> ➡️ <span class="block-darkgrey">Subdivide</span> 을 사용하는 방법도 있습니다.

# B-evel
{: .notice--warning}

📢 Vertex, Edge의 모서리를 둥글게 깎아 부드러운 형태로 만드는 기능입니다.

<span class="block-darkgrey">Edit Mode</span> ➡️ <span class="block-darkgrey">Mesh</span> 👆 ➡️ <span class="block-darkgrey">Ctrl</span> ➕ <span class="block-darkgrey">B</span> ➡️ 🖱️

➡️ <span class="block-lightgreen">Bevel Panel</span> 을 통해 Vertices에 적용할지 Edges에 적용할지 Width, Segments, Shape 등 상세 조절