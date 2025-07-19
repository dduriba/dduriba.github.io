---
title: "Audio"
categories: my-unity-docu
tag: [컴포넌트]
excerpt: "Audio Listener, Audio Source"
---




<span style="color:gray">unity version 2022.3.7f1</span>




# Audio Listener
{: .notice}

오디오 리스너 컴포넌트는 기본적으로 메인 카메라에 추가되어 있습니다. 카메라가 눈이라면 오디오 리스너는 귀에 해당해 일반적으로 카메라에 추가합니다.




# Audio Source
{: .notice}




## AudioClip
{: .notice--primary}

재생될 사운드 클립에 대한 레퍼런스입니다.




## Output
{: .notice--primary}

이 프로퍼티를 사용하면 클립을 오디오 믹서에 출력합니다.(이 프로퍼티를 사용하지 않으면 기본적으로 오디오 리스너에 직접 출력됩니다.)




## Mute
{: .notice--primary}

클립을 음소거 상태로 재생합니다.




## Bypass Effects
{: .notice--primary}

오디오 소스에 적용된 필터 효과를 즉시 우회해 키고 끕니다.




## Bypass Listener Effects
{: .notice--primary}

모든 리스너 효과를 즉시 우회해 키고 끕니다.




## Bypass Reverb Zones
{: .notice--primary}

모든 리버브 존을 즉시 우회해 키고 끕니다.




## Play On Awake
{: .notice--primary}

플레이 명령을 내리지 않아도 컴포넌트가 로드되면 클립을 플레이합니다.




## Loop
{: .notice--primary}

오디오 클립의 재생이 끝나면 반복 재생합니다.




## Priority
{: .notice--primary}

재생되는 오디오 소스들 간 우선순위를 설정합니다.(0 - 256, 숫자가 낮을수록 우선 순위입니다. BGM은 0으로 설정해야 합니다.)




## Volume
{: .notice--primary}

오디오 리스너로부터 1월드 유닛(1 Meter) 거리에서 소리가 얼마나 크게 들리는지 정의합니다.




## Pitch
{: .notice--primary}

재생 속도를 설정합니다.




## Stereo Pan
{: .notice--primary}

2D 사운드 환경에서 소리가 나는 좌우 위치를 설정합니다.




## Spatial Blend
{: .notice--primary}

현재 오디오 소스를 2D 사운드로만 사용하거나 3D 사운드로만 사용할 수도 있으며 혼합해 사용할 수 있습니다.




## Reverb Zone Mix
{: .notice--primary}

리버브 존으로 보내지는 출력 신호의 양을 설정합니다.(동굴에 진입하거나 사운드를 극대화 시킬 때 사용합니다.)




## 3D Sound Settings
{: .notice--primary}

<span class="li-1">Doppler Level : 현재 오디오 소스에 적용될 도플러 이펙트(파원과 관찰자의 상대 속도에 따라 소리의 높낮이가 달리 들리는 현상)의 정도를 결정합니다.</span>

<span class="li-1">Spread : 스피커 공간에서 사운드가 퍼지는 각도를 설정합니다.(0 - 360)</span>

<span class="li-1">Volume Rolloff : 거리에 따라 사운드(Volume, Spatial Blend, Spread, Reverb Zone Mix)가 페이드되는 속도를 그래프로 설정하는데, 해당 타입을 지정할 수 있습니다.</span>

<span class="li-2">Rogarythmic Rolloff : 오디오 소스에 가까우면 사운드가 크지만 멀어지면 매우 빠른 속도로 사운드가 작아집니다.</span>

<span class="li-2">Linear Rolloff : 오디오 소스에서 멀어질수록 거리에 따라 사운드가 일정하게 작아집니다.</span>

<span class="li-2">Custom Rolloff : 거리에 따른 사운드 조절을 그래프로 직접 설정합니다.(다른 두 타입에서 사운드 라인에 마우스 우클릭→Add Key를 통해 형태를 가져와 커스텀이 가능하고 자동으로 타입은 Custom Rolloff로 바뀌게 됩니다.)</span>

<span class="li-1">Min Distance : 사운드가 최대치로 들릴 거리입니다.</span>

<span class="li-1">Max Distance : 사운드가 들릴 최대 거리입니다.</span>

<img src="/img/my-unity-docu/VolumeRolloffGraph.png"/>

사진 1. Volume Rolloff Graph


<img src="/img/my-unity-docu/VolumeRolloffDistance.png"/>

사진 2. 씬 뷰에서 선으로 이루어진 구를 통해 Min/Max Distance를 확인할 수 있습니다.