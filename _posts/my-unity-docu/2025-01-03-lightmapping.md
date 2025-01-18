---
title: "Lightmapping(Baked Lighting)"
categories: my-unity-docu
tag: [최적화]
---

<span style="color:gray">unity version 2022.3.7f1</span>

# 라이트매핑(Lightmapping)
{: .notice--warning}

씬의 표면 밝기를 미리 계산해 텍스처로 저장하는 기능으로 해당 텍스처는 <span class="highlight-pencel-black">라이트맵</span>이라고 합니다. 실시간 조명은 연산에 많은 부담이 되기 때문에 움직이지 않는 게임오브젝트에 라이트매핑을 적용해 연산 부담을 줄일 수 있습니다.

라이트매핑 설정 방법
{: .notice--primary}

정적 게임오브젝트 설정
{: .notice}

조명의 영향을 받을 정적 게임오브젝트들의 <span class="highlight-pencel-black">Static</span> 옵션에서 Contribute GI(Contribute Global Illumination)를 활성화 시켜줍니다.

조명 게임오브젝트 설정
{: .notice}

정적 게임오브젝트에 영향을 줄 조명의 Light 컴포넌트에서 Mode를 <span class="highlight-pencel-black">Baked</span>로 변경합니다.

라이팅 창 설정
{: .notice}

Lighting 창(<span class="highlight-black">Window</span>→<span class="highlight-black">Rendering</span>→<span class="highlight-black">Lighting</span>)을 열어 Scene탭의 Mixed Lighting의 <span class="highlight-pencel-black">Baked Global Illumination</span>을 활성화 시켜줍니다.

라이트맵 생성
{: .notice}

Lighting 창에서 <span class="highlight-pencel-black">Generate Lighting</span>로 라이트맵을 생성해 줍니다.

<span class="highlight-pencel-black">개발 단계에서 Auto Generate는 컴퓨팅 비용이 증가하기 때문에 비활성화</span>한 뒤, 정적 게임오브젝트의 트랜스폼 변화가 있는 등 라이트 맵 생성이 필요할 때마다 Generate Lighting을 이용하고 Auto Generate는 빌드 단계에서 필요시 다시 활성화할 수 있습니다.