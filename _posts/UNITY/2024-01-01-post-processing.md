---
title:  "포스트 프로세싱"
excerpt: "Post Processing"
categories: Unity
tag: [Post Processing]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# 포스트 프로세싱?
{: .notice--warning .text-center}

기존에 렌더링된 씬에 렌더링 효과를 더하는 작업

[https://docs.unity3d.com/kr/2019.4/Manual/BestPracticeMakingBelievableVisuals8.html](https://docs.unity3d.com/kr/2019.4/Manual/BestPracticeMakingBelievableVisuals8.html)

# 적용 방법
{: .notice--warning .text-center}

Window -> Package Manager에서 먼저 Post Processing을 인스톨한다.

카메라 오브젝트에 PostProcessing 레이어를 만들어 추가해준다.

같은 오브젝트에 Post-Process Layer 컴포넌트를 추가해주고<br>
Volumn Blending-Layer를 앞서 설정한 PostProcessing으로 변경<br>
카메라 컴포넌트의 Rendering Path를 Deferred로 변경해주고 MSAA를 Off.<br>
Post-process Layer 컴포넌트에서 Anti-aliasing을 설정해준다.

다음은 같은 오브젝트에 Post-process Volume 컴포넌트를 추가해주고,<br>
Is Global을 True로, Profile을 New로 생성해준다.
(이 Profile은 Clone을 통해 다양하게 설정해둔 포스트 프로세싱 옵션을 프리팹처럼 사용할 수 있다)

이제 Add effect...를 통해 원하는 포스트 프로세싱 기능을 사용할 수 있다.

<img src="/img/Unity/post-processing-1.PNG"/>
<img src="/img/Unity/post-processing-2.PNG"/>

