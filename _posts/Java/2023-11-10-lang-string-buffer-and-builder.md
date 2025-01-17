---
title:  "java.lang.StringBuffer&Builder"
categories: Java
---

# append, insert, indexOf, delete, replace, compareTo, reverse, setCharAt, sebSequence
{: .notice--warning}

```java
//- String
//많은 Library를 제공, 전용 연산자 제공
//불변성의 원칙으로 인해 문자열 연산 속도가 느리고 메모리를 많이 사용

//- StringBuffer
//문자열에 더하기 연산과 텍스트 교체, 삭제를 위해 개발된 Library
//가변성 배열 통해 문자열을 삽입, 삭제가 자율적, 연산 속도가 빠르고 메모리 낭비가 없음
//Library 지원이 적다->String 사용해야 함
//thread safe하여 StringBulider보다 아주 조금 느림

//- StringBuilder
//StringBuffer와 기능 동일, 문법이 완벽히 호환되고 좀 더 빠르지만 thread safe하지 않음

StringBuffer sb = new StringBuffer("Hell");
//StringBuilder sb = new StringBuilder("Hello");
		
// append : 문자열을 더하는 메서드
sb.append("World");
System.out.println(sb);//HellWorld
		
// insert : 문자열을 오프셋만큼에 삽입
sb.insert(4, "o");
System.out.println(sb);//HelloWorld
sb.insert(10, "!");
System.out.println(sb);//HelloWorld!
		
// indexOf : 문자열을 탐색하여 index로 반환하는 기능
int index = sb.indexOf("World");
System.out.println(index);//5
index = sb.indexOf("Healo");
System.out.println(index);//-1 => 찾는 문자열이 없을 때 음수 리턴
index = sb.indexOf("l", sb.indexOf("l") + "l".length());//다음 값을 찾고 싶을 때
System.out.println(index);//3
		
// delete : 시작 인덱스부터 끝 인덱스까지 해당하는 문자열을 삭제
int index2 =  sb.indexOf("World");//5
sb.delete(index2, index2 + "World".length());//5, 5
System.out.println(sb);//Hello!
//방금 삭제한 곳에 다른 문자열 추가
sb.insert(index2, "java");
System.out.println(sb);//Hellojava!
		
// replace : 시작 인덱스부터 끝 인덱스까지 삭제 후 시작 인덱스에 문자열 삽입
sb.replace(index2, index2 + "Java".length(), "String");
System.out.println(sb);//HelloString!
		
// compareTo : 문자열끼리 비교해 거리의 차이를 리턴
StringBuffer sb2 = new StringBuffer("b"); 
System.out.println(sb2.compareTo(new StringBuffer("b")));//0(같은 문자)
System.out.println(sb2.compareTo(new StringBuffer("a")));//1(양수일 때 비교 대상이 차이만큼 더 앞에 있음)
System.out.println(sb2.compareTo(new StringBuffer("c")));//-1(음수일 때 비교 대상이 차이만큼 더 뒤에 있음)
//equals를 사용할 수 있는 방법**
System.out.println(sb2.toString().equals("b"));//true
		
// reverse : 문자열 반전
StringBuffer sb3 = new StringBuffer("live"); 
System.out.println(sb3.reverse());//evil
		
// setCharAt : 한 글자만 바꿔주는 기능
sb3.setCharAt(0, 'E');
System.out.println(sb3);//Evil
		
// sebSequence : 문자열 자르기
String str = (String)sb3.subSequence(1, 3);//리턴 타입인 CharSequence는 문자열 타입의 원형 
System.out.println(str);//vi
```
