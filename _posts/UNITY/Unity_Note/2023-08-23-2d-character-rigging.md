---
title:  "2D Character Rigging"
excerpt: "Unity 2D Character Rigging"
categories: Unity_Note
tag: [2D Rigging]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# - Package 다운로드
{: .notice--warning .text-center}

Package Manager
- 2D Animation
- 2D PSD Importer

# - .psb 파일 생성
{: .notice--warning .text-center}

포토샵으로 캐릭터를 구성해 .psb 확장자로 저장 후 유니티에 Import

- 레이어 = 신체 부위
- 레이어 순서 = 카메라 기준 신체 depth

<img src="/img/Unity/Unity_Note/2023_08_23_create_psb_file.png"/>

# - Rigging
{: .notice--warning .text-center}

## = Create Bone
{: .notice--success .text-center}

1. PSB 파일의 Sprite Editor를 열어 Skinning Editor로 변경
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