---
title: "1인칭 플레이어"
categories: my-unity-docu
tag: [개발일지]
excerpt: "플레이어 움직임, 카메라 회전, 1인칭 팔, 애니메이션"
---

<span style="color:gray">unity version 2022.3.7f1</span>

# 플레이어 움직임 구현
{: .notice--warning}

- [X] 이동(걷기, 달리기)

- [X] 점프

- [X] 자연스러운 앉기와 일어서기

- [X] 중력과 지면 체크

- [X] 헤드밥

- [ ] 플레이어에 Character Controller 컴포넌트 추가

- [ ] 플레이어에 Rigidbody 컴포넌트 추가(Is Kinematic = true)

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class FirstPersonController : MonoBehaviour
{
    private CharacterController controller;

    private Vector3 velocity;
    private bool isGrounded;
    private float stableVelocityY = -0.5f; // 안정적으로 지면 체크를 할 기준 벨로시티 Y 값
    private bool isCrouching;
    private bool isCrouchTransitioning; // 앉거나 일어서기 중인지 확인하는 변수

    [Header ("Movement Speed")]
    public float walkSpeed;
    public float runSpeed;
    public float crouchSpeed;
    private float currentSpeed;
    [Header ("Player Height")]
    public float standHeight;
    public float crouchHeight;
    private float currentHeight;
    private float heightVelocity; // currentVelocity, 앉기/일어서기를 자연스럽게 도와줄 변수
    [Header ("Jump & Fall")]
    public float jumpHeight;
    public float gravity;
    private Vector3 lastGroundedVelocity;
    [Header ("headBob")]
    public float headBobFrequency;
    public float headBobAmplitude;
    private float headBobTimer;

    [Space (10f)]
    [SerializeField] private Transform cameraTransform;
    private float cameraOffsetY = -0.2f; // 플레이어 키 기준 카메라(눈) 위치 오프셋

    void Start()
    {
        Initialize();
    }

    void Update()
    {
        HandleMovement();
        HandleHeadBob();
        SmoothCrouch();
    }

    void Initialize()
    {
        controller = GetComponent<CharacterController>();

        // Movement Speed
        walkSpeed = 2.0f;
        runSpeed = 5.0f;
        crouchSpeed = 1.0f;

        // Player Height
        standHeight = 1.3f;
        crouchHeight = 0.5f;

        //Jump & Fall
        jumpHeight = 0.5f;
        gravity = -9.81f;

        //HeadBob
        headBobFrequency = 10f;
        headBobAmplitude = 0.1f;

        //Character Controller
        controller.radius = 0.5f;
        controller.height = standHeight;
    }

    void HandleMovement()
    {
        // 지면 체크
        isGrounded = controller.isGrounded;

        if (isGrounded && velocity.y < 0)
        {
            velocity.y = stableVelocityY; // isGrounded를 안정적으로 체크(0이면 안정적으로 안됨)하며 중력 가속(중첩) 방지를 위해 값 초기화
        }

        // 방향키 인풋
        float moveX = Input.GetAxisRaw("Horizontal");
        float moveZ = Input.GetAxisRaw("Vertical");

        // 일어서기, 웅크리기
        if (!isCrouchTransitioning)
        {
            if(isCrouching)
            {
                if(Input.GetKeyDown(KeyCode.C) ||
                   Input.GetKey(KeyCode.LeftShift) && moveZ > 0)
                {
                    StandUp();
                }
            }
            else if (Input.GetKeyDown(KeyCode.C))
            {
                Crouch();
            }
        }

        // 이동 속도 설정
        if (isGrounded)
        {
            if (moveZ > 0) // 뛰는건 앞으로 이동시에만 가능하도록 설정
            {
                currentSpeed = isCrouching ? crouchSpeed : (Input.GetKey(KeyCode.LeftShift) ? runSpeed : walkSpeed);
            }
            else
            {
                currentSpeed = isCrouching ? crouchSpeed : walkSpeed;
            }

            // 공중에서의 이동을 자연스럽게 처리하기 위해 땅에 있을 때의 마지막 속도 저장
            lastGroundedVelocity = (transform.right * moveX + transform.forward * moveZ).normalized * currentSpeed;
        }

        // 이동 방향 설정
        Vector3 move = isGrounded ? (transform.right * moveX + transform.forward * moveZ).normalized * currentSpeed
                                  : lastGroundedVelocity;

        // 이동 적용
        controller.Move(move * Time.deltaTime);

        // 점프 설정
        if (isGrounded && Input.GetKeyDown(KeyCode.Space) && !isCrouching)
        {
            velocity.y = Mathf.Sqrt(jumpHeight * -2f * gravity); // 점프 공식 v = sqrt(2gh)
        }

        // 중력 적용
        velocity.y += gravity * Time.deltaTime;
        controller.Move(velocity * Time.deltaTime);
    }

    void Crouch()
    {
        if (isCrouching || !isGrounded) return;

        controller.height = crouchHeight;
        isCrouching = true;

        isCrouchTransitioning = true; // 앉는 중 플래그 활성화
        StartCoroutine(ResetCrouchTransition());
    }

    void StandUp()
    {
        if (!isCrouching || !isGrounded) return;

        controller.height = standHeight;
        isCrouching = false;

        isCrouchTransitioning = true; // 일어서는 중 플래그 활성화
        StartCoroutine(ResetCrouchTransition());
    }

    IEnumerator ResetCrouchTransition()
    {
        yield return new WaitForSeconds(0.2f); // 0.2초 후 플래그 해제
        isCrouchTransitioning = false;
    }

    void HandleHeadBob()
    {
        Vector3 targetPosition = new Vector3(0, controller.height + cameraOffsetY, 0); // 카메라 위치
    
        if (isGrounded && (Input.GetAxisRaw("Horizontal") != 0 || Input.GetAxisRaw("Vertical") != 0))
        {
            if(currentSpeed == walkSpeed)
            {
                headBobTimer += Time.deltaTime * headBobFrequency;
            }
            else if(currentSpeed == runSpeed)
            {
                headBobTimer += Time.deltaTime * headBobFrequency * 2.0f;
            }
            else if(currentSpeed == crouchSpeed)
            {
                headBobTimer += Time.deltaTime * headBobFrequency * 0.6f;
            }

            float bobOffset = Mathf.Sin(headBobTimer) * headBobAmplitude;
            targetPosition.y += bobOffset;
        }
    
        cameraTransform.localPosition = Vector3.Lerp(cameraTransform.localPosition, targetPosition, Time.deltaTime * 5f);
    }

    void SmoothCrouch()
    {
        float targetHeight = isCrouching ? crouchHeight : standHeight;
        currentHeight = Mathf.SmoothDamp(currentHeight, targetHeight, ref heightVelocity, 0.01f);
        controller.height = currentHeight;
    }
}
```

# 플레이어 카메라(눈) 구현 추가
{: .notice--warning}

- [X] 마우스로 플레이어 카메라 시야 회전

- [X] Q, E 버튼으로 플레이어 카메라 기울기 상태를 선형보간으로 적용

- [ ] 플레이어 카메라 컴포넌트 Near = 0.01

```c#
public class FirstPersonController : MonoBehaviour
{
    // 마우스 회전
    private float mouseSensitivity = 2.0f; // 마우스 감도
    private float xRotation;
    // Q, E(좌, 우로 약간의 시야 이동과 함께 시야 기울기)
    private float maxTiltAngle = 20f; // 기울기 제한 각도
    private float tiltSpeed = 5f; // 기울기 보간 속도
    private float currentTilt; // 현재 기울기
    private float targetTilt; // 목표 기울기
    private float maxShiftAmount = 0.4f; // 시야 이동 최대 거리
    private float shiftSpeed = 5f; // 시야 이동 보간 속도
    private float currentShift; // 현재 시야 이동 값
    private float targetShift; // 목표 시야 이동 값

    void Update()
    {
        HandleMouseLook();
        HandleCameraTiltAndShift();
    }

    void HandleMouseLook()
    {
        float mouseX = Input.GetAxis("Mouse X") * mouseSensitivity;
        float mouseY = Input.GetAxis("Mouse Y") * mouseSensitivity;

        xRotation -= mouseY;
        xRotation = Mathf.Clamp(xRotation, -90f, 90f); // 상하 각도 제한

        cameraTransform.localRotation = Quaternion.Euler(xRotation, 0f, 0f);
        transform.Rotate(Vector3.up * mouseX);
    }

    void HandleCameraTiltAndShift()
    {
        targetTilt = 0f;
        targetShift = 0f;

        if (isGrounded && (currentSpeed != runSpeed))
        {
            if (Input.GetKey(KeyCode.Q) && !Input.GetKey(KeyCode.E))
            {
                targetTilt = maxTiltAngle;
                targetShift = -maxShiftAmount;
            }
            else if (Input.GetKey(KeyCode.E) && !Input.GetKey(KeyCode.Q))
            {
                targetTilt = -maxTiltAngle;
                targetShift = maxShiftAmount;
            }
        }

        currentTilt = Mathf.Lerp(currentTilt, targetTilt, Time.deltaTime * tiltSpeed); // 기울기 보간

        currentShift = Mathf.Lerp(currentShift, targetShift, Time.deltaTime * shiftSpeed); // 좌우 이동 보간

        // 카메라 로컬 회전 및 위치 적용 (기울기, 좌우 이동)
        cameraTransform.localRotation = Quaternion.Euler(xRotation, 0f, currentTilt);
        cameraTransform.localPosition = new Vector3(currentShift, cameraTransform.localPosition.y, cameraTransform.localPosition.z);
    }
}
```

# 플레이어 팔, 장착 가능한 카메라 구현 추가
{: .notice--warning}

- [X] 플레이어 팔 추가

- [X] 팔 관련 애니메이션 추가(Idle)

- [X] 장착 가능한 카메라 추가

- [X] 카메라 관련 애니메이션 추가(Idle, Equip, Unequip, ZoomIdle, ZoomIn, ZoomOut)

- [X] 키 버튼 1을 눌러 카메라 장착/해제(모션이 끝나야 다음 모션으로 가도록 설정)

- [X] 마우스 우클릭을 통해 카메라 줌 인/아웃(모션이 끝나지 않아도 중간에 자연스러운 전이가 가능하도록 설정)

- [ ] 플레이어 카메라 하위에 1인칭 팔 추가

- [ ] 오른손이나 왼손 오브젝트 하위에 장착 가능한 카메라 추가

- [ ] 플레이어 카메라 하위에 PointLight를 두고 위치 조정, 팔 오브젝트와 장착 가능한 오브젝트에 레이어"Arms"를 적용하고 PointLight의 Culling Mask = "Arms"를 적용해 어두운 곳에서도 팔 오브젝트와 장착 가능한 오브젝트는 보이도록 설정(Intensity와 Range 조절 필요)

- [ ] 카메라의 카메라 컴포넌트 설정
<br>→ Near = 0.1
<br>→ Depth를 플레이어 카메라보다 높은 수로 설정
<br>→ Physical Camera = true, Sensor Type = 65mm ALEXA 로 설정 해 카메라 느낌 살리기
<br>→ Render Target(Target Texture)의 Size = 1024 * 1024, Anti-aliasing = 8 samples

- [ ] 애니메이션 추가(각 애니메이션은 1초로 만들고 Speed 값으로 조절, Idle 타입은 Loop Time = true)

- [ ] 애니메이터 설정
<br>→ bool 타입으로 파라미터 값 추가
<br>→ 각 애니메이션 간 필요한 전이 추가
<br>→→ Idle 상태에서 다른 애니메이션으로 전이할 땐 Has Exit Time = false, Fixed Duration = false, Transition Duration = 0, 파라미터 값을 통해 전이
<br>→→ Idle 상태로 전환될 땐 Has Exit Time = true, Exit Time = 1, Transition Duration = 0으로 둬 애니메이션이 끝나면 자동으로 Idle 상태로 전이
<br>→→ Zoom In/Out간 전이를 만들어 애니메이션 진행 도중 즉각적으로 자연스러운 전이가 되도록 설정(Transition Duration, Transition Offset, Transition Graph를 이용)

<img src="/img/my-unity-docu/firstperson-player-animator.png"/>

```c#
public class FirstPersonController : MonoBehaviour
{
    // Anim 관련 변수
    bool isCameraEquiped;
    bool isEquipping;

    [SerializeField] private Animator armsAnim;

    void Update()
    {
        CameraEquipping();
        CameraZoomInOut();
    }

    void CameraEquipping()
    {
        if (Input.GetKeyDown(KeyCode.Alpha1) && !isEquipping)
        {
            isCameraEquiped = !isCameraEquiped;
            armsAnim.SetBool("isCameraEquiped", isCameraEquiped);
            StartCoroutine(WaitEquipping(0.5f));
        }
    }

    IEnumerator WaitEquipping(float animTransitionTime)
    {
        isEquipping = true;
        yield return new WaitForSeconds(animTransitionTime);
        isEquipping = false;
    }

    void CameraZoomInOut()
    {
        if (Input.GetKeyDown(KeyCode.Mouse1))
        {
            armsAnim.SetBool("isCameraZoomed", true);
        }
        else if (Input.GetKeyUp(KeyCode.Mouse1))
        {
            armsAnim.SetBool("isCameraZoomed", false);
        }
    }
}
```

# 사운드 추가
{: .notice--warning}

- [X] 걷기(서서 걷기, 앉아서 걷기), 뛰기, 점프, 착지 사운드 추가

- [ ] 플레이어에 Audio Source 컴포넌트 추가

```c#
public class FirstPersonController : MonoBehaviour
{
    private AudioSource audioSource;

    [SerializeField] private AudioClip walkSound;
    [SerializeField] private AudioClip runSound;
    private bool isFootstepPlaying; // 발소리 WaitForSeconds
    [SerializeField] private AudioClip jumpSound;
    [SerializeField] private AudioClip landSound;
    private bool landedRecently; // 착지소리 WaitForSeconds

    void Start()
    {
        Initialize();
    }

    void Update()
    {
        HandleMovement();
        HandleHeadBob();
        CameraFlash();
    }

    void Initialize()
    {
        audioSource = GetComponent<AudioSource>();
    }

    void HandleMovement()
    {
        // 지면 체크
        bool wasGrounded = isGrounded; // 착지 사운드 트리거
        /* isGrounded = controller.isGrounded; */

        // 점프 설정
        if (isGrounded && Input.GetKeyDown(KeyCode.Space) && !isCrouching)
        {
            /* velocity.y = Mathf.Sqrt(jumpHeight * -2f * gravity); // 점프 공식 v = sqrt(2gh) */
            audioSource.PlayOneShot(jumpSound);
        }

        // 착지 사운드 재생
        if (!wasGrounded && isGrounded && velocity.y < stableVelocityY && !landedRecently && !isCrouchTransitioning)
        {
            audioSource.PlayOneShot(landSound);
            StartCoroutine(PreventLandingSpam());
        }
    }

    void HandleHeadBob()
    {
        /* Vector3 targetPosition = new Vector3(0, controller.height + cameraOffsetY, 0); // 카메라 위치 */
    
        if (isGrounded && (Input.GetAxisRaw("Horizontal") != 0 || Input.GetAxisRaw("Vertical") != 0))
        {
            /*
            if(currentSpeed == walkSpeed)
            {
                headBobTimer += Time.deltaTime * headBobFrequency;
            }
            else if(currentSpeed == runSpeed)
            {
                headBobTimer += Time.deltaTime * headBobFrequency * 2.0f;
            }
            else if(currentSpeed == crouchSpeed)
            {
                headBobTimer += Time.deltaTime * headBobFrequency * 0.6f;
            }

            float bobOffset = Mathf.Sin(headBobTimer) * headBobAmplitude;
            targetPosition.y += bobOffset;
            */

            // 헤드밥이 제일 낮은 순간에 걷는 소리 재생
            if (Mathf.Sin(headBobTimer) <= -0.99f && !isFootstepPlaying)
            {
                PlayFootstepSound();
            }
        }
    
        /* cameraTransform.localPosition = Vector3.Lerp(cameraTransform.localPosition, targetPosition, Time.deltaTime * 5f); */
    }

    void PlayFootstepSound()
    {
        if (!isGrounded) return;
        if (isFootstepPlaying) return;

        isFootstepPlaying = true;

        audioSource.PlayOneShot(currentSpeed == runSpeed ? runSound : walkSound);

        StartCoroutine(ResetFootstep());
    }

    IEnumerator ResetFootstep()
    {
        yield return new WaitForSeconds(0.2f);
        isFootstepPlaying = false;
    }

    IEnumerator PreventLandingSpam()
    {
        // 불안정한 지면 인식으로 착지 사운드가 연속으로 나는것을 방지
        landedRecently = true;
        yield return new WaitForSeconds(0.3f);
        landedRecently = false;
    }
}
```

# 카메라 효과 추가
{: .notice--warning}

- [X] 카메라에 플래시 기능 추가(한 순간 밝아졌다가 점점 사라지는 빛, 플래시가 터질 때 빛이 해당 포지션에 고정)

- [X] 플래시에 플래시 사운드 추가

- [X] 플래시 순간 앞 일정 범위의 특정 레이어 프롭을 비활성화 하고 해당 위치에 파티클 재생

- [X] 카메라 스크립트는 따로 만들어 플레이어 스크립트에서 사용

- [ ] 장착 가능한 카메라에 Audio Source 컴포넌트 추가, 카메라 컴포넌트 Near = 0.1

- [ ] 장착 가능한 카메라 하위에 Spot Light 추가(FlashLight)(렌즈 앞에 정면을 보도록 포지션)

- [ ] 장착 가능한 카메라로만 볼 수 있는 오브젝트의 레이어"Ghost"를 설정하고 Collider 추가 후 Is Trigger = true

- [ ] 플레이어 카메라 컴포넌트 Culling Mask에 플레이어의 시야에 안보이게 할 오브젝트의 레이어"Ghost"를 해제

- [ ] "Ghost" 오브젝트를 비활성화 하고 재생할 파티클을 만들어 프리팹 화(하나만 인스턴스해서 사용)

- [ ] 스크립트 인스펙터의 타겟 레이어에 레이어"Ghost" 설정

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class CameraEquip : MonoBehaviour
{
    [SerializeField] private Light flashLight;
    [SerializeField] private float maxIntensity; // 플래시 최대 밝기
    [SerializeField] private float flashDuration; // 최대 밝기 유지 시간
    [SerializeField] private float fadeOutTime; // 빛이 사라지는 시간
    [Header ("Flash Sound")]
    [SerializeField] private AudioSource audioSource;
    [SerializeField] private AudioClip flashSound;

    [Header("Flash Hit Settings")]
    [SerializeField] private LayerMask targetLayer; // 플래시로 비활성화 할 특정 레이어
    [SerializeField] private float detectionRadius; // 탐지 범위 (구 형태)
    [SerializeField] GameObject ghostAfterglowPrefab;
    [SerializeField] GameObject ghostAfterglow;

    private bool isFlashing;
    private Transform originalParent; // 부모 오브젝트 정보
    private Vector3 originalPosition; // 하위 오브젝트일 때 로컬 포지션
    private Quaternion originalRotation; // 하위 오브젝트일 때 로컬 로테이션

    void Start()
    {
        flashLight = GetComponentInChildren<Light>();
        audioSource = GetComponent<AudioSource>();

        maxIntensity = 10f;
        flashDuration = 0.2f;
        fadeOutTime = 0.7f;

        detectionRadius = 2f;

        if (flashLight != null)
        {
            flashLight.spotAngle = 150f;
            flashLight.range = 10f;

            originalParent = flashLight.transform.parent;
            originalPosition = flashLight.transform.localPosition;
            originalRotation = flashLight.transform.localRotation;
        }

        ghostAfterglow = Instantiate(ghostAfterglowPrefab);
    }

    public void Flash()
    {
        if (Input.GetKeyDown(KeyCode.Mouse0) && !isFlashing)
        {
            StartCoroutine(FlashEffect());
        }
    }

    IEnumerator FlashEffect()
    {
        isFlashing = true;

        flashLight.transform.SetParent(null); // 부모 오브젝트에서 분리

        // 빛 점점 밝아지기
        float elapsedTime = 0f;
        while (elapsedTime < 0.05f) // 0.05초 동안 빠르게 밝아짐
        {
            flashLight.intensity = Mathf.Lerp(0, maxIntensity, elapsedTime / 0.05f);
            elapsedTime += Time.deltaTime;
            yield return null;
        }

        // 플래시가 비추는 방향으로 구 형태 범위 안의 특정 레이어의 오브젝트를 비활성화
        DetectingGhostInRange();

        // 플래시 사운드 재생
        audioSource.clip = flashSound;
        audioSource.time = 1f;
        audioSource.Play();

        // 강한 빛 유지 (flashDuration)
        flashLight.intensity = maxIntensity;
        yield return new WaitForSeconds(flashDuration);

        // 빛이 천천히 사라짐 (fadeOutTime)
        elapsedTime = 0f;
        while (elapsedTime < fadeOutTime)
        {
            flashLight.intensity = Mathf.Lerp(maxIntensity, 0, elapsedTime / fadeOutTime);
            elapsedTime += Time.deltaTime;
            yield return null;
        }

        flashLight.intensity = 0;

        // 부모 오브젝트로 되돌리고 로컬 포지션, 로테이션 값 적용
        flashLight.transform.SetParent(originalParent);
        flashLight.transform.localPosition = originalPosition;
        flashLight.transform.localRotation = originalRotation;

        isFlashing = false;
    }

    void DetectingGhostInRange()
    {
        // 플레이어 포지션의 앞쪽에 detectionRadius 만큼의 거리에 원점 기준 detectionRadius 범위의 구로 충돌 감지
        Collider[] hitColliders = Physics.OverlapSphere(flashLight.transform.position + flashLight.transform.forward * detectionRadius, detectionRadius, targetLayer);

        foreach (var hit in hitColliders)
        {
            ghostAfterglow.transform.position = hit.transform.position;
            ghostAfterglow.GetComponent<ParticleSystem>().Play();

            hit.gameObject.SetActive(false);
        }
    }

    void OnDrawGizmos()
    {
        if (flashLight != null)
        {
            Gizmos.color = Color.red;
            Gizmos.DrawWireSphere(flashLight.transform.position + flashLight.transform.forward * detectionRadius, detectionRadius);
        }
    }
}
```

```c#
public class FirstPersonController : MonoBehaviour
{
    // Equip
    CameraEquip cameraEquip;

    void Start()
    {
        Initialize();
    }

    void Update()
    {
        CameraFlash();
    }

    void Initialize()
    {
        cameraEquip = FindObjectOfType<CameraEquip>();
    }

    void CameraFlash()
    {
        if (cameraEquip == null) return;

        if (isCameraEquiped)
        {
            cameraEquip.Flash();
        }
    }
}
```

# 전체 코드
{: .notice--warning}

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class FirstPersonController : MonoBehaviour
{
    private CharacterController controller;
    private AudioSource audioSource;

    private Vector3 velocity;
    private bool isGrounded;
    private float stableVelocityY = -0.5f; // 안정적으로 지면 체크를 할 기준 벨로시티 Y 값
    private bool isCrouching;
    private bool isCrouchTransitioning; // 앉거나 일어서기 중인지 확인하는 변수
    // 마우스 회전
    private float mouseSensitivity = 2.0f; // 마우스 감도
    private float xRotation;
    // Q, E(좌, 우로 약간의 시야 이동과 함께 시야 기울기)
    private float maxTiltAngle = 20f; // 기울기 제한 각도
    private float tiltSpeed = 5f; // 기울기 보간 속도
    private float currentTilt; // 현재 기울기
    private float targetTilt; // 목표 기울기
    private float maxShiftAmount = 0.4f; // 시야 이동 최대 거리
    private float shiftSpeed = 5f; // 시야 이동 보간 속도
    private float currentShift; // 현재 시야 이동 값
    private float targetShift; // 목표 시야 이동 값
    // Anim 관련 변수
    bool isCameraEquiped;
    bool isEquipping;

    [Header ("Movement Speed")]
    public float walkSpeed;
    public float runSpeed;
    public float crouchSpeed;
    private float currentSpeed;
    [Header ("Player Height")]
    public float standHeight;
    public float crouchHeight;
    private float currentHeight;
    private float heightVelocity; // currentVelocity
    [Header ("Jump & Fall")]
    public float jumpHeight;
    public float gravity;
    private Vector3 lastGroundedVelocity;
    [Header ("headBob")]
    public float headBobFrequency;
    public float headBobAmplitude;
    private float headBobTimer;

    [Space (10f)]
    [SerializeField] private Transform cameraTransform;
    private float cameraOffsetY = -0.2f; // 플레이어 키 기준 카메라(눈) 위치 오프셋
    [SerializeField] private Animator armsAnim;
    [SerializeField] private AudioClip walkSound;
    [SerializeField] private AudioClip runSound;
    private bool isFootstepPlaying; // 발소리 WaitForSeconds
    [SerializeField] private AudioClip jumpSound;
    [SerializeField] private AudioClip landSound;
    private bool landedRecently; // 착지소리 WaitForSeconds

    // Equip
    CameraEquip cameraEquip;

    void Start()
    {
        Initialize();
    }

    void Update()
    {
        HandleMovement();
        HandleMouseLook();
        HandleHeadBob();
        SmoothCrouch();
        HandleCameraTiltAndShift();
        CameraEquipping();
        CameraZoomInOut();
        CameraFlash();
    }

    void Initialize()
    {
        controller = GetComponent<CharacterController>();
        audioSource = GetComponent<AudioSource>();

        // Movement Speed
        walkSpeed = 2.0f;
        runSpeed = 5.0f;
        crouchSpeed = 1.0f;

        // Player Height
        standHeight = 1.3f;
        crouchHeight = 0.5f;

        //Jump & Fall
        jumpHeight = 0.5f;
        gravity = -9.81f;

        //HeadBob
        headBobFrequency = 10f;
        headBobAmplitude = 0.1f;

        //Character Controller
        controller.radius = 0.5f;
        controller.height = standHeight;

        cameraEquip = FindObjectOfType<CameraEquip>();
    }

    void HandleMovement()
    {
        // 지면 체크
        bool wasGrounded = isGrounded; // 착지 사운드 트리거
        isGrounded = controller.isGrounded;

        if (isGrounded && velocity.y < 0)
        {
            velocity.y = stableVelocityY; // isGrounded를 안정적으로 체크(0이면 안정적으로 안됨)하며 중력 가속(중첩) 방지를 위해 값 초기화
        }

        // 방향키 인풋
        float moveX = Input.GetAxisRaw("Horizontal");
        float moveZ = Input.GetAxisRaw("Vertical");

        // 일어서기, 웅크리기
        if (!isCrouchTransitioning)
        {
            if(isCrouching)
            {
                if(Input.GetKeyDown(KeyCode.C) ||
                   Input.GetKey(KeyCode.LeftShift) && moveZ > 0)
                {
                    StandUp();
                }
            }
            else if (Input.GetKeyDown(KeyCode.C))
            {
                Crouch();
            }
        }

        // 이동 속도 설정
        if (isGrounded)
        {
            if (moveZ > 0) // 뛰는건 앞으로 이동시에만 가능하도록 설정
            {
                currentSpeed = isCrouching ? crouchSpeed : (Input.GetKey(KeyCode.LeftShift) ? runSpeed : walkSpeed);
            }
            else
            {
                currentSpeed = isCrouching ? crouchSpeed : walkSpeed;
            }

            // 공중에서의 이동을 자연스럽게 처리하기 위해 땅에 있을 때의 마지막 속도 저장
            lastGroundedVelocity = (transform.right * moveX + transform.forward * moveZ).normalized * currentSpeed;
        }

        // 이동 방향 설정
        Vector3 move = isGrounded ? (transform.right * moveX + transform.forward * moveZ).normalized * currentSpeed
                                  : lastGroundedVelocity;

        // 이동 적용
        controller.Move(move * Time.deltaTime);

        // 점프 설정
        if (isGrounded && Input.GetKeyDown(KeyCode.Space) && !isCrouching)
        {
            velocity.y = Mathf.Sqrt(jumpHeight * -2f * gravity); // 점프 공식 v = sqrt(2gh)
            audioSource.PlayOneShot(jumpSound);
        }

        // 착지 사운드 재생
        if (!wasGrounded && isGrounded && velocity.y < stableVelocityY && !landedRecently && !isCrouchTransitioning)
        {
            audioSource.PlayOneShot(landSound);
            StartCoroutine(PreventLandingSpam());
        }

        // 중력 적용
        velocity.y += gravity * Time.deltaTime;
        controller.Move(velocity * Time.deltaTime);
    }

    void HandleMouseLook()
    {
        float mouseX = Input.GetAxis("Mouse X") * mouseSensitivity;
        float mouseY = Input.GetAxis("Mouse Y") * mouseSensitivity;

        xRotation -= mouseY;
        xRotation = Mathf.Clamp(xRotation, -90f, 90f); // 상하 각도 제한

        cameraTransform.localRotation = Quaternion.Euler(xRotation, 0f, 0f);
        transform.Rotate(Vector3.up * mouseX);
    }

    void Crouch()
    {
        if (isCrouching || !isGrounded) return;

        controller.height = crouchHeight;
        isCrouching = true;

        isCrouchTransitioning = true; // 앉는 중 플래그 활성화
        StartCoroutine(ResetCrouchTransition());
    }

    void StandUp()
    {
        if (!isCrouching || !isGrounded) return;

        controller.height = standHeight;
        isCrouching = false;

        isCrouchTransitioning = true; // 일어서는 중 플래그 활성화
        StartCoroutine(ResetCrouchTransition());
    }

    IEnumerator ResetCrouchTransition()
    {
        yield return new WaitForSeconds(0.2f); // 0.2초 후 플래그 해제
        isCrouchTransitioning = false;
    }

    void HandleHeadBob()
    {
        Vector3 targetPosition = new Vector3(0, controller.height + cameraOffsetY, 0); // 카메라 위치
    
        if (isGrounded && (Input.GetAxisRaw("Horizontal") != 0 || Input.GetAxisRaw("Vertical") != 0))
        {
            if(currentSpeed == walkSpeed)
            {
                headBobTimer += Time.deltaTime * headBobFrequency;
            }
            else if(currentSpeed == runSpeed)
            {
                headBobTimer += Time.deltaTime * headBobFrequency * 2.0f;
            }
            else if(currentSpeed == crouchSpeed)
            {
                headBobTimer += Time.deltaTime * headBobFrequency * 0.6f;
            }

            float bobOffset = Mathf.Sin(headBobTimer) * headBobAmplitude;
            targetPosition.y += bobOffset;

            // 헤드밥이 제일 낮은 순간에 걷는 소리 재생
            if (Mathf.Sin(headBobTimer) <= -0.99f && !isFootstepPlaying)
            {
                PlayFootstepSound();
            }
        }
    
        cameraTransform.localPosition = Vector3.Lerp(cameraTransform.localPosition, targetPosition, Time.deltaTime * 5f);
    }

    void SmoothCrouch()
    {
        float targetHeight = isCrouching ? crouchHeight : standHeight;
        currentHeight = Mathf.SmoothDamp(currentHeight, targetHeight, ref heightVelocity, 0.01f);
        controller.height = currentHeight;
    }

    void PlayFootstepSound()
    {
        if (!isGrounded) return;
        if (isFootstepPlaying) return;

        isFootstepPlaying = true;

        audioSource.PlayOneShot(currentSpeed == runSpeed ? runSound : walkSound);

        StartCoroutine(ResetFootstep());
    }

    IEnumerator ResetFootstep()
    {
        yield return new WaitForSeconds(0.2f);
        isFootstepPlaying = false;
    }

    IEnumerator PreventLandingSpam()
    {
        // 불안정한 지면 인식으로 착지 사운드가 연속으로 나는것을 방지
        landedRecently = true;
        yield return new WaitForSeconds(0.3f);
        landedRecently = false;
    }

    void HandleCameraTiltAndShift()
    {
        targetTilt = 0f;
        targetShift = 0f;

        if (isGrounded && (currentSpeed != runSpeed))
        {
            if (Input.GetKey(KeyCode.Q) && !Input.GetKey(KeyCode.E))
            {
                targetTilt = maxTiltAngle;
                targetShift = -maxShiftAmount;
            }
            else if (Input.GetKey(KeyCode.E) && !Input.GetKey(KeyCode.Q))
            {
                targetTilt = -maxTiltAngle;
                targetShift = maxShiftAmount;
            }
        }

        currentTilt = Mathf.Lerp(currentTilt, targetTilt, Time.deltaTime * tiltSpeed); // 기울기 보간

        currentShift = Mathf.Lerp(currentShift, targetShift, Time.deltaTime * shiftSpeed); // 좌우 이동 보간

        // 카메라 로컬 회전 및 위치 적용 (기울기, 좌우 이동)
        cameraTransform.localRotation = Quaternion.Euler(xRotation, 0f, currentTilt);
        cameraTransform.localPosition = new Vector3(currentShift, cameraTransform.localPosition.y, cameraTransform.localPosition.z);
    }

    void CameraEquipping()
    {
        if (Input.GetKeyDown(KeyCode.Alpha1) && !isEquipping)
        {
            isCameraEquiped = !isCameraEquiped;
            armsAnim.SetBool("isCameraEquiped", isCameraEquiped);
            StartCoroutine(WaitEquipping(0.5f));
        }
    }

    IEnumerator WaitEquipping(float animTransitionTime)
    {
        isEquipping = true;
        yield return new WaitForSeconds(animTransitionTime);
        isEquipping = false;
    }

    void CameraZoomInOut()
    {
        if (Input.GetKeyDown(KeyCode.Mouse1))
        {
            armsAnim.SetBool("isCameraZoomed", true);
        }
        else if (Input.GetKeyUp(KeyCode.Mouse1))
        {
            armsAnim.SetBool("isCameraZoomed", false);
        }
    }

    void CameraFlash()
    {
        if (cameraEquip == null) return;

        if (isCameraEquiped)
        {
            cameraEquip.Flash();
        }
    }
}
```

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class CameraEquip : MonoBehaviour
{
    [SerializeField] private Light flashLight;
    [SerializeField] private float maxIntensity; // 플래시 최대 밝기
    [SerializeField] private float flashDuration; // 최대 밝기 유지 시간
    [SerializeField] private float fadeOutTime; // 빛이 사라지는 시간
    [Header ("Flash Sound")]
    [SerializeField] private AudioSource audioSource;
    [SerializeField] private AudioClip flashSound;

    [Header("Flash Hit Settings")]
    [SerializeField] private LayerMask targetLayer; // 플래시로 비활성화 할 특정 레이어
    [SerializeField] private float detectionRadius; // 탐지 범위 (구 형태)
    [SerializeField] GameObject ghostAfterglowPrefab;
    [SerializeField] GameObject ghostAfterglow;

    private bool isFlashing;
    private Transform originalParent; // 부모 오브젝트 정보
    private Vector3 originalPosition; // 하위 오브젝트일 때 로컬 포지션
    private Quaternion originalRotation; // 하위 오브젝트일 때 로컬 로테이션

    void Start()
    {
        flashLight = GetComponentInChildren<Light>();
        audioSource = GetComponent<AudioSource>();

        maxIntensity = 10f;
        flashDuration = 0.2f;
        fadeOutTime = 0.7f;

        detectionRadius = 2f;

        if (flashLight != null)
        {
            flashLight.spotAngle = 150f;
            flashLight.range = 10f;

            originalParent = flashLight.transform.parent;
            originalPosition = flashLight.transform.localPosition;
            originalRotation = flashLight.transform.localRotation;
        }

        ghostAfterglow = Instantiate(ghostAfterglowPrefab);
    }

    public void Flash()
    {
        if (Input.GetKeyDown(KeyCode.Mouse0) && !isFlashing)
        {
            StartCoroutine(FlashEffect());
        }
    }

    IEnumerator FlashEffect()
    {
        isFlashing = true;

        flashLight.transform.SetParent(null); // 부모 오브젝트에서 분리

        // 빛 점점 밝아지기
        float elapsedTime = 0f;
        while (elapsedTime < 0.05f) // 0.05초 동안 빠르게 밝아짐
        {
            flashLight.intensity = Mathf.Lerp(0, maxIntensity, elapsedTime / 0.05f);
            elapsedTime += Time.deltaTime;
            yield return null;
        }

        // 플래시가 비추는 방향으로 구 형태 범위 안의 특정 레이어의 오브젝트를 비활성화
        DetectingGhostInRange();

        // 플래시 사운드 재생
        audioSource.clip = flashSound;
        audioSource.time = 1f;
        audioSource.Play();

        // 강한 빛 유지 (flashDuration)
        flashLight.intensity = maxIntensity;
        yield return new WaitForSeconds(flashDuration);

        // 빛이 천천히 사라짐 (fadeOutTime)
        elapsedTime = 0f;
        while (elapsedTime < fadeOutTime)
        {
            flashLight.intensity = Mathf.Lerp(maxIntensity, 0, elapsedTime / fadeOutTime);
            elapsedTime += Time.deltaTime;
            yield return null;
        }

        flashLight.intensity = 0;

        // 부모 오브젝트로 되돌리고 로컬 포지션, 로테이션 값 적용
        flashLight.transform.SetParent(originalParent);
        flashLight.transform.localPosition = originalPosition;
        flashLight.transform.localRotation = originalRotation;

        isFlashing = false;
    }

    void DetectingGhostInRange()
    {
        // 플레이어 포지션의 앞쪽에 detectionRadius 만큼의 거리에 원점 기준 detectionRadius 범위의 구로 충돌 감지
        Collider[] hitColliders = Physics.OverlapSphere(flashLight.transform.position + flashLight.transform.forward * detectionRadius, detectionRadius, targetLayer);

        foreach (var hit in hitColliders)
        {
            ghostAfterglow.transform.position = hit.transform.position;
            ghostAfterglow.GetComponent<ParticleSystem>().Play();

            hit.gameObject.SetActive(false);
        }
    }

    void OnDrawGizmos()
    {
        if (flashLight != null)
        {
            Gizmos.color = Color.red;
            Gizmos.DrawWireSphere(flashLight.transform.position + flashLight.transform.forward * detectionRadius, detectionRadius);
        }
    }
}
```

# 기록 영상
{: .notice--warning}

{% include video id="gNm2mz5XsAE" provider="youtube" %}