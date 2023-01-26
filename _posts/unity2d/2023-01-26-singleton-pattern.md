---
title:  "싱글톤 디자인 패턴"
excerpt: "singleton design pattern for unity"
categories: unity2d
tag: [unity, singleton, designPattern]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# 1.싱글톤 스크립트 생성
{: .notice--warning .text-center}

```c#
using UnityEngine;

public abstract class SingletonMonoBehaviour<T> : MonoBehaviour where T : MonoBehaviour
{
    private static T instance;

    public static T Instance { get { return instance; } }

    protected virtual void Awake()
    {
        if (instance == null) instance = this as T;
        else Destroy(gameObject);
    }
}
```

# 2.싱글톤을 적용시킬 스크립트 생성
{: .notice--warning .text-center}

```c#
using UnityEngine;

public class Player : SingletonMonoBehaviour<Player>
{
    protected override void Awake()
    {
        base.Awake();
    }
}
```

# 3.게임 오브젝트에 스크립트 추가
{: .notice--warning .text-center}

<img src="/img/2023-01-26-singleton-pattern.png"/>