---
title:  "캔버스 렌더 모드"
categories: Unity
tag: [ui]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# Screen Space - Overlay
{: .notice--warning .text-center}

씬에 카메라가 없어도 게임 뷰 제일 후에 렌더링<br>
(하이어라키 순서에 따라 영향을 받을 수 있다고 한다)

# Screen Space - Camera
{: .notice--warning .text-center}

카메라를 지정해 해당 카메라에서 캔버스를 렌더링<br>
카메라와 캔버스 사이에 있는 오브젝트는 캔버스 앞에 있는것 처럼 보여진다
(3d 오브젝트를 두고 회전시킬 수 있다)

# World Space
{: .notice--warning .text-center}

캔버스를 World안에 둘 수 있다. 예를들면 컴퓨터의 모니터나 태블릿PC 같은 경우로 사용할 수 있다.