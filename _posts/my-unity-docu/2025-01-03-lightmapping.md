---
title: "Lightmapping(Baked Lighting)"
categories: my-unity-docu
tag: [최적화]
---

<span style="color:gray">unity version 2022.3.7f1</span>

# 라이트매핑(Lightmapping)
{: .notice--warning}

씬의 표면 밝기를 미리 계산해 텍스처로 저장하는 기능으로 해당 텍스처는 라이트맵이라고 합니다. 실시간 조명은 연산에 많은 부담이 되기 때문에 움직이지 않는 게임오브젝트에 라이트매핑을 적용해 연산 부담을 줄일 수 있습니다.

