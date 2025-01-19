---
title: "Post Processing"
categories: my-unity-docu
---

<span style="color:gray">unity version 2022.3.7f1</span>

# 포스트 프로세싱
{: .notice--warning}

포스트 프로세싱이란 렌더링 된 씬에 렌더링 효과를 더하는 작업으로 보다 적은 비용으로 씬에 실체감이나 특수한 효과를 더 해줍니다.

포스트 프로세싱 적용 방법
{: .notice--primary}

포스트 프로세싱을 사용하려면 유니티의 Post Processing 패키지가 설치되어 있어야 합니다.

유저 레이어 추가
{: .notice}

적용할 카메라 오브젝트에서 Layer→Add Layer...→Layers 토글을 열어 유저 레이어를 추가해주고(본문에선 레이어 이름을 "PostProcessing"으로 사용했습니다.) 카메라 오브젝트의 레이어를 만들어 준 유저 레이어로 적용합니다.

Post-process Layer 추가
{: .notice}

카메라 오브젝트에 Post-process Layer 컴포넌트를 추가해 Volume blending→Layer에 만들어 준 유저 레이어를 적용합니다.

Post-process Volume 추가
{: .notice}

카메라 오브젝트에 Post-process Volume 컴포넌트를 추가

- [X] Is Global = true

- [X] Profile = New로 새로운 프로파일을 만들어 Add effect→Unity에서 필요한 효과를 추가합니다.(여러 개의 프로파일을 만들어 상황 마다 다른 포스트 프로세싱을 사용할 수 있습니다.)

## Ambient Occlusion
{: .notice--success}

음영을 더 강조해 보다 입체감있고 사실적인 그래픽으로 나타나게 해줍니다.

적용 전
{: .notice--primary}

<img src="/img/my-unity-docu/Post-Process-Off.png"/>

적용 후
{: .notice--primary}

<img src="/img/my-unity-docu/Ambient-Occlusion-On.png"/>

- [ ] Intensity = 1

- [ ] Thickness Modifier = 2

## Bloom
{: .notice--success}

빛이 퍼져나가는 느낌으로 광원을 더 현실감 있게 만들어 줍니다.

적용 전
{: .notice--primary}

<img src="/img/my-unity-docu/Post-Process-Off.png"/>

적용 후
{: .notice--primary}

<img src="/img/my-unity-docu/Bloom-On.png"/>

- [ ] Intensity = 5

- [ ] Threshold = 0.9

- [ ] Soft Knee = 0.3

- [ ] Diffusion = 8

## Color Grading
{: .notice--success}

색보정 효과입니다.

적용 전
{: .notice--primary}

<img src="/img/my-unity-docu/Post-Process-Off.png"/>

적용 후
{: .notice--primary}

<img src="/img/my-unity-docu/Color-Grading-On.png"/>

- [ ] Tonemapping→Mode = ACES

## Grain
{: .notice--success}

화면에 노이즈를 만들어 옛날 필름 느낌을 줍니다.(공포 게임이나 게임 내 캠코더 등에 사용합니다.)

적용 전
{: .notice--primary}

<img src="/img/my-unity-docu/Post-Process-Off.png"/>

적용 후
{: .notice--primary}

<img src="/img/my-unity-docu/Grain-On.png"/>

- [ ] Colored = true

- [ ] Intensity = 1

- [ ] Size = 3

- [ ] Luminance Contribution = 1

## Vignette
{: .notice--success}

화면 외곽 부분을 어둡게 만듭니다.

적용 전
{: .notice--primary}

<img src="/img/my-unity-docu/Post-Process-Off.png"/>

적용 후
{: .notice--primary}

<img src="/img/my-unity-docu/Vignette-On.png"/>

- [ ] Mode = Classic

- [ ] Color = Black

- [ ] Center x = 0.5, y = 0.5

- [ ] Intensity = 0.6

- [ ] Smoothness = 1

- [ ] Roundness = 1

- [ ] Rounded = true