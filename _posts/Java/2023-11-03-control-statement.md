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

스파게티 코드
{: .notice--success}

```java
if () {
    if () {

    } else {
        if () {

        } else {

        }
    }
}
```

리팩터링
{: .notice--success}

- 들여쓰기 최소화
1. 예외 처리: if + return으로 필터링 후
2. 패스 케이스 배치

```java
//1.예외 처리
if () {

    return;
}

if () {

    return;
}

if () {
    
    return;
}

//2.패스 케이스 배치
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