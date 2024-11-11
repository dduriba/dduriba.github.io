---
title:  "Billboard UI"
categories: Unity
tag: [ui]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# 카메라를 바라보는 빌보드 UI
{: .notice--warning .text-center}

3D 일 때, 적들의 머리 위에 카메라를 바라보는 이름이나 체력 바를 만들려고 한다.<br>
Canvas 오브젝트를 적 오브젝트 하위에 두고 
Canvas 오브젝트의 Render Mode = World Space, Event Camera = Main Camera 연결 후
Look At Constraint 컴포넌트를 추가, Sources에 Main Camera를 연결해 주고 
Activate를 눌러 Is Active를 활성화해준다.<br>
UI가 뒤집어져 있다면 Text 오브젝트의 회전을 건드려 보자(Rotation Y = 180)