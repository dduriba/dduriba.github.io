---
title:  "Text Mesh Pro"
categories: Unity
tag: [ui]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# Overflow : Linked
{: .notice--warning .text-center}

할당된 Text UI 영역이 Overflow 될 경우 Overflow된 만큼 
Linked된 Text UI 영역에 Text가 출력되는 방법, 
두 개 이상의 Text UI를 노드 형식으로 연결할 수 있으며 
기준이 되는 Text UI 오브젝트의 Overflow를 Linked로 설정했을 때 
나타나는 공간에 추가로 나타낼 Text UI 오브젝트를 연결해 설정

# 폰트 변경
{: .notice--warning .text-center}

Window - TextMeshPro - Font Asset Creator에서 
.ttf 폰트 파일을 소스로 두고 Generate Font Atlas > Save 후 
만들어진 SDF Font Asset을 Text UI 오브젝트에 연결

# 카메라를 바라보는 빌보드 UI
{: .notice--warning .text-center}

적들의 머리 위에 이름이나 체력 바를 만들려고 한다.<br>
Canvas 오브젝트를 적 오브젝트 하위에 두고 
Canvas 오브젝트의 Render Mode = World Space, Event Camera = Main Camera 연결 후
Look At Constraint 컴포넌트를 추가, Sources에 Main Camera를 연결해 주고 
Activate를 눌러 Is Active를 활성화해준다.<br>
UI가 뒤집어져 있다면 Text 오브젝트의 회전을 건드려 보자(Rotation Y = 180)
