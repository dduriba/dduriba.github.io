---
title:  "인터페이스"
categories: Java
---

# interface:Charger
{: .notice--warning}

```java
//인터페이스
//주로 코드간의 설계 규격을 맞추거나 또는 특별한 타입임을 알리기 위해 활용되는 문법
//인스턴스를 생성할 수 없다.
//추상 메서드와 상수만을 멤버로 가질 수 있다.=>JDK1.8부턴 static메서드와 default메서드 추가 가능
//서로 관계없는 클래스들에게 관계를 맺어 줄 수 있는 이점이 있다.
public interface Charger {
	public static final String CONNECTOR = "C타입";
	
	public abstract void ChargerType();
}
```

# interface:SleepMode
{: .notice--warning}

```java
public interface SleepMode {
	public abstract void SleepModeDescription();
}
```

# class:Mac
{: .notice--warning}

```java
public abstract class Mac{
	private String name;
	
	public Mac(String name) {
		super();
		this.name = name;
	}

	@Override
	public String toString() {
		return "Mac [name=" + name + "]";
	}
}
```

# class:Pro13_2017
{: .notice--warning}

```java
public class Pro13_2017 extends Mac implements SleepMode {

	protected Pro13_2017(String name) {
		super(name);
	}

	@Override
	public void SleepModeDescription() {
		System.out.println("잠자기 모드를 통해 부팅 시간을 없애보세요.");
	}
}
```

# class:Pro13_2020
{: .notice--warning}

```java
//인터페이스는 다중상속이 가능
public class Pro13_2020 extends Mac implements SleepMode, Charger {

	protected Pro13_2020(String name) {
		super(name);
	}

	@Override
	public void ChargerType() {
		System.out.println("해당 모델은 " + CONNECTOR + "으로 충전합니다.");
	}

	@Override
	public void SleepModeDescription() {
		System.out.println("더욱 더 쾌적한 잠자기 모드가 가능합니다.");
	}
}
```

# class:Run
{: .notice--warning}

```java
public class Run {
	public static void main(String[] args) {
		Mac[] products = new Mac[2];
		products[0] = new Pro13_2017("Pro13_2017");
		products[1] = new Pro13_2020("Pro13_2020");
		
		for (Mac product : products) {
			ProductDetail(product);
		}
	}
	
	public static void ProductDetail(Mac product) {
		System.out.println("====================");
		System.out.println(product.toString());
		if (product instanceof SleepMode) ((SleepMode)product).SleepModeDescription();
		if (product instanceof Charger) ((Charger)product).ChargerType();
		System.out.println("====================");
	}
}
```