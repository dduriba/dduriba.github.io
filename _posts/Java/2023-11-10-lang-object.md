---
title:  "java.lang.Object"
excerpt: "java.lang.Object"
categories: Java
tag: [lang, Object]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# toString, hashCode, equals, identityHashCode, clone, getClass
{: .notice--warning .text-center}

```java
import java.lang.reflect.InvocationTargetException;
import java.lang.reflect.Method;
import java.util.Objects;

public class ObjectLibrary {
	public static void main(String[] args) throws IllegalAccessException, IllegalArgumentException, InvocationTargetException {
		Object str1 = new String("helloworld");
		Object str2 = "helloworld";
		Object hash1 = new HashTest("java", 20);
		Object hash2 = new HashTest("java", 21);
		Object hash3 = new HashTest("java", 20);
		
		//toString : 일반적으로 @Override하여 객체의 정보를 문자열로 출력
		System.out.println(hash1.toString());//패키지명.클래스명@해시코드 => @Override하지 않을 경우 나오는 패턴
		
		//hashCode : 객체의 고유 식별 번호
		System.out.println(str1.hashCode());//-1524582912
		System.out.println(str2.hashCode());//-1524582912
		System.out.println(str1.equals(str2));//true
		
		//hashCode를 @Override하지 않으면 메모리 주소를 참조하여 hashCode를 생성하기 때문에 equals를 활용할 수 없음
		//equals : 객체의 고유 값을 비교하여 객체가 같은지 확인해 주는 메서드
		//객체 클래스에 hashCode, equals @Override 전
		System.out.println(hash1.hashCode());//1865127310
		System.out.println(hash2.hashCode());//1586600255
		System.out.println(hash3.hashCode());//474675244
		System.out.println(hash1.equals(hash3));//false
		
		//객체 클래스에 hashCode, equals @Override 후
		System.out.println(hash1.hashCode());//3273493
		System.out.println(hash2.hashCode());//3273524
		System.out.println(hash3.hashCode());//3273493
		System.out.println(hash1.equals(hash3));//true
		
		//identityHashCode : 실제 메모리 주소를 기반으로 hashCode를 확인하는 방법
		//hashCode를 @Override하지 않았을 때와 동일한 값 리턴(메모리 주소 기반)
		System.out.println(System.identityHashCode(hash1));//1865127310
		System.out.println(System.identityHashCode(hash2));//1586600255
		System.out.println(System.identityHashCode(hash3));//474675244
		
		//clone : 객체를 복사(hard copy)하는 메서드
		CloneTest clone1 = new CloneTest("java");
		CloneTest clone2 = clone1.clone(); 
		
		System.out.println(clone1.equals(clone2));//true
		
		//getClass : Class의 정보를 가져올 때 활용 (클래스 이름, 메서드, 멤버변수 선언 된 값, 실제 값)
		//해당 기능을 통해 Class의 모든 정보를 알 수 있고 자동화 처리가 가능(Spring의 핵심 원리)
		System.out.println(str2.getClass().getName());//패키지명.클래스명
		System.out.println(str2.getClass().getSimpleName());//클래스명
		System.out.println(str2.getClass().getSuperclass().getName());//부모의 패키지명.클래스명
		for (Method method : str2.getClass().getMethods()) {
//	 			System.out.println(method.getName());
			if (method.getName().equals("length")) {
				//method.invoke() Add throws declaration
				System.out.println(method.invoke(str2, null));
				System.out.println(((String) str2).length());
			}
		}
	}
	
	public static class HashTest {
		private String name;
		private int age;
		
		public HashTest(String name, int age) {
			super();
			this.name = name;
			this.age = age;
		}

		@Override
		public int hashCode() {
			return Objects.hash(age, name);
		}

		@Override
		public boolean equals(Object obj) {
			if (this == obj)
				return true;
			if (obj == null)
				return false;
			if (getClass() != obj.getClass())
				return false;
			HashTest other = (HashTest) obj;
			return age == other.age && Objects.equals(name, other.name);
		}
	}
	
	public static class CloneTest implements Cloneable {
		String str;
		
		public CloneTest(String str) {
			super();
			this.str = str;
		}
		
		@Override
		public int hashCode() {
			return Objects.hash(str);
		}

		@Override
		public boolean equals(Object obj) {
			if (this == obj)
				return true;
			if (obj == null)
				return false;
			if (getClass() != obj.getClass())
				return false;
			CloneTest other = (CloneTest) obj;
			return Objects.equals(str, other.str);
		}

		//1.클래스에 implements Cloneable
		//2.오버라이드 clone method
		//3.clone메서드의 접근제한자 public으로 변경
		//4.메서드에 붙은 throws CloneNotSupportedException 예외처리 제거
		//5.super.clone()을 Surround with try/catch
		//6.코드가 끝나는 지점에 return null처리
		//7.return 타입을 본인 클래스로 바꾸고 super.clone()를 본인 클래스 타입으로 캐스팅
		@Override
		public CloneTest clone() {
			try {
				return (CloneTest)super.clone();
			} catch (CloneNotSupportedException e) {
				e.printStackTrace();
			}
			return null;
		}
	}
}
```
