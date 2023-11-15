---
title:  "java.lang.String"
excerpt: "java.lang.String"
categories: Java
tag: [lang, String]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# equals
{: .notice--warning .text-center}

```java
// equals : 문자열을 비교해 boolean값으로 리턴
System.out.println("aa".equals("AA"));//false
System.out.println("aa".equals("AA".toLowerCase()));//true, toLowerCase : 문자열의 모든 문자들을 소문자로 전환
System.out.println("AA".equals("aa".toUpperCase()));//true, toUpperCase : 문자열의 모든 문자들을 대문자로 전환
System.out.println("aa".equalsIgnoreCase("AA"));//true, equalsIgnoreCase : 대소문자를 무시하고 문자열을 비교해 boolean값으로 리턴
```

# contains
{: .notice--warning .text-center}

```java
// contains : 문자열이 포함되었는지 확인 후 boolean값으로 리턴
System.out.println("aabb".contains("ab"));//true
```

# compairTo
{: .notice--warning .text-center}

```java
// compareTo : 문자열끼리 비교해 거리의 차이를 int값으로 리턴
System.out.println("Alex".compareTo("Alen"));//10, 대상과 비교할 때 10만큼 뒤에있음
System.out.println("Alen".compareTo("Alex"));//-10, 대상과 비교할 때 10만큼 앞에있음
System.out.println("Alex".compareTo("Alex"));//0, 같은 문자열
```

# concat
{: .notice--warning .text-center}

```java
// concat : 문자열을 결합해 String값으로 리턴
String str1 = "Hello";
String str2 = "World!";
System.out.println(str1.concat(str2));
System.out.println(str1 + str2);//concat을 잘 쓰지 않는 이유
```

# charAt
{: .notice--warning .text-center}

```java
// charAt : 문자열에서 index에 해당하는 문자를 char값으로 리턴
String str = "domain@email.com";
System.out.println(str.charAt(6));//@
```

# indexOf
{: .notice--warning .text-center}

```java
// indexOf : 문자열에서 인자의 문자열과 일치하는 index를 int값으로 리턴
String str = "Can you can a can as a canner can can a can?";
System.out.println(str.indexOf("CAN"));//-1, 값을 찾지 못했을 때 -1 리턴
System.out.println(str.indexOf("Can"));//0, 대소문자 구별함
System.out.println(str.indexOf("can"));//8, 첫번째 index인 8 리턴
System.out.println(str.indexOf("can", 9));//14, index9부터 검사해 두번째 index인 14 리턴
System.out.println(str.indexOf("can", 15));//23, index15부터 검사해 두번째 index인 23 리턴
int i = str.indexOf("can", 9);//14
System.out.println(str.indexOf("can", i + "can".length()));//23, index14+3부터 검사해 두번째 index인 23 리턴
		
// indexOf 활용편
String token = "can";
int startIndex = 0;
int count = 0;
		
while(true) {
	int result = str.indexOf(token, startIndex);
	if(result < 0) break;//못 찾은 경우(result == -1)
	startIndex = result + token.length();
	count++;
	System.out.println("찾은 index : " + result);
}
System.out.println("찾은 갯수 : " + count);
```

# lastIndexOf
{: .notice--warning .text-center}

```java
// lastIndexOf : 문자열의 마지막 인덱스부터 인자의 문자열과 일치하는 index를 int값으로 리턴
String str = "Can you can a can as a canner can can a can?";
System.out.println(str.lastIndexOf("can"));//40
System.out.println(str.lastIndexOf("can", 40 - "can".length()));//34
```

# startWith
{: .notice--warning .text-center}

```java
// startWith : 문자열의 첫 번째 인덱스부터 연속성을 확인해 boolean값으로 리턴
String str = "Can you can a can as a canner can can a can?";
System.out.println(str.startsWith("can"));//false
System.out.println(str.startsWith("Can"));//true
System.out.println(str.startsWith("Canyou"));//false
System.out.println(str.startsWith("Can you"));//true
```

# endsWith
{: .notice--warning .text-center}

```java
// endsWith : 문자열의 마지막 인덱스부터 연속성을 확인해 boolean값으로 리턴, *확장자를 확인할때 유용*
String str = "log.txt";
System.out.println(str.endsWith(".txt"));//true
```

# trim, strip
{: .notice--warning .text-center}

```java
// trim, strip : 문자열의 white space 제거해 String값으로 리턴
// strip은 11버전부터 사용 가능
String str = "\r 이름 : 리트리버, \t 나이 : 7		\u2003\n\t";
System.out.println(str.trim());// trim : 문자 쓰레기 값을 제외한 white space 제거
//=>"이름 : 리트리버, 	 나이 : 7		 "
System.out.println(str.strip());// strip : **모든 white space 제거**
//=>"이름 : 리트리버, 	 나이 : 7"
System.out.println(str.stripLeading());// strip : 앞쪽의 white space만 제거
//=>"이름 : 리트리버, 	 나이 : 7		 //
//=>	"//
System.out.println(str.stripTrailing());// strip : 뒤쪽의 white space만 제거
//=>"
//=> 이름 : 리트리버, 	 나이 : 7"
System.out.println(str.stripIndent());// strip : \n\t 일부 공백을 살려 indent가 보이도록 제거
//=>"
//=>이름 : 리트리버, 	 나이 : 7
//=>"
```

# subString
{: .notice--warning .text-center}

```java
// subString : 문자열을 지정한 범위만큼 잘라 String값으로 리턴
String str = "0123456789ABCDEFG";
System.out.println(str.substring(10));//ABCDEFG
System.out.println(str.substring(2, 5));//234
System.out.println(str.substring(str.length() - 7));//ABCDEFG
System.out.println(str.substring(str.length() - 7, str.length()));//ABCDEFG
```

# replace
{: .notice--warning .text-center}

```java
// replace : 지정한 문자열을 교체해 String값으로 리턴
String str = "He__o Wor_d";
System.out.println(str.replace("_", "l"));//Hello World
System.out.println(str.replace(" ", ""));//He__oWor_d, 띄어쓰기를 제거
System.out.println(str.replace("He__o", "Hello"));//Hello Wor_d
```

# replaceAll
{: .notice--warning .text-center}

```java
// replaceAll : 정규식 패턴으로 문자열을 교체/제거 할때 활용, 일반 문자열도 가능, String값으로 리턴
String str = "TH!$ !$ $O RANDOM!\n\t";
//특수문자를 제거하는 정규식 표현 => id, pw 또는 입력값의 특수문자를 제거하거나 교체하는 용도로도 활용
String match = "[^\uAC00-\uD7A3xfe0-9a-zA-Z\\s]";
System.out.println(str.replaceAll(match, ""));
//=>"TH  O RANDOM
//=>	"
System.out.println(str.replaceAll(match, "").strip());//white space까지 같이 제거
//=>"TH  O RANDOM"
```

# repaceFirst
{: .notice--warning .text-center}

```java
// repaceFirst : 매칭되는 첫 번째 문자열을 교체해 String값으로 리턴
String str = "!t !s !t";
System.out.println(str.replaceFirst("!s", "is"));//!t is !t
```

# split
{: .notice--warning .text-center}

```java
// split : 문자열을 특정 인자(Delimiter=구분자,정규식)로 잘라 토큰배열로 반환
String str = "name : Alex, name : Alen, name : Alice";
String[] strArray1 = str.split(",");
for(String s : strArray1) {
	System.out.println(s.strip());
}
		
// 2중으로 자르기
for(String s1 : strArray1) {
	String[] strArray2 = s1.split(":");
	for(String s2 : strArray2) {
		System.out.println(s2.strip());
	}
	System.out.println(strArray2[1].strip());
}
```

# join
{: .notice--warning .text-center}

```java
String str = "name : Alex, name : Alen, name : Alice";
String[] strArray = str.split(",");
System.out.println(Arrays.toString(strArray));//[name : Alex,  name : Alen,  name : Alice]
// join을 사용하지 않고 문자열 합치기
String str2 = "";
for(String s : strArray) {
	str2 += s + ",";
}
System.out.println(str2);//name : Alex, name : Alen, name : Alice,
		
// join : 배열된 문자열을 하나의 문자열로 합칠 때 사용
String str3 = "";
str3 = String.join(",", strArray);
System.out.println(str3);//name : Alex, name : Alen, name : Alice
```

# StringTokenizer
{: .notice--warning .text-center}

```java
// StringTokenizer : Split 객체버전
String str = "name : Alex, name : Alen, name : Alice";
StringTokenizer tokens = new StringTokenizer(str, ",");
// while문 has + nextMore 패턴
while(tokens.hasMoreElements()) {// 엘리먼트가 더 있을때
	System.out.println(tokens.nextElement());// 다음 엘리먼트를 가져옴
}
```

# toUpperCase, toLowerCase
{: .notice--warning .text-center}

```java
// toUpperCase, toLowerCase : 문자열의 대소문자 변경
String str = "Hello World!";
System.out.println(str.toUpperCase());//HELLO WORLD!
System.out.println(str.toLowerCase());//hello world!
```

# valueOf
{: .notice--warning .text-center}

```java
// valueOf : 다른 자료형을 문자열로 변경하는 방법
int temp = 7;
// 편한 방법
String str1 = "" + temp;
System.out.println(str1);
// valueOf를 이용한 방법
String str2 = String.valueOf(temp);
System.out.println(str2);
```

# repeat
{: .notice--warning .text-center}

```java
// repeat : 문자열 반복
System.out.println("-=".repeat(5));//-=-=-=-=-=
```

# format
{: .notice--warning .text-center}

```java
// format : %d, %f, %s등 format출력 지원 함수->소수점 자르는 용도로 많이 활용
String str = String.format("%.2f %s", 3.14159, "pi");
System.out.println(str);//3.14 pi
```

