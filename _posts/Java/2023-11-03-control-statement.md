---
title:  "제어문"
excerpt: "control statement"
categories: Java
tag: [control statement]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# if
{: .notice--warning .text-center}

안으로 말려들어가는 코드
```java
if () {
    if () {

    } else {
        if () {

        }
    }
}
```

예외를 먼저 if + return으로 필터링
통과 케이스를 코드 하단에 배치
최소한의 들여쓰기 구성
```java
//예외 필터링
if () {

    return;
}

if () {

    return;
}

//통과 케이스 배치
```

# switch
{: .notice--warning .text-center}

# while
{: .notice--warning .text-center}

//continue
//break

```java
int select = -1;
while(true) {
    //code
    if (select == 9) break;
}
```

# do while
{: .notice--warning .text-center}

# for
{: .notice--warning .text-center}

//continue
//break
//이중포문 flag 기법

# for each
{: .notice--warning .text-center}