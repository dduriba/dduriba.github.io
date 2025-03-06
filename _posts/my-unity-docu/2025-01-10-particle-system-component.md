---
title: "Particle System"
categories: my-unity-docu
tag: [컴포넌트]
excerpt: "Particle System Modules"
---

<span style="color:gray">unity version 2022.3.7f1</span>

# Main Module
{: .notice--warning}

- [X] Duration : 파티클 시스템이 실행되는 총 시간(초)입니다.

- [X] Looping : Duration이 끝나도 자동으로 재실행합니다.

- [X] Prewarm : 처음 실행될 때 한 번 초기 상태를 준비하여 시작하자마자 파티클이 이미 퍼져 있는 것처럼 보이게 합니다. Looping 이 활성화되었을 때에만 작동합니다.

- [X] Start Delay : 파티클이 생성되기 전에 대기하는 시간(초)입니다.

  + [ ] Constant

  + [ ] Random Between Two Constants : 이 모드를 사용하여 최소/최대 값을 지정하면, 랜덤하게 지연 시간이 결정됩니다.

- [X] Start Lifetime : 개별 파티클이 살아 있는 시간(초)입니다.

  + [ ] Constant

  + [ ] Curve

  + [ ] Random Between Two Constants : 이 옵션을 사용하여 최소/최대 수명 범위를 설정할 수 있습니다.

  + [ ] Random Between Two Curves

- [X] Start Speed : 파티클이 처음 생성될 때의 속도를 결정합니다. 0으로 설정하면 정지된 상태로 생성됩니다.

  + [ ] Constant

  + [ ] Curve

  + [ ] Random Between Two Constants

  + [ ] Random Between Two Curves

- [X] 3D Start Size : 활성화하면 X, Y, Z 축 각각의 크기를 설정할 수 있습니다.

- [X] Start Size : 각 파티클의 초기 크기입니다.

  + [ ] Constant

  + [ ] Curve

  + [ ] Random Between Two Constants

  + [ ] Random Between Two Curves

- [X] 3D Start Rotation : 활성화하면 X, Y, Z 축별 회전을 개별적으로 설정할 수 있습니다.

- [X] Start Rotation : 파티클이 생성될 때의 회전 값(라디안 단위)입니다.

  + [ ] Constant

  + [ ] Curve

  + [ ] Random Between Two Constants

  + [ ] Random Between Two Curves

- [X] Flip Rotation : 0~1 사이 값을 설정하여 파티클의 회전을 반전할 수 있습니다. 0이면 기본 방향, 1이면 180도 반전됩니다.

- [X] Start Color : 각 파티클의 초기 컬러입니다.

  + [ ] Color

  + [ ] Gradient

  + [ ] Random Between Two Colors

  + [ ] Random Between Two Gradients

  + [ ] Random Color

- [X] Gravity Source

  + [ ] 3D physics

  + [ ] 2D physics

- [X] Gravity Modifier : Physics 창에서 설정된 중력 값을 스케일합니다. 이 값을 0으로 하면 중력 효과가 해제됩니다. 양수면 중력이 아래로 작용, 음수면 위쪽으로 작용합니다.

  + [ ] Constant

  + [ ] Curve

  + [ ] Random Between Two Constants

  + [ ] Random Between Two Curves

- [X] Simulation Space : 파티클의 움직임이 어느 공간을 기준으로 계산될지 설정합니다.

  + [ ] Local : 파티클이 부모 오브젝트의 로컬 공간에서 애니메이션화되도록 합니다.(부모 오브젝트와 함께 이동)

  + [ ] World : 파티클이 월드 공간에서 애니메이션화되도록 합니다.

  + [ ] Custom : 파티클이 커스텀 오브젝트에 대해 상대적으로 애니메이션화(선택한 커스텀 오브젝트와 함께 이동)되도록 합니다.

- [X] Simulation Speed : 파티클 시스템의 전체적인 속도를 조절합니다. 값이 1보다 크면 빠르게 실행, 1보다 작으면 느리게 실행됩니다.

- [X] Delta Time : 파티클의 움직임을 시간에 따라 어떻게 계산할지를 설정합니다.

  + [ ] Scaled : Time.timeScale의 영향을 받습니다. (예: 게임이 일시 정지되면 파티클도 정지)

  + [ ] Unscaled : Time.timeScale에 관계없이 항상 동일한 속도로 실행됩니다.

- [X] Scaling Mode : 부모 오브젝트의 크기 조절이 파티클에 어떻게 적용될지를 설정합니다.

  + [ ] Hierarchy : 부모의 크기 조절에 따라 파티클 크기도 조절됨.

  + [ ] Local : 파티클의 크기는 독립적으로 유지됨.

  + [ ] Shape : 파티클의 발사 방향이 부모의 크기에 따라 조정됨.

- [X] Play On Awake : 활성화하면 파티클 시스템이 씬에서 활성화될 때 자동으로 실행됩니다. 비활성화하면 Play()를 호출해야 실행됩니다.

- [X] Emitter Velocity Mode : 파티클 시스템이 Inherit Velocity 모듈과 Emission 모듈에 사용할 속도를 계산하는 방법을 선택합니다. 시스템은 Rigidbody 컴포넌트(존재하는 경우)를 사용하거나 트랜스폼 컴포넌트의 움직임을 추적하여 속도를 계산할 수 있습니다. Rigidbody 컴포넌트가 없는 경우 시스템은 기본적으로 트랜스폼 컴포넌트를 사용합니다.

  + [ ] Transform : 부모 오브젝트의 Transform 이동 속도를 반영

  + [ ] Rigidbody : 부모의 Rigidbody 속도를 반영

  + [ ] Custom

- [X] Max Particles : 동시에 존재할 수 있는 최대 파티클 개수입니다. 이 값을 초과하면 오래된 파티클이 사라집니다.

- [X] Auto Random Seed : 활성화하면 Unity가 자동으로 랜덤 시드를 설정하여 매번 다른 결과를 생성합니다. 비활성화하면 수동으로 시드를 설정하여 동일한 랜덤 결과를 유지할 수 있습니다.

- [X] Stop Action : 시스템에 속한 모든 파티클이 완료되어 시스템이 중지되었을 때 특정 동작을 수행하도록 설정할 수 있습니다. 시스템의 파티클이 모두 소멸되고 파티클의 수명이 지속 시간을 초과하면 시스템이 중지된 것으로 간주됩니다. 루프를 반복하는 시스템에서는 스크립트를 통해 중지되었을 때 중지된 것으로 간주됩니다.

  + [ ] None

  + [ ] Disable : 게임 오브젝트를 비활성화합니다.

  + [ ] Destroy : 게임 오브젝트를 파괴합니다.

  + [ ] Callback : OnParticleSystemStopped 콜백을 게임 오브젝트에 연결된 스크립트로 전송합니다.

- [X] Culling Mode : 파티클이 화면을 벗어나면 파티클 시스템 시뮬레이션을 일시정지할지 여부를 선택합니다. 오프스크린인 경우 컬링이 가장 효율적이지만, 오프스크린 효과의 시뮬레이션을 지속하는 것이 좋습니다.

  + [ ] Automatic : Unity가 자동으로 적절한 컬링 방식을 선택합니다. 루핑 시스템은 Pause 를, 기타 모든 시스템은 Always Simulate 를 사용합니다.

  + [ ] Pause and Catch-up : 시스템이 화면에서 벗어나면 시뮬레이션을 중단합니다. 뷰 안으로 다시 진입하면 시뮬레이션은 일시정지되지 않았다면 도달했을 포인트에 도달하기 위해 대규모 단계를 수행합니다. 복잡한 시스템의 경우 이 옵션을 설정하면 성능이 순간적으로 크게 저하될 수 있습니다.

  + [ ] Pause : 시스템이 화면에서 벗어나면 시뮬레이션을 중단합니다.

  + [ ] Always Simulate : 온스크린 여부와는 상관없이 시스템이 모든 프레임에서 시뮬레이션을 처리합니다. 시뮬레이션 시 명확하게 알아볼 수 있는 불꽃놀이와 같은 일회성 효과에 유용합니다.

- [X] Ring Buffer Mode : 파티클이 Max Particles 수에 도달할 때까지 파티클을 계속 활성화합니다. Max Particles 수에 도달하면 수명이 경과한 파티클을 제거하는 대신 가장 오래된 파티클을 재활용하여 새 파티클을 생성합니다.

  + [ ] Disabled : 시스템이 수명이 경과한 파티클을 제거하도록 Ring Buffer Mode 를 비활성화합니다.

  + [ ] Pause Until Replaced : 수명을 다한 오래된 파티클을 일시정지했다가 Max Particle 한계에 도달하면 시스템에서 재활용하여 새 파티클로 다시 표시되게 합니다.

  + [ ] Loop Until Replaced : 수명을 다한 파티클이 특정한 수명 비율 지점으로 다시 돌아가며, Max Particle 한계에 도달하면 시스템에서 재활용하여 새 파티클로 다시 표시되게 합니다.

# Emission
{: .notice--warning}

이 모듈은 파티클의 생성 속도를 조절하고, 특정 이벤트 또는 타이밍에 따라 파티클을 생성합니다.

- [X] Rate over Time : 초당 생성되는 파티클의 개수를 설정하는 값, 기본값: 10(초당 10개의 파티클 생성).

- [X] Rate over Distance : 파티클 시스템이 이동할 때, 이동한 거리만큼 비례하여 파티클을 생성(플레이어가 달릴 때 먼지가 날리는 효과 등).

- [X] Bursts : 특정한 순간에 한 번에 여러 개의 파티클을 생성하는 기능.(Time = 0, Count = 100 → 시작하자마자 100개의 파티클을 생성)

  + [ ] Time : 언제(몇 초 후)에 버스트를 실행할지 설정

  + [ ] Count : 방출되는 파티클 수를 설정합니다.

  + [ ] Cycles : 버스트를 반복할 횟수를 설정합니다.
  
  + [ ] Interval : 반복되는 경우, 반복 주기 설정
  
  + [ ] Probability : 확률적으로 버스트가 발생하도록 설정합니다. 값을 ’1’로 설정하면 시스템이 100% 파티클을 생성합니다.

# Shape
{: .notice--warning}

- [X] 

# Velocity over Lifetime
{: .notice--warning}

- [X] 

# Limit Velocity over Lifetime
{: .notice--warning}

- [X] 

# Inherit Velocity
{: .notice--warning}

- [X] 

# Lifetime by Emitter Speed
{: .notice--warning}

- [X] 

# Force over Lifetime
{: .notice--warning}

- [X] 

# Color over Lifetime
{: .notice--warning}

- [X] 

# Color by Speed
{: .notice--warning}

- [X] 

# Size over Lifetime
{: .notice--warning}

- [X] 

# Size by Speed
{: .notice--warning}

- [X] 

# Rotation over Lifetime
{: .notice--warning}

- [X] 

# Rotation by Speed
{: .notice--warning}

- [X] 

# External Forces
{: .notice--warning}

- [X] 

# Noise
{: .notice--warning}

- [X] 

# Collision
{: .notice--warning}

- [X] 

# Triggers
{: .notice--warning}

- [X] 

# Sub Emitters
{: .notice--warning}

- [X] 

# Texture Sheet Animation
{: .notice--warning}

- [X] 

# Lights
{: .notice--warning}

- [X] 

# Trails
{: .notice--warning}

- [X] 

# Custom Data
{: .notice--warning}

- [X] 

# Renderer
{: .notice--warning}

- [X] 