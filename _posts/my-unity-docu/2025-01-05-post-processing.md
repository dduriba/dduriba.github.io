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

적용할 카메라 오브젝트에서 <span class="highlight-black">Layer</span>→<span class="highlight-black">Add Layer...</span>→Layers 토글을 열어 <span class="highlight-pencel-black">유저 레이어를 추가</span>해주고(본문에선 유저 레이어 명을 "PostProcessing"으로 사용했습니다.) 카메라 오브젝트의 레이어에 만들어 준 <span class="highlight-pencel-black">유저 레이어를 적용</span>합니다.

Post-process Layer 추가
{: .notice}

카메라 오브젝트에 <span class="highlight-pencel-black">Post-process Layer</span> 컴포넌트를 추가해 <span class="highlight-black">Volume blending</span>→Layer에 만들어 준 <span class="highlight-pencel-black">유저 레이어를 적용</span>합니다.

Post-process Volume 추가
{: .notice}

카메라 오브젝트에 <span class="highlight-pencel-black">Post-process Volume</span> 컴포넌트를 추가

- [X] <span class="highlight-black">Is Global</span> = true

- [X] <span class="highlight-black">Profile</span> = New로 새로운 프로파일을 만들어 <span class="highlight-black">Add effect</span>→<span class="highlight-black">Unity</span>에서 필요한 효과를 추가합니다.(여러 개의 프로파일을 만들어 상황 마다 다른 포스트 프로세싱을 사용할 수 있습니다.)

## Ambient Occlusion
{: .notice--success}

음영을 더 강조해 보다 입체감있고 사실적인 그래픽으로 나타나게 해줍니다.

적용 전
{: .notice--primary}

<img src="/img/my-unity-docu/Post-Process-Off.png"/>

적용 후
{: .notice--primary}

<img src="/img/my-unity-docu/Ambient-Occlusion-On.png"/>

- [ ] <span class="highlight-black">Intensity</span> = 1

- [ ] <span class="highlight-black">Thickness Modifier</span> = 2

## Bloom
{: .notice--success}

빛이 퍼져나가는 느낌으로 광원을 더 현실감 있게 만들어 줍니다.

적용 전
{: .notice--primary}

<img src="/img/my-unity-docu/Post-Process-Off.png"/>

적용 후
{: .notice--primary}

<img src="/img/my-unity-docu/Bloom-On.png"/>

- [ ] <span class="highlight-black">Intensity</span> = 5

- [ ] <span class="highlight-black">Threshold</span> = 0.9

- [ ] <span class="highlight-black">Soft Knee</span> = 0.3

- [ ] <span class="highlight-black">Diffusion</span> = 8

## Color Grading
{: .notice--success}

색보정 효과입니다.

적용 전
{: .notice--primary}

<img src="/img/my-unity-docu/Post-Process-Off.png"/>

적용 후
{: .notice--primary}

<img src="/img/my-unity-docu/Color-Grading-On.png"/>

- [ ] <span class="highlight-black">Tonemapping</span>→<span class="highlight-black">Mode</span> = ACES

## Grain
{: .notice--success}

화면에 노이즈를 만들어 옛날 필름 느낌을 줍니다.(공포 장르나 게임 내 캠코더 등에 사용합니다.)

적용 전
{: .notice--primary}

<img src="/img/my-unity-docu/Post-Process-Off.png"/>

적용 후
{: .notice--primary}

<img src="/img/my-unity-docu/Grain-On.png"/>

- [ ] <span class="highlight-black">Colored</span> = true

- [ ] <span class="highlight-black">Intensity</span> = 1

- [ ] <span class="highlight-black">Size</span> = 3

- [ ] <span class="highlight-black">Luminance Contribution</span> = 1

## Vignette
{: .notice--success}

화면 외곽 부분을 어둡게 만듭니다.

적용 전
{: .notice--primary}

<img src="/img/my-unity-docu/Post-Process-Off.png"/>

적용 후
{: .notice--primary}

<img src="/img/my-unity-docu/Vignette-On.png"/>

- [ ] <span class="highlight-black">Mode</span> = Classic

- [ ] <span class="highlight-black">Color</span> = Black

- [ ] <span class="highlight-black">Center</span> = 0.5(x), 0.5(y)

- [ ] <span class="highlight-black">Intensity</span> = 0.6

- [ ] <span class="highlight-black">Smoothness</span> = 1

- [ ] <span class="highlight-black">Roundness</span> = 1

- [ ] <span class="highlight-black">Rounded</span> = true