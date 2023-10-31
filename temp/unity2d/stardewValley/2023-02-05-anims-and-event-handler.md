---
title:  "4.애니메이션/애니메이터와 이벤트 핸들러"
excerpt: "animation, animator and event handler"
categories: stardewValley
tag: [unity, 2d, stardewValley]
classes: wide
---

# 1.Animation (Clip), Animator Controller 생성
{: .notice--warning .text-center}

<img src="/img/unity2d/stardewValley/2023-02-05-create-clips-and-controller.png" style="zoom:50%;"/>

# 2.Animator Contoller 설정 (Animator window)
{: .notice--warning .text-center}

## 2-1 Parameter 추가
{: .notice--success}

<img src="/img/unity2d/stardewValley/2023-02-05-animator-parameters.png" style="zoom:50%;"/>

## 2-2 State 추가 및 설정
{: .notice--success}

<details>
<summary>1) Create Sub-State Machine -> Idle, Run, Walk</summary>
<div markdown="1">

<img src="/img/unity2d/stardewValley/2023-02-05-animator-sub-state-machine.png"/>

</div>
</details>

<details>
<summary>2) Create State -> Empty -> IdleUp, IdleDown, IdleLeft, IdleRight, RunUp...</summary>
<div markdown="1">

<img src="/img/unity2d/stardewValley/2023-02-05-animator-state.png"/>

</div>
</details>

<details>
<summary>3) 각 State에 맞는 Animation Clip(Motion) 연결</summary>
<div markdown="1">

<img src="/img/unity2d/stardewValley/2023-02-05-animator-state-motion.png" style="zoom:50%;"/>

</div>
</details>

## 2-3 Transition 추가 및 설정
{: .notice--success}

<details>
<summary>1) State {R Click} -> Make Transition -> (Up) Base Layer {L Click} -> States...</summary>
<div markdown="1">

<img src="/img/unity2d/stardewValley/2023-02-05-animator-make-transition-1.png"/>

<img src="/img/unity2d/stardewValley/2023-02-05-animator-make-transition-2.png"/>

- Idle 의 4개의 State 마다 Run, Walk 의 8개의 State 로의 Transition 을 추가
- Run, Walk 에선 같은 방향의 Idle State 로의 동일한 Transition 을 두 개씩 추가

</div>
</details>

<details>
<summary>2) Transition 설정</summary>
<div markdown="1">

<img src="/img/unity2d/stardewValley/2023-02-05-animator-transition-edit.png" style="zoom:50%;"/>

Has Exit Time : false
<br>Transition Duration in seconds : 0
<br> Conditions :
<body>
<table border="1">
    <tr align="center">
	    <td>from Idle</td>
	    <td>Up</td>
        <td>Down</td>
        <td>Right</td>
        <td>Left</td>
    </tr>
	<tr align="center">
	    <td>to Run</td>
	    <td>isRunning : true <br> yInput : Greater 0.01</td>
        <td>isRunning : true <br> yInput : Less -0.01</td>
        <td>isRunning : true <br> xInput : Greater 0.01</td>
        <td>isRunning : true <br> xInput : Less -0.01</td>
	</tr>
	<tr align="center">
	    <td>to Walk</td>
	    <td>isWalking : true <br> yInput : Greater 0.01</td>
        <td>isWalking : true <br> yInput : Less -0.01</td>
        <td>isWalking : true <br> xInput : Greater 0.01</td>
        <td>isWalking : true <br> xInput : Less -0.01</td>
	</tr>
</table>
<table border="1">
    <tr align="center">
	    <td>to Idle</td>
	    <td>Up</td>
        <td>Down</td>
        <td>Right</td>
        <td>Left</td>
    </tr>
	<tr align="center">
	    <td>from Run</td>
	    <td>isRunning : false <br> yInput : Less 0.01</td>
        <td>isRunning : false <br> yInput : Greater -0.01</td>
        <td>isRunning : false <br> xInput : Less 0.01</td>
        <td>isRunning : false <br> xInput : Greater -0.01</td>
	</tr>
	<tr align="center">
	    <td>from Walk</td>
	    <td>isWalking : false <br> yInput : Less 0.01</td>
        <td>isWalking : false <br> yInput : Greater -0.01</td>
        <td>isWalking : false <br> xInput : Less 0.01</td>
        <td>isWalking : false <br> xInput : Greater -0.01</td>
	</tr>
</table>
</body>

</div>
</details>

# 3.Animation Clip 편집
{: .notice--warning .text-center}

<img src="/img/unity2d/stardewValley/2023-02-05-animation-clip.png"/>

- 편집할 Sprite Renderer 컴포넌트를 가진 게임오브젝트에 Animator 컴포넌트 추가 ->
컨트롤러 연결 -> 해당 게임오브젝트 클릭 후 Animation Window 에서 각 Clip 마다 편집
- 타임라인 옆 … -> Show Sample Rate 활성 후 생긴 Samples 로 프레임 조절
- Add Property -> Sprite Renderer -> Flip X 로 좌우 이미지 조절
- 반복돼야 하는 Clip 일 경우 Clip Inspector Window 에서 Loop Time 체크

# 4.Script 생성 편집 및 추가
{: .notice--warning .text-center}

<details>
<summary>/Scripts/Misc/Settings.cs 편집</summary>
<div markdown="1">

```c#
using UnityEngine;

public static class Settings
{
    // Player Movement
    public const float runningSpeed = 5.333f;
    public const float walkingSpeed = 2.666f;

    // Player Animation Parameters
    public static int xInput;
    public static int yInput;
    public static int isWalking;
    public static int isRunning;

    // static constructor
    static Settings()
    {
        // Player Animation Parameters
        xInput = Animator.StringToHash("xInput");
        yInput = Animator.StringToHash("yInput");
        isWalking = Animator.StringToHash("isWalking");
        isRunning = Animator.StringToHash("isRunning");
    }
}
```

</div>
</details>

<details>
<summary>/Scripts/Events/EventHandler.cs 생성</summary>
<div markdown="1">

```c#
public delegate void MovementDelegate(
    float inputX, float inputY, bool isWalking, bool isRunning);

public static class EventHandler
{
    // Movement Event
    public static event MovementDelegate MovementEvent;

    // Movement Event Call For Publishers
    public static void CallMovementEvent(
        float inputX, float inputY, bool isWalking, bool isRunning)
    {
        if (MovementEvent != null)
        {
            MovementEvent(inputX, inputY, isWalking, isRunning);
        }
    }
}
```

</div>
</details>

<details>
<summary>/Scripts/Animation/MovementAnimationParameterControl.cs 생성</summary>
<div markdown="1">

```c#
using UnityEngine;

public class MovementAnimationParameterControl : MonoBehaviour
{
    private Animator animator;

    // Use this for initialisation

    private void Awake()
    {
        animator = GetComponent<Animator>();
    }

    private void OnEnable()
    {
        EventHandler.MovementEvent += SetAnimationParameters;
    }

    private void OnDisable()
    {
        EventHandler.MovementEvent -= SetAnimationParameters;
    }

    private void SetAnimationParameters(
        float xInput, float yInput, bool isWalking, bool isRunning)
    {
        animator.SetFloat(Settings.xInput, xInput);
        animator.SetFloat(Settings.yInput, yInput);
        animator.SetBool(Settings.isWalking, isWalking);
        animator.SetBool(Settings.isRunning, isRunning);
    }
}
```

<div class="notice">
Animator 컴포넌트를 가지고 있는 게임오브젝트에 해당 스크립트 추가
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
    private bool isRunning;
    private bool isWalking;

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

        // Send event to any listeners for player movement input
        EventHandler.CallMovementEvent(xInput, yInput, isWalking, isRunning);

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
        {
            isRunning = true;
            isWalking = false;
            movementSpeed = Settings.runningSpeed;
        }
        else if (xInput == 0 && yInput == 0)
        {
            isRunning = false;
            isWalking = false;
        }
    }

    private void PlayerWalkInput()
    {
        if (Input.GetKey(KeyCode.LeftShift) || Input.GetKey(KeyCode.RightShift))
        {
            isRunning = false;
            isWalking = true;
            movementSpeed = Settings.walkingSpeed;
        }
        else
        {
            isRunning = true;
            isWalking = false;
            movementSpeed = Settings.runningSpeed;
        }
    }

    private void PlayerMovement()
    {
        Vector2 move = new Vector2(xInput * movementSpeed * Time.deltaTime, yInput * movementSpeed * Time.deltaTime);

        rigidBody2D.MovePosition(rigidBody2D.position + move);
    }
}
```

</div>
</details>