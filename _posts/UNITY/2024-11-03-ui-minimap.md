---
title:  "미니맵"
categories: Unity
tag: [ui]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# 미니맵
{: .notice--warning .text-center}

매니저(빈 오브젝트)에 추가할 스크립트를 생성

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;

public class MiniMap : MonoBehaviour
{
    [SerializeField] private GameObject _player;
    [SerializeField] private GameObject _enemy;
    [SerializeField] private Image _enemyPOS;
    [SerializeField] private Image _mapPOS;

    // Update is called once per frame
    void Update()
    {
        _mapPOS.rectTransform.localPosition =
            new Vector3(-1 * _player.transform.position.x,
                        -1 * _player.transform.position.z,
                        0);
        _enemyPOS.rectTransform.localPosition = 
            new Vector3(_enemy.transform.position.x,
                        _enemy.transform.position.z,
                        0);
    }
}
```

```mathematica
계층 구조
├── Manager(MiniMap.cs을 컴포넌트로 가지는 빈 오브젝트)
├── Terrain(맵)
├── Player(MiniMap._player에 연결할 플레이어 오브젝트)
├── Enemy(MiniMap._enemy에 연결할 플레이어 오브젝트)
├── Canvas
│   └── Map(UI를 우측 상단에 고정시킬 Rect Transform만 가지는 빈 오브젝트)
│       ├── ImageMask(Mask 컴포넌트를 가져 맵을 플레이어 중심으로 사각으로 자를 오브젝트)
│       │   └── ImageMap(MiniMap._mapPos에 연결할 맵 이미지를 가질 오브젝트로 맵의 크기에 따라 미니맵의 크기도 달라진다(맵 Scale X 20, Z 20 = 미니맵 Width 200, Height 200))
│       │       └── EnemyMap(MiniMap._enemyPos에 연결할 적의 위치를 나타낼 오브젝트)
│       └── PlayerMap(Player의 위치를 보여줄 Image로 Rect Transform의 중심으로 설정하기 때문에 플레이어는 항상 맵의 중앙에 위치하게 된다)
```
