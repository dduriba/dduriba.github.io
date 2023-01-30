---
title:  "3.플레이어 무브먼트"
excerpt: "player movement"
categories: stardewValley
tag: [unity, 2d, stardewValley]
classes: wide
---

# 1.Player 게임오브젝트에 Rigidbody 2D 컴포넌트 추가 및 설정
{: .notice--warning .text-center}

<img src="/img/unity2d/stardewValley/2023-01-28-rigidbody-2d-component.png"/>

[Unity docs Rigidbody2D](https://docs.unity3d.com/kr/2020.3/Manual/class-Rigidbody2D.html)

# 2.스크립트 추가 및 편집
{: .notice--warning .text-center}

<details>
<summary>/Scripts/Misc/Settings.cs 추가</summary>
<div markdown="1">

```c#
using UnityEngine;

public static class Settings
{
    // Player Movement
    public const float runningSpeed = 5.333f;
    public const float walkingSpeed = 2.666f;
}
```

<div class="notice">
플레이어의 뛰는속도, 걷는속도 수치의 값을 담을 변수를 const 로 저장, 전역으로 접근할 수 있게 static class 로 생성
</div>

</div>
</details>

<details>
<summary>/Scripts/Player/Player.cs 편집</summary>
<div markdown="1">

```c#
using UnityEngine;

public class Player : SingletonMonoBehaviour<Player>
{
    // Movement Parameters
    private float xInput;
    private float yInput;

    private Rigidbody2D rigidBody2D;

    private float movementSpeed;

    protected override void Awake()
    {
        base.Awake();

        rigidBody2D = GetComponent<Rigidbody2D>();
    }

    private void Update()
    {
        #region Player Input
        
        PlayerMovementInput();

        PlayerWalkInput();

        #endregion    
    }

    private void FixedUpdate()
    {
        PlayerMovement();
    }

    private void PlayerMovementInput()
    {
        yInput = Input.GetAxisRaw("Vertical");
        xInput = Input.GetAxisRaw("Horizontal");

        if (yInput != 0 && xInput != 0)
        {
            xInput = xInput * 0.71f;
            yInput = yInput * 0.71f;
        }

        if (xInput != 0 || yInput != 0)
            movementSpeed = Settings.runningSpeed;
    }

    private void PlayerWalkInput()
    {
        if (Input.GetKey(KeyCode.LeftShift) || Input.GetKey(KeyCode.RightShift))
            movementSpeed = Settings.walkingSpeed;
        else
            movementSpeed = Settings.runningSpeed;
    }

    private void PlayerMovement()
    {
        Vector2 move = new Vector2(xInput * movementSpeed * Time.deltaTime, yInput * movementSpeed * Time.deltaTime);

        rigidBody2D.MovePosition(rigidBody2D.position + move);
    }
}
```

<div class="notice">
PlayerMovementInput 메소드와 PlayerWalkInput 메소드의 movementSpeed = Settings.runningSpeed; 부분이 겹쳐 한 쪽을 지워도 작동하지만 후에 수정을 대비해 그대로 두거나 PlayerWalkInput 메소드의 중복되는 부분을 삭제
</div>

</div>
</details>
