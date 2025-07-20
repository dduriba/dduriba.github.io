---
title: "Particle System"
categories: my-unity-docu
tag: [컴포넌트]
excerpt: "Particle System Modules"
---




<span style="color:gray">unity version 2022.3.7f1</span>




# 📌 Main
{: .notice}

<span class="li-1">Duration : 파티클 시스템 생성이 지속되는 시간</span>

<span class="li-1">Looping : Duration이 끝나는 시점을 기준으로 자동으로 Duration을 반복합니다.</span>

<span class="li-2">Prewarm : 처음 실행될 때 이미 최대로 퍼져있는 상태로 시작합니다.(Looping 이 활성화되었을 때에만 작동합니다.)</span>

<span class="li-1">Start Delay : 파티클이 생성되기 전에 대기하는 시간</span>

<span class="li-1">Start Lifetime : 개별 파티클이 살아 있는 시간(초)입니다.</span>

<span class="li-1">Start Speed : 파티클이 처음 생성될 때의 속도를 결정합니다. 0으로 설정하면 정지된 상태로 생성됩니다.</span>

<span class="li-1">3D Start Size : 활성화하면 파티클이 생성될 때의 크기를 각각의 축마다 개별로 설정할 수 있습니다.</span>

<span class="li-1">Start Size : 각 파티클의 초기 크기를 설정합니다.</span>

<span class="li-1">3D Start Rotation : 활성화하면 파티클이 생성될 때의 회전 값을 각각의 축마다 개별로 설정할 수 있습니다.</span>

<span class="li-1">Start Rotation : 각 파티클의 초기 회전 값을 설정합니다.</span>

<span class="li-1">Flip Rotation : 각 파티클의 회전을 확률적으로 반전시킬 수 있습니다.(0부터 1사이의 값으로, 0이면 기본 방향, 1이면 모든 파티클이 180도 반전됩니다. 그 사이의 값은 확률에 따라 각각의 파티클이 기본 방향, 180도 방향 중 결정됩니다.)</span>

<span class="li-1">Start Color : 각 파티클의 초기 컬러를 설정합니다.</span>

<span class="li-1">Gravity Source : 3D Physics, 2D Physics 중 선택합니다.</span>

<span class="li-1">Gravity Modifier : Physics Manager에서 설정된 중력 값을 스케일합니다. 이 값을 0으로 하면 중력 효과가 해제됩니다. 양수면 중력이 아래로 작용, 음수면 위쪽으로 작용합니다.</span>

<span class="li-1">Simulation Space : 파티클의 움직임이 어느 공간을 기준으로 계산될지 설정합니다.</span>

<span class="li-2">Local : 파티클이 부모 오브젝트의 로컬 공간에서 애니메이션화되도록 합니다.(부모 오브젝트와 함께 이동)</span>

<span class="li-2">World : 파티클이 월드 공간에서 애니메이션화되도록 합니다.</span>

<span class="li-2">Custom : 기준이 될 대상 오브젝트를 직접 지정해 파티클이 대상 오브젝트에 대해 상대적으로 애니메이션화(선택한 커스텀 오브젝트와 함께 이동)되도록 합니다.</span>

<span class="li-1">Simulation Speed : 파티클 시스템의 전체적인 속도를 조절합니다.(값이 1보다 크면 빠르게 실행, 1보다 작으면 느리게 실행됩니다.)</span>

<span class="li-1">Delta Time : 파티클의 움직임을 시간에 따라 어떻게 계산할지를 설정합니다.</span>

<span class="li-2">Scaled : Time.timeScale의 영향을 받습니다. (예: 게임이 일시 정지되면 파티클도 정지)</span>

<span class="li-2">Unscaled : Time.timeScale에 관계없이 항상 동일한 속도로 실행됩니다.</span>

<span class="li-1">Scaling Mode : 부모 오브젝트의 크기 조절이 파티클에 어떻게 적용될지를 설정합니다.</span>

<span class="li-2">Hierarchy : 부모와 그 부모로부터, 계층 관계를 통해 곱해진 트랜스폼 최종 스케일이 파티클 크기에 영향을 주게 됩니다.</span>

<span class="li-2">Local : 해당 파티클 시스템이 위치한 게임 오브젝트의 트랜스폼의 스케일이 파티클 크기에 영향을 주게 됩니다.</span>

<span class="li-2">Shape : Shape 모듈에서 설정한 스케일이 파티클의 크기에 영향을 주게 됩니다.</span>

<span class="li-1">Play On Awake : 활성화하면 파티클 시스템이 씬에서 활성화될 때 자동으로 실행됩니다. 비활성화하면 Play()를 호출해야 실행됩니다.</span>

<span class="li-1">Emitter Velocity Mode : 파티클이 부모 오브젝트의 속도를 어떻게 계승할지 선택할 수 있습니다.(Rigidbody 컴포넌트가 없는 경우 시스템은 기본적으로 Transform 컴포넌트를 사용합니다.)</span>

<span class="li-2">Transform : 부모 오브젝트의 Transform 이동 속도를 반영</span>

<span class="li-2">Rigidbody : 부모 오브젝트의 Rigidbody 속도를 반영</span>

<span class="li-2">Custom : 부모 오브젝트로부터 영향을 받지 않고, 직접 속도를 설정할 수 있습니다.</span>

<span class="li-1">Max Particles : 동시에 존재할 수 있는 파티클의 최대 개수입니다.</span>

<span class="li-1">Auto Random Seed : 활성화하면 Unity가 랜덤 시드 값을 설정하여 매번 다른 결과를 생성합니다. 비활성화하면 직접 시드 값을 설정하여 동일한 랜덤 결과를 유지할 수 있습니다.</span>

<span class="li-1">Stop Action : 시스템에 속한 모든 파티클이 완료되어 시스템이 중지되었을 때 특정 동작을 수행하도록 설정합니다.(시스템의 파티클이 모두 소멸되고 파티클의 수명이 지속 시간을 초과하면 시스템이 중지된 것으로 간주됩니다. 루프를 반복하는 시스템에서는 스크립트를 통해 중지되었을 때 중지된 것으로 간주됩니다.)</span>

<span class="li-2">None</span>

<span class="li-2">Disable : 게임 오브젝트를 비활성화합니다.</span>

<span class="li-2">Destroy : 게임 오브젝트를 파괴합니다.</span>

<span class="li-2">Callback : 해당 게임 오브젝트에 존재하는 OnParticleSystemStopped() 메서드를 호출합니다.</span>

<span class="li-1">Culling Mode : 파티클 시스템이 화면에서 벗어날 때 동작을 결정합니다.</span>

<span class="li-2">Automatic : Unity가 자동으로 적절한 컬링 방식을 선택합니다.(Looping 일 때는 Pause, 기타 모든 시스템은 Always Simulate를 사용합니다.)</span>

<span class="li-2">Pause and Catch-up : 시스템이 화면에서 벗어나면 시뮬레이션을 중단하고, 다시 포착될 경우 시뮬레이션이 일시정지되지 않았다면 도달했을 포인트부터 재생합니다.</span>

<span class="li-2">Pause : 시스템이 화면에서 벗어나면 시뮬레이션을 중단하고 다시 포착될 경우 중단된 곳부터 이어서 재생합니다.</span>

<span class="li-2">Always Simulate : 시스템이 화면에서 벗어나도 계속해서 재생합니다.</span>

<span class="li-1">Ring Buffer Mode : 파티클이 Max Particles 수에 도달했을 때 파티클의 수명에 따라 파티클을 재활용하여 새 파티클을 생성할 수 있습니다.</span>

<span class="li-2">Disabled : Max Particle 수에 도달하면 초과해서 새 파티클을 생성하지 않고, 파티클은 수명이 다 됐을 때 제거합니다.</span>

<span class="li-2">Pause Until Replaced : Max Particle 수에 도달하고 새 파티클이 생성될 때, 수명이 제일 오래된 파티클을 바로 일시정지하고 재활용합니다.</span>

<span class="li-2">Loop Until Replaced : Max Particle 수에 상관없이 일단 새 파티클이 생성되며, 새 파티클이 필요할 때 Max Particle 수에 도달하고 수명이 다 한 파티클이 있을 경우에만 재활용합니다. 이때 재활용되지 않은 파티클은 수명이 다해도 사라지지 않고 계속해서 반복됨에 주의해야 합니다.</span>




# 📌 Emission
{: .notice}

📢 이 모듈은 파티클의 생성 속도를 조절하고, 특정 타이밍에 파티클이 생성되게 할 수 있습니다. 세 옵션은 각자 별개로 동시에 사용할 수 있습니다.

<span class="li-1">Rate over Time : 초당 생성되는 파티클의 개수를 설정합니다.</span>

<span class="li-1">Rate over Distance : 파티클 시스템의 게임 오브젝트가 이동한 거리에 비례하여 파티클을 생성합니다.</span>

<span class="li-1">Bursts : 한 순간에 다량의 파티클을 생성할 수 있습니다.</span>

<span class="li-2">Time : Duration 동안에 버스트의 초당 Stary Delay를 설정합니다.</span>

<span class="li-2">Count : 한순간에 버스트될 파티클의 개수를 설정합니다.</span>

<span class="li-2">Cycles : Duration 동안에 버스트를 반복할 횟수를 설정합니다.</span>
  
<span class="li-2">Interval : Cycles가 1이 아닌 2 이상이거나 Infinite인 경우 반복 주기를 초 단위로 설정합니다.</span>
  
<span class="li-2">Probability : 버스트가 확률에 따라 발생하도록 설정합니다.(값 "1" = 100% 확률)</span>




# 🔝 Shape
{: .notice}

📢 이 모듈은 파티클이 방출되는 모양, 위치, 방향, 범위를 지정합니다.</span>

<span class="li-1">Shape : 파티클이 방출되는 모양을 지정합니다.(모양에 따라 파티클이 방출되는 Direction, Position이 달라집니다.)</span>

<span class="li-2">Sphere(구), Hemisphere(반구), Cone(원뿔), Donut(도넛), Box(박스)</span>

<span class="li-2">Mesh : 3D 모델(Mesh)의 표면에서 파티클을 방출할 수 있습니다.</span>

<span class="li-2">Mesh Renderer : 특정한 Mesh Renderer를 가진 오브젝트에서 파티클을 방출할 수 있습니다. Mesh와 비슷하지만, 게임 오브젝트에 연결된 Renderer를 참조합니다.</span>
  
<span class="li-2">Skinned Mesh Renderer : 애니메이션이 적용된 캐릭터의 Skinned Mesh에서 파티클을 방출할 수 있습니다.</span>

<span class="li-2">Sprite, Sprite Renderer : Sprite 이미지, Sprite Renderer에서 파티클을 방출할 수 있습니다. 주로 2D 게임에서 사용됩니다.</span>

<span class="li-2">Circle(원, 2D 평면), Edge(직선), Rectangle(사각형, 2D 평면)</span>

<span class="li-1">Texture : 지정한 텍스처를 기반으로 파티클을 특정한 패턴으로 방출되게 할 수 있습니다. 적절한 텍스처 이미지를 사용하면 메시 기반의 방출보다 더 가벼우면서 복잡한 방출 패턴을 만들 수 있습니다.</span>

<span class="li-1">Position, Rotation, Scale : Shape의 위치, 방향, 영역을 조절합니다.(트랜스폼의 기능과 일치하지만 트랜스폼은 게임 오브젝트에 적용되는 부분에 차이가 있습니다.)</span>

<span class="li-1">Align To Direction : 방출된 파티클이 방출된 방향으로 정렬되어 항상 이동하는 방향을 바라보도록 설정합니다.(파티클이 빌보드일 경우 빌보드를 무시합니다.)</span>

<span class="li-1">Randomize Direction : 파티클의 이동 방향이 무작위가 되도록 블렌드합니다.(0부터 1까지의 값으로, 0으로 설정하면 아무런 영향도 미치지 않고, 1로 설정하면 파티클의 이동 방향이 완전히 무작위로 변경됩니다.)</span>

<span class="li-1">Spherize Direction : 파티클의 이동 방향이 구체 방향이 되도록 블렌드합니다.(0부터 1까지의 값으로, 0으로 설정하면 아무런 영향도 미치지 않고, 1로 설정하면 파티클의 이동 방향이 중앙을 기준으로 방사형이 됩니다.)</span>

<span class="li-1">Randomzie Position : 파티클의 방출 위치에 무작위성을 추가합니다.(0으로 설정하면 아무런 영향도 미치지 않고, 0보다 높은 값으로 설정하면 설정한 값 만큼 파티클 생성 위치에 무작위성이 적용됩니다.)</span>




# 🚀 Velocity over Lifetime
{: .notice}

📢 이 모듈은 파티클에 선형 속도를 추가할 수 있고 질량중심을 설정해 파티클을 공전시킬 수도 있고 빨아들이거나 밀어낼 수도 있습니다.

<span class="li-1">Linear X, Y, Z : 파티클의 선형 속도를 각 축마다 설정합니다.</span>

<span class="li-2">Space : Linear X, Y, Z 프로퍼티가 Local, World 중 적용될 공간을 설정합니다.</span>

<span class="li-1">Offset X, Y, Z : Orbital X, Y, Z, Radial 프로퍼티를 사용할 질량중심의 위치를 설정합니다.</span>

<span class="li-2">Orbital X, Y, Z : 파티클이 생성된 지점부터 Offset X, Y, Z를 중심으로 두고 각 축마다 공전하게 될 속도를 설정합니다.</span>

<span class="li-2">Radial : Offset X, Y, Z를 중심으로 파티클을 밀어내거나 빨아들일 만큼 값(속도)을 설정할 수 있습니다. 음수로 두면 파티클을 빨아들이고 양수로 두면 파티클을 밀어냅니다.</span>

<span class="li-1">Speed Modifier : 파티클의 속도 배율을 설정합니다.</span>




# 🔝 Limit Velocity over Lifetime
{: .notice}

📢 이 모듈은 파티클의 속도를 제한하고 파티클에 항력을 설정할 수 있습니다.

<span class="li-1">Separate Axes : Speed 프로퍼티를 축마다 별도로 설정합니다.</span>

<span class="li-2">Space : Speed 프로퍼티가 Local, World 중 적용될 공간을 설정합니다.</span>

<span class="li-1">Speed : 파티클의 최대 제한 속도를 설정합니다.</span>

<span class="li-2">Dampen : 파티클이 Speed 값을 초과할 때 감소되는 속도의 비율을 설정합니다.(0부터 1까지의 값으로, 1로 둘 경우 파티클의 최대 속도는 항상 Speed 값을 가지게 됩니다.)</span>

<span class="li-1">Drag : 파티클 속도에 항력을 설정할 수 있습니다.</span>

<span class="li-2">Multiply by Size : 활성화하면 파티클의 크기에 따라 항력의 영향을 더 많이 받습니다.</span>

<span class="li-2">Multiply by Velocity : 활성화하면 파티클의 속도에 따라 항력의 영향을 더 많이 받습니다.</span>




# 🚧🛠️🚧 Inherit Velocity 🚧🛠️🚧
{: .notice}




# 📝 Lifetime by Emitter Speed
{: .notice}

<span class="li-1">Multiplier : Constant 모드로 둘 경우 방출기의 속도에 상관없이 설정한 값으로 수명 주기의 배율을 설정합니다.(값이 0.1일 경우 기존 수명 주기 대비 10%, 3일 경우는 기존 수명 주기 대비 세배가 됩니다.) Curve 모드로 둘 경우 Speed Range를 기준으로 설정한 값에 따라 수명 주기의 배율을 설정합니다.(Curve 모드일 때 Y 축의 수명 주기 배율의 최댓값은 Constant 모드의 값으로 지정할 수 있습니다.)</span>

<span class="li-2">Speed Range : Multiplier 프로퍼티의 X 축인 Min-Max Normalization될 범위(Min, Max)를 설정합니다. 범위를 벗어난 값은 Min, Max 값에 해당됩니다. Multiplier 프로퍼티의 설정이 Curve 모드로 되어있을 때 적용됩니다.</span>




# 🔝 Force over Lifetime
{: .notice}

📢 이 모듈은 파티클에 힘을 설정합니다. 파티클에 중력을 받는 환경을 만드는 데 사용할 수 있습니다.

<span class="li-1">X, Y, Z(Force) : 파티클에 각 축마다 힘을 설정합니다.</span>

<span class="li-2">Space : 각 축마다 설정된 Force가 Local, World 중 적용될 공간을 설정합니다.</span>

<span class="li-2">Randomize : 활성화할 경우 Force에 설정된 값을 매 프레임마다 갱신합니다. (Force에 설정된 값이 랜덤일 때 활성화할 수 있습니다.)</span>




# 🔝 Color over Lifetime
{: .notice}

📢 이 모듈은 퇴색되거나 소멸되는 파티클(불꽃, 연기, 폭죽 등)에 사용할 수 있습니다.

<span class="li-1">Color : 수명 주기 동안 변화하는 파티클의 컬러 그레디언트를 설정합니다. 그레디언트 바의 좌측 끝은 파티클 수명의 시작을 나타내며 우측 끝은 파티클 수명이 끝났음을 나타냅니다. 그레디언트 바의 상단에서 알파 값(A), 하단에서 컬러(RGB)를 설정할 수 있습니다.</span>




# 🔝 Color by Speed
{: .notice}

📢 이 모듈은 빠르게 움직일수록 색이 변하는 파티클(연기 등)에 사용할 수 있습니다.

<span class="li-1">Color : 속도에 따라 변화하는 파티클의 컬러 그레디언트를 설정합니다. 그레디언트 바의 좌측 끝은 파티클 수명의 시작을 나타내며 우측 끝은 파티클 수명이 끝났음을 나타냅니다. 그레디언트 바의 상단에서 알파 값(A), 하단에서 컬러(RGB)를 설정할 수 있습니다.</span>

<span class="li-2">Speed Range : 컬러 그레디언트가 매핑될 속도 범위의 최솟값 및 최댓값을 설정합니다.(범위 밖의 속도는 그레디언트의 끝에 매핑됩니다.)</span>




# 🔝 Size over Lifetime
{: .notice}

<span class="li-1">Size : 파티클의 수명 주기에 따라 파티클의 크기를 설정합니다.</span>

<span class="li-2">Separate Axes : Size 프로퍼티를 각 축마다 설정합니다.</span>




# 📝 Size by Speed
{: .notice}

<span class="li-1">Size : 파티클의 속도에 따라 파티클의 크기를 설정합니다.</span>

<span class="li-2">Separate Axes : Size 프로퍼티를 각 축마다 설정합니다.</span>

<span class="li-2">Speed Range : Size 프로퍼티의 X 축인 Min-Max Normalization될 범위(Min, Max)를 설정합니다. 범위를 벗어난 값은 Min, Max 값에 해당됩니다.</span>




# 📝 Rotation over Lifetime
{: .notice}

<span class="li-1">Angular Velocity : 파티클의 수명 주기에 따라 파티클을 회전시키고 회전 속도를 설정합니다.</span>

<span class="li-2">Separate Axes : Angular Velocity 프로퍼티를 각 축마다 설정합니다.</span>




# 📝 Rotation by Speed
{: .notice}

<span class="li-1">Angular Velocity : Constant 모드로 둘 경우 파티클의 속도에 상관없이 설정한 값으로 회전합니다. Curve 모드로 둘 경우 Speed Range를 기준으로 설정한 값에 따라 회전합니다.</span>

<span class="li-2">Separate Axes : Angular Velocity 프로퍼티를 각 축마다 설정합니다.</span>

<span class="li-2">Speed Range : Angular Velocity 프로퍼티의 X 축인 Min-Max Normalization될 범위(Min, Max)를 설정합니다. 범위를 벗어난 값은 Min, Max 값에 해당됩니다. Angular Velocity 프로퍼티의 설정이 Curve 모드로 되어있을 때 활성화할 수 있습니다.</span>




# 🚧🛠️🚧 External Forces 🚧🛠️🚧
{: .notice}




# 🔥 Noise
{: .notice}

📢 이 모듈은 파티클의 위치, 회전, 크기에 대해 불규칙적으로 부드럽거나 역동적인 변화(도깨비불 등)를 줄 수 있습니다.

<span class="li-1">Separate Axes : 활성화하면 Strength 프로퍼티와 Remap 프로퍼티를 각 축마다 별도로 제어합니다.</span>

<span class="li-1">Strength : 노이즈 효과의 강도를 설정합니다. 값이 0에서 멀어질수록 파티클이 더 빠르고 멀리 이동합니다.</span>

<span class="li-1">Frequency : 노이즈 효과의 빈도를 설정합니다. 값이 0보다 커질수록 파티클의 노이즈 효과 빈도 수가 증가합니다.</span>

<span class="li-1">Scroll Speed : 노이즈 맵을 스크롤 해 노이즈 효과가 더 불규칙하게 일어나게 합니다. 값이 0에서 멀어질수록 스크롤 속도가 빨라집니다.</span>

<span class="li-1">Damping : 활성화하면 Strength가 Frequency에 비례합니다.</span>

<span class="li-1">Octaves : 노이즈 맵의 패턴을 더 복잡하게 설정할 수 있습니다. 1보다 높은 값을 설정하면 노이즈의 패턴이 더 다채로워지지만 성능 비용이 증가합니다.</span>

<span class="li-2">Octave Multiplier</span>

<span class="li-2">Octave Scale</span>

<span class="li-1">Quality : 노이즈 맵의 품질을 결정합니다. 높은 품질일수록 더 부드럽고 정교한 노이즈를 생성하지만 연산 비용이 증가합니다.</span>

<span class="li-1">Remap : 최종 노이즈 맵에서 원하는 범위로 노이즈를 다시 매핑할 수 있습니다.</span>

<span class="li-2">Remap Curve : 그래프를 통해 노이즈를 다시 매핑합니다. 리맵 전의 최종 노이즈 맵의 값은 X=Y입니다. Y 축의 값이 낮아질수록 어두운 영역, 높아질수록 밝은 영역으로 노이즈 맵에 프리뷰로 나타나게 됩니다.</span>

<span class="li-1">Position Amount : 노이즈가 파티클 위치에 영향을 주는 정도를 설정합니다.</span>

<span class="li-1">Rotation Amount : 노이즈가 파티클 회전에 영향을 주는 정도를 설정합니다.</span>

<span class="li-1">Size Amount : 노이즈가 파티클 크기에 영향을 주는 정도를 설정합니다.</span>




# 🚧🛠️🚧 Collision 🚧🛠️🚧
{: .notice}




# 🚧🛠️🚧 Triggers 🚧🛠️🚧
{: .notice}




# 🎭 Sub Emitters
{: .notice}

<span class="li-1">Event Condition</span>

<span class="li-2">Birth</span>

<span class="li-2">Collision</span>

<span class="li-2">Death</span>

<span class="li-2">Trigger</span>

<span class="li-2">Manual : 스크립트로 트리거</span>

<span class="li-1">Inherit</span>

<span class="li-2">Nothing</span>

<span class="li-2">Everything</span>

<span class="li-2">Color</span>

<span class="li-2">Size</span>

<span class="li-2">Rotation</span>

<span class="li-2">Lifetime</span>

<span class="li-2">Duration</span>

<span class="li-1">Emit Probability : 각 파티클이 서브 이미터를 가질 확률을 설정합니다.(0부터 1사이의 값으로, 0.5는 50% 확률로 파티클이 방출될 때 해당 파티클이 서브 이미터를 가집니다.)</span>




# 🔝 Texture Sheet Animation
{: .notice}

<span class="li-1">Mode</span>

<span class="li-2">Grid : 그리드 형태로 나누어진 텍스처가 적용된 머티리얼을 사용합니다.(Renderer Module에서 설정된 머티리얼을 사용합니다.)</span>

<span class="li-2">Sprites : 스프라이트 시트의 필요한 스프라이트만 추가해 사용합니다.</span>

<span class="li-1">Time Mode</span>

<span class="li-2">Lifetime : 파티클의 한 번의 수명주기에 애니메이션 과정을 몇 번 진행할지 설정합니다.</span>

<span class="li-2">Speed</span>

<span class="li-2">FPS : FPS를 지정해 고정된 속도로 애니메이션을 진행합니다.</span>

<span class="li-1">Start Frame : 애니메이션을 특정 프레임부터 시작하게 설정할 수 있습니다. 랜덤 프레임부터 시작하게 해 더 자연스러운 환경을 만들 수도 있습니다.</span>

<span class="li-1">Affected UV Channels : 애니메이션에 적용할 UV 채널을 선택합니다.</span>

<span class="li-2">: Nothing</span>
  
<span class="li-2">: Everything</span>
  
<span class="li-2">: UV0</span>
  
<span class="li-2">: UV1</span>
  
<span class="li-2">: UV2</span>
  
<span class="li-2">: UV3</span>




# 💡 Lights
{: .notice}

<span class="li-1">Light : 라이트 오브젝트(프리팹)를 할당합니다.</span>

<span class="li-1">Ratio : 전체 파티클 중 Light를 가질 파티클의 비율을 설정합니다.(0부터 1까지의 값으로, 0.5로 둘 경우 50%로 한번은 라이트 파티클이 방출되고 그다음 차례의 파티클엔 라이트가 없는 파티클이 방출됩니다.)</span>

<span class="li-1">Random Distribution : 활성화하면 Ratio 설정의 비율을 확률로 설정합니다.</span>

<span class="li-1">Use Particle Color : 라이트의 색을 파티클과 동일한 색으로 사용합니다.</span>

<span class="li-1">Size Affects Range : 파티클의 크기에 따라 라이트의 범위에 영향을 주도록 설정합니다.</span>

<span class="li-1">Alhpa Affects Intensity : 파티클의 알파값에 따라 라이트의 세기에 영향을 주도록 설정합니다.</span>

<span class="li-1">Range Multiplier : 라이트의 범위 배율을 조절합니다.</span>

<span class="li-1">Intensity Multiplier : 라이트의 세기 배율을 조절합니다.</span>

<span class="li-1">Maximum Lights : 동시에 존재할 수 있는 라이트 파티클의 개수를 제한합니다.</span>




# 🚧🛠️🚧 Trails 🚧🛠️🚧
{: .notice}




# 🚧🛠️🚧 Custom Data 🚧🛠️🚧
{: .notice}




# 📌 Renderer
{: .notice}

📢 이 모듈은 파티클의 이미지를 결정, 그림자를 생성하고 조절하거나 다른 오브젝트의 그림자에 의해 영향을 받을지 설정합니다. 또한 파티클에 모션 블러를 적용할 수 있고, 라이트 프로브나 리플렉션 프로브로부터 영향을 받을지를 결정합니다. 2D 환경에서 파티클의 정렬을 결정할 수도 있습니다.

<span class="li-1">Render Mode : 파티클이 화면에 그려지는 방식을 설정합니다.</span>

<span class="li-2">Billboard : 파티클이 항상 카메라를 향하도록 렌더링</span>

<span class="li-2">Stretch Billboard : 파티클이 이동 방향으로 길게 늘어나며 렌더링</span>

<span class="li-2">Horizontal Billboard : 파티클이 X-Z 평면(지면)에 평행한 상태로 렌더링</span>

<span class="li-2">Vertical Billboard : 파티클이 Y축을 기준으로 세워진 상태로 렌더링</span>

<span class="li-2">Mesh : 3D Mesh를 파티클로 렌더링</span>

<span class="li-2">None : 파티클을 렌더링하지 않음</span>

<span class="li-1">Material</span>

<span class="li-1">Sort Mode</span>

<span class="li-1">Sorting Fudge</span>

<span class="li-1">Flip</span>

<span class="li-1">Pivot : 각 파티클의 피벗으로부터 오프셋 값을 설정합니다.</span>

<span class="li-1">Visualize Pivot : Scene 뷰에서 각 파티클의 피벗 위치를 작은 십자 형태로 시각화해서 보여줍니다.</span>

<span class="li-1">Masking</span>

<span class="li-1">Apply Active Color Space</span>

<span class="li-1">Custom Vertex Streams</span>

<span class="li-1">Cast Shadows : 파티클이 그림자를 생성할지 결정합니다.</span>

<span class="li-2">Off</span>

<span class="li-2">On</span>

<span class="li-2">Two Sided : 앞면과 뒷면 모두 그림자를 생성</span>

<span class="li-2">Shadows Only : 파티클은 숨긴 채 그림자만 생성</span>

<span class="li-1">Receive Shadows : 파티클이 다른 오브젝트의 그림자에 영향을 받을지 설정합니다.</span>

<span class="li-1">Shadow Bias : 그림자가 얼마나 정확하게 생성될지 조정하는 값입니다. 낮은 값일수록 그림자가 오브젝트 가까이에 생기고, 높은 값일수록 그림자가 멀리 생깁니다.(그림자가 너무 가까우면 Shadow Acne. 그림자가 깨지는 현상이 발생할 수 있고, 너무 멀리 떨어지면 Peter Panning. 그림자가 떠 보이는 현상이 생길 수 있습니다.)</span>

<span class="li-1">Motion Vectors : 파티클에 모션 블러를 적용합니다.</span>

<span class="li-2">Camera Motion Only : 카메라가 움직일 때만 모션 블러 적용</span>

<span class="li-2">Per Object Motion : 개별 파티클 자체의 속도에 따라 모션 블러 적용</span>

<span class="li-2">Force No Motion : 모션 벡터를 사용하지 않음</span>

<span class="li-1">Sorting Layer ID : 2D 환경에서 파티클의 Sorting Layer를 결정합니다.</span>

<span class="li-1">Order in Layer : 같은 Sorting Layer 내에서의 순서를 결정합니다.</span>

<span class="li-1">Light Probes : 파티클이 라이트 프로브로부터 영향을 받을지 결정합니다.</span>

<span class="li-2">Off</span>

<span class="li-2">Blend Probes : 주변 라이트 프로브 값을 블렌딩해 조명 변화를 적용합니다.</span>

<span class="li-2">Use Proxy volume : 더 정교한 조명 정보를 적용하는 Light Probe Proxy Volume을 사용합니다.</span>

<span class="li-2">Custom Provided : 스크립트에서 직접 라이트 프로브 데이터를 제공합니다.</span>

<span class="li-1">Reflection Probes : 파티클이 반사 프로브로부터 영향을 받을지 결정합니다.</span>

<span class="li-2">Off</span>

<span class="li-2">Blend Probes : 여러 개의 반사 프로브를 블렌딩해 반사 효과를 적용합니다.</span>

<span class="li-2">Blend Probes And Skybox : 반사 프로브와 스카이박스 반사 효과를 함께 적용합니다.</span>

<span class="li-2">Simple : 가장 가까운 반사 프로브의 값을 적용합니다.</span>