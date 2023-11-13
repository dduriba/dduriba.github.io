---
title:  "다형성"
excerpt: "polymorphism"
categories: Java
tag: [polymorphism]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# class:Mac
{: .notice--warning .text-center}

```java
public class Mac {
	private String name;
	
	public Mac(String name) {
		super();
		this.name = name;
	}

	protected void SleepMode() {
		System.out.println("잠자기 모드 사용 가능");
	}
	
	protected void ChargerType() {
		System.out.print("충전 커넥터 :");
	}

	@Override
	public String toString() {
		return "Mac [name=" + name + "]";
	}
}
```

# class:Pro13_2017
{: .notice--warning .text-center}

```java
public class Pro13_2017 extends Mac {

	public Pro13_2017(String name) {
		super(name);
	}

	@Override
	protected void SleepMode() {
		System.out.println("잠자기 모드 사용 불가능");
	}

	@Override
	protected void ChargerType() {
		super.ChargerType();
		System.out.println("C타입");
	}
	
	public void ChipWarn() {
		System.out.println("해당 제품은 인텔 칩을 사용합니다");
	}
}
```

# class:Pro13_2020
{: .notice--warning .text-center}

```java
public class Pro13_2020 extends Mac {

	public Pro13_2020(String name) {
		super(name);
	}

	@Override
	protected void ChargerType() {
		super.ChargerType();
		System.out.println("라이트닝");
	}
}
```

# class:Run
{: .notice--warning .text-center}

```java
public class Run {
	public static void main(String[] args) {
		//다형성 : 부모의 타입으로 자식의 타입을 대체할 수 있는 개념, 부모의 타입으로 배열을 선언해 자식을 담을 수 있다.
		Mac[] products = new Mac[2];
		
		products[0] = new Pro13_2017("Pro13_2017");//up casting
		products[1] = new Pro13_2020("Pro13_2020");//up casting
		
		for (Mac product : products) {
			ProductDetail(product);
		}
	}
	
	public static void ProductDetail(Mac product) {
		System.out.println(product.toString());
		product.SleepMode();//override 안 할 경우 부모 메서드 실행, 할 경우 동적 바인딩
		product.ChargerType();//동적 바인딩 : 컴파일 시 정적 바인딩 된 메서드를 실행할 당시의 객체 타입을 기준으로 바인딩 되는 것
		if (product instanceof Pro13_2017)//instanceof : 객체 타입 비교 연산자
			((Pro13_2017)product).ChipWarn();//down casting
	}
}
```