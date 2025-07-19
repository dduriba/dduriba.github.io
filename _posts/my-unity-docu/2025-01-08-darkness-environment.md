---
title: "어두운 환경 구현"
categories: my-unity-docu
tag: [개발일지]
excerpt: "Lighting Environment"
---




<span style="color:gray">unity version 2022.3.7f1</span>




# Lighting Environment 탭의 프로퍼티로 어두운 환경 구현
{: .notice}




# Lighting Environment 속성 알아보기
{: .notice}

Lighting Environment 창(<span class="color-control">Window</span>-><span class="color-control">Rendering</span>-><span class="color-control">Lighting</span>-><span class="color-control">Environment</span>)을 열어 줍니다.

<span class="li-1">Skybox Material : 하늘이나 기타 먼 배경을 시뮬레이션하기 위해 씬의 다른 모든 요소 뒤에 나타나는 머티리얼</span>

<span class="li-1">Sun Source : 씬에서 태양으로 사용할 광원을 선택합니다.Unity는 이 광원을 사용하여 스카이박스와 씬에 대한 태양 위치 및 강도의 효과를 시뮬레이션합니다.이 옵션을 None으로 설정하면 Unity는 씬에서 가장 밝은 방향 광원을 태양으로 간주합니다.Render Mode 프로퍼티가 Not Important로 설정된 광원은 스카이박스에 영향을 주지 않습니다.</span>

<span class="li-1">Realtime Shadow Color : 서브트랙티브 광원 모드에서 실시간 그림자를 렌더링할 때 Unity가 사용하는 컬러를 정의합니다.</span>

<details>
<summary class="color-comment">Environment Lighting(이 섹션에는 현재 씬의 주변광에 영향을 미치는 설정이 들어 있습니다.)</summary>
<div markdown="1">

<span class="li-1">Source : 씬의 주변광에 대한 소스 컬러를 정의할 때 사용합니다.</span>

<span class="li-2">Skybox : Skybox Material 에 설정된 스카이박스의 컬러를 사용하여 다른 각도에서 나오는 주변광을 판단합니다. 이를 통해 Gradient 보다 더 정밀한 효과를 구현할 수 있습니다.</span>

<span class="li-2">Gradient : 	하늘, 지평선, 지면의 주변광에 사용할 컬러를 각각 다르게 설정하고 서로 부드럽게 블렌딩합니다.</span>

<span class="li-2">Color : 모든 주변광에 플랫 컬러를 사용합니다.</span>

<span class="li-1">Intensity Multiplier : 씬의 주변광 밝기를 설정하는 데 사용합니다.(이 프로퍼티는 Source 가 Skybox 으로 설정된 경우에만 표시됩니다. Gradient나 Color로 설정한 경우 컬러를 지정하는 프로퍼티가 표시됩니다.)</span>

</div>
</details>

<details>
<summary class="color-comment">Environment Reflections(이 섹션에는 반사 프로브 베이킹용 전역 설정과 전역 반사에 영향을 주는 설정이 나와 있습니다.)</summary>
<div markdown="1">

<span class="li-1">Source : 반사 효과에 스카이박스를 사용할지, 아니면 원하는 큐브맵을 사용할지 지정합니다.</span>

<span class="li-2">Skybox : 스카이박스를 반사 소스로 사용하려는 경우 선택합니다.</span>

<span class="li-2">Custom : 반사에 큐브맵 에셋 또는 큐브 타입의 렌더 텍스처를 사용하려는 경우 선택합니다.</span>

<span class="li-1">Resolution : 반사 목적으로 스카이박스의 해상도를 설정하려는 경우 선택합니다. 이 프로퍼티는 Source 가 Skybox 로 설정된 경우에만 표시됩니다.</span>

<span class="li-1">Cubemap : 반사 목적으로 사용할 큐브맵을 지정합니다. 이 프로퍼티는 Source 가 Custom 으로 설정된 경우에만 표시됩니다.</span>

<span class="li-1">Compression : 반사 텍스처의 압축 여부를 설정합니다.</span>

<span class="li-2">Auto : 압축 포맷이 적합하면 반사 텍스처를 압축합니다.</span>

<span class="li-2">Uncompressed : 반사 텍스처를 압축하지 않고 메모리에 저장합니다.</span>

<span class="li-2">Compressed : 텍스처를 압축합니다.</span>

<span class="li-1">Intensity Multiplier : 반사 소스가 반사 오브젝트에 표시되는 각도입니다.</span>

<span class="li-1">Bounces : 한 오브젝트의 반사가 다른 오브젝트에 의해 반사될 때 반사 바운스가 일어납니다. 이 프로퍼티를 사용하여 반사 프로브가 오브젝트 간에 오고가는 반사를 평가하는 횟수를 설정할 수 있습니다. 값을 1로 설정하면 Unity는 처음 반사(Reflection Source 프로퍼티에 지정된 스카이박스 또는 큐브맵)만 고려합니다.</span>

</div>
</details>




# 어두운 환경 구현하기
{: .notice}




## 구현 방법 (1)
{: .notice--primary}

어두운 환경(밤)으로 미리 설정된 스카이박스를 사용합니다.




## 구현 방법 (2)
{: .notice--primary}

스카이 박스를 사용하지 않아도 될 경우 Skybox Material을 None으로 지정합니다.




## 구현 방법 (3)
{: .notice--primary}

어둡지 않은 스카이 박스를 사용하며 어둡게 만들고 싶은 경우 Environment Lighting->Intensity Multiplier, Environment Reflections->Intensity Multiplier의 값을 조절합니다.(매우 어둡게 만들 경우 두 값 모두 0으로 설정합니다.)




## 프로젝트에 적용한 방법
{: .notice--primary}

어두운 환경으로 설정된 스카이박스를 사용, 완전하게 어둡게 만들기 위해 Environment Lighting->Intensity Multiplier의 값을 0으로 설정, 자연스러움을 위해 Environment Reflections->Intensity Multiplier의 값은 1로 설정