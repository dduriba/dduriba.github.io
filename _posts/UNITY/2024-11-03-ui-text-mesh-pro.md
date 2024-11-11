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