---
title: "Occlusion Culling & Frustum Culling"
categories: my-unity-docu
tag: [최적화]
excerpt: "Occluder, Occludee, Dynamic Occlusion"
---

<span style="color:gray">unity version 2022.3.7f1</span>

# 오클루전 컬링(Occlusion Culling)
{: .notice--warning}

카메라를 뷰 프러스텀 영역 안에서 가까운 오브젝트에 의해 가려져 보이지 않는 오브젝트를 렌더링 하지 않는 기능입니다.

- [X] <span class="highlight-black">작동 방식</span> : 씬의 데이터를 생성 후 런타임 시점에서 해당 데이터를 사용해 카메라가 볼 수 있는 요소를 결정(Bake)합니다. 씬을 셸로 나누어 셸 내 지오메트리와 인접 셸 간의 가시성을 설명하는 데이터를 생성 후 생성된 데이터의 크기를 줄이기 위해 가능한 경우 셸을 병합합니다. 런타임 시점에서 유니티는 베이크된 데이터를 메모리에 로드, 오클루전 컬링 프로퍼티가 활성화된 각 카메라에 대해 해당 데이터에 대한 쿼리를 수행해 카메라가 볼 수 있는 요소를 결정합니다.

- [X] <span class="highlight-black">사용 시기</span> :

  + [ ] 오클루전 컬링 데이터는 런타임 시점에서 메모리에 로드되므로 디바이스에 해당 데이터를 로드할 만큼 충분한 메모리가 있어야합니다.

  + [ ] 오클루전 컬링은 작고 윤곽이-뚜렷한 영역이-견고한 게임 오브젝트에 의해 서로 명확하게 분리(복도로 연결된 방)된 씬에서 잘 작동합니다. 야외 씬에서도 사용할 수 있지만 오브젝트끼리 가려지는 경우가 적은 경우 얻는 이득이 적고 오히려 오버헤드가 발생할 수 있음에 주의해야 합니다.

  + [ ] 프로젝트가 런타임에 씬 찌오메트리를 생성하는 경우 해당 기능은 적합하지 않습니다.

- [X] <span class="highlight-black">오클루더, 오클루디, 동적 오클루전</span> :

  + [ ] 오클루더(Occluder) : 다른 렌더러를 가리는 게임오브젝트(정적 게임 오브젝트)

  + [ ] 오클루디(Occludee) : 다른 게임오브젝트에 의해 가려지는 렌더러(정적 게임 오브젝트)

  + [ ] 동적 오클루전(Dynamic Occlusion) : 동적 게임오브젝트의 경우 오클루더에 의해 컬링 되려면 해당 Mesh Renderer 컴포넌트에서에서  <span class="highlight-pencel-black">Dynamic Occlusion</span>을 활성화 시켜야합니다.(동적 게임 오브젝트의 경우 오클루전 컬링 데이터에 베이크할 수 없으므로 동적 오클루전을 활성화해 오클루더가 해당 렌더러를 가릴 때 컬링할 수 있도록 해줍니다.) 오클루전 컬링을 사용해 동적 게임 오브젝트를 가릴 수 있으나 동적 게임오브젝트는 다른 게임오브젝트를 가릴 수 없습니다.(동적 게임 오브젝트는 오클루디가 될 수 있지만 오클루더는 될 수 없습니다.)

오클루전 컬링 설정 방법
{: .notice--primary}

카메라 설정
{: .notice}

카메라 컴포넌트의 Occlusion Culling을 활성화 시켜줍니다.

정적 게임오브젝트 설정
{: .notice}

적용할 정적 게임오브젝트들의 Static 옵션에서 Everything 또는 Occluder Static, Occludee Static을 선택합니다.(일반적으로 Everything을 사용합니다.)

동적 게임오브젝트 설정
{: .notice}

적용할 동적 게임오브젝트들의 Mesh Renderer 컴포넌트에서 Dynamic Occlusion을 활성화 시켜줍니다.

베이크
{: .notice}

오클루전 창을 열고(<span class="highlight-black">Window</span>→<span class="highlight-black">Rendering</span>→<span class="highlight-black">Occlusion Culling</span>)
Bake탭→Bake로 베이크를 시작합니다.

- [X] <span class="highlight-black">Bake 옵션</span> :

  + [ ] Smallet Occluder : 오브젝트를 Occluder로 인식할 게임 오브젝트의 최소 크기(M단위)로 이 값보다 작은 크기를 가지는 게임오브젝트는 다른 게임오브젝트를 가리지 않는다고 판단합니다. 값이 작을수록 컬링 정밀도는 올라가지만 데이터 크기가 늘어나고 오버헤드가 발생할 수 있습니다.

  + [ ] Smallet Hole : 카메라가 지오메트리 사이의 빈 공간으로 인식할 최소 거리(카메라가 들여다 볼 수 있는 가장 작은 직경(M단위))로 오브젝트들이 촘촘하게 배치되어 있을수록 더 작은 값을 설정해야 합니다.

  + [ ] Backface Threshold : 백페이스를 제거할 임계값으로 값이 작을수록 더 많은 백페이스를 제거합니다. 기본값인 100은 데이터에서 영역을 제거하지 않습니다. 값을 낮추면 파일 크기가 작아지지만 시각적 결함이 발생할 수 있습니다.

Bake가 끝나면 프로젝트 창에 씬의 이름으로 폴더가 생성되고 안에 컬링 데이터가 생성됩니다.

오클루전 컬링 창에서 Visualization을 선택하면 씬 뷰에서 오클루전 컬링 적용을 확인할 수 있습니다.

게임 뷰의 Status 창에서 Batches와 Saved by batching의 수치가 줄어듦을 확인할 수 있습니다.

# 프러스텀 컬링(Frustum Culling)
{: .notice--warning}

카메라의 뷰 프러스텀 영역 밖의 오브젝트들은 렌더링하지 않는 기능으로 유니티 내에서 기본적으로 적용됩니다. 카메라 컴포넌트의 Field of View, Clipping Planes 기능을 통해 프러스텀 영역을 조절할 수 있습니다.