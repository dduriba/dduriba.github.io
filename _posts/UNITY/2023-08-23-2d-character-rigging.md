---
title:  "2D Character Rigging"
excerpt: "Unity 2D Character Rigging"
categories: Unity
tag: [2D Rigging]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# - .psb 파일 생성
{: .notice--warning .text-center}

포토샵으로 신체 부위를 조합한 캐릭터를 만든 뒤 .psb 확장자로 저장 후 유니티에 Import

- 레이어 = 신체 부위
- 레이어 순서 = 카메라 기준 신체 depth

<img src="/img/Unity/Unity_Note/2023_08_23_create_psb_file.png"/>

# - Package 인스톨
{: .notice--warning .text-center}

Package Manager
- 2D Animation
- 2D PSD Importer

# - Rigging
{: .notice--warning .text-center}

## = Create Bone
{: .notice--success .text-center}

1. .psb 파일의 Sprite Editor를 열어 Skinning Editor로 변경
2. Create Bone(우클릭으로 상속관계를 끊고 본을 선택해 부모 선택)

<img src="/img/Unity/Unity_Note/2023_08_23_create_bone.png"/>

## = Edit Bone
{: .notice--success .text-center}

1. Bone Name, Position, Rotation, (Depth) 설정 (Visibility 창으로 더 원활한 작업 가능)

<img src="/img/Unity/Unity_Note/2023_08_23_edit_bone.png"/>

## = Bone(Sprite) Influence
{: .notice--success .text-center}

만든 Bone에 Sprite를 연결

<img src="/img/Unity/Unity_Note/2023_08_23_bone_influence.png"/>

## = Auto Weights
{: .notice--success .text-center}

Bone을 연결한 모든 Sprite를 Generate Weights

<img src="/img/Unity/Unity_Note/2023_08_23_auto_weights.png"/>

# - 완성한 .psb 파일 기반 Prefab Variant 생성 후 Hierachy(World) 에 생성
{: .notice--warning .text-center}

<img src="/img/Unity/Unity_Note/2023_08_23_prefab_variant.png"/>

# - IK Manager 2D 컴포넌트를 추가해 IK Solvers::Limb 추가
{: .notice--warning .text-center}

1. 프리팹(최상위 게임오브젝트)에 IK Manager 2D (Script) 컴포넌트 추가
2. IK Solvers 중 Limb 추가
3. 생성된 LimbSolver2D 게임오브젝트의 Limb Solver 2D (Script) 컴포넌트 중 Effector 부분에 손 부분 Bone 게임오브젝트 연결 후 Create Target
4. 남은 다른 손과 두 발에 대해서도 Target을 만들어 준다.
5. Target 게임오브젝트의 Position을 움직여보고 팔꿈치나 무릎관절이 부자연스러울 경우 해당 Solver의 Limb Solver 2D 컴포넌트에서 Flip=true

- 프리팹에 빈 게임오브젝트를 만들어 Solver들을 차일드화 해 정리
- 타겟이 제대로 따라오기 위해 발 타겟 게임오브젝트는 프리팹 하위에 두고, 손 타겟 게임오브젝트는 Upper Torso Bone 하위에 둠
- 프리팹 Overrides->Apply All

<img src="/img/Unity/Unity_Note/2023_08_23_solvers.png"/>

# - Animation 추가
{: .notice--warning .text-center}

1. Animation clip 생성 (Hierachy의 Prafab을 선택하고 Animation 창에서 Create, Animator는 자동 생성됨)
2. keyframe recording mode를 Enable해 Bone과 Target을 움직여 Transform 값 기록을 통해 각 frame을 만들어 전체 애니메이션 생성

- 마지막 keyframe에 첫 keyframe을 Copy&Paste
- Default Pose keyframe은 프리팹의 IK Manager 2D (Script) 컴포넌트의 Restore Default Pose를 통해 획득

<img src="/img/Unity/Unity_Note/2023_08_23_animation.png"/>