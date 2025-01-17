---
title:  "제어문"
categories: Java
---

# if
{: .notice--warning}

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

코딩 중 들여쓰기는 최소화!
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
{: .notice--warning}

```java
char grade;
swtich(grade) {
    case 'A': case 'a':
        
        break;
    case 'B': case 'b':

        break;
    default :

        break;
}
```

# while
{: .notice--warning}

```java
int select = -1;
while(true) {
    if (select == 0) continue;
    //code
    if (select == 9) break;
}
```

# do while
{: .notice--warning}

do while의 특징: 조건에 관계없이 do 블록을 최초 한번은 무조건 실행
```java
int i = 0;
do {
    i++;
    //code
} while(i < 10)
```

# for
{: .notice--warning}

```java
boolean flag = false;
for(int i = 0; i < 10; i++) {
    if(i % 2 == 0) continue;
    for(int j = 0; j < 10; j++) { //중첩for문
        if(i * j == 72) {
            flag = true;
            break;
        }
    }
    if(flag) break; //flag기법
}
```

# for each
{: .notice--warning}

for ({배열의 데이터 타입}{요소 명} : {배열 명})
```java
int[] numbers = new int[10];
for (int number : numbers) {

}
```