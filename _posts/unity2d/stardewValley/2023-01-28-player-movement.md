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

# 2.스크립트
{: .notice--warning .text-center}

```c#
using UnityEngine;

public static class Settings
{
    // Player Movement
    public const float runningSpeed = 5.333f;
    public const float walkingSpeed = 2.666f;
}
```

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