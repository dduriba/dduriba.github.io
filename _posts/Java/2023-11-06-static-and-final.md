---
title:  "Static, Final"
categories: Java
---

# 초기화 블록
{: .notice--warning}

Java에서는 객체 생성자보다 먼저 실행되는 두 가지 종류의 블록이 있습니다. 

## 1. 인스턴스 초기화 블록(Instance Initialization Block)
{: .notice--success}

- 인스턴스 초기화 블록은 객체가 생성될 때 인스턴스 변수의 초기화를 위해 사용됩니다.
- 객체가 생성될 때마다 실행되며, 생성자보다 먼저 실행됩니다.
- 클래스 내에서 중괄호 {}를 사용하여 정의되며, 인스턴스 변수를 초기화하는 코드를 포함할 수 있습니다.

```java
public class MyClass {
    // 인스턴스 초기화 블록
    {
        // 인스턴스 변수 초기화 코드
    }

    // 생성자 및 다른 멤버 변수, 메서드 등...
}
```

## 1. 정적 초기화 블록(Static Initialization Block)
{: .notice--success}

- 정적 초기화 블록은 클래스가 로딩될 때 실행되며, 클래스 변수의 초기화를 위해 사용됩니다.
- 클래스가 처음 로딩될 때 한 번만 실행되며, 인스턴스의 생성과는 무관합니다.
- static 키워드를 사용하여 정의됩니다.

```java
public class MyClass {
    // 정적 초기화 블록
    static {
        // 클래스 변수 초기화 코드
    }

    // 다른 정적 멤버 변수, 메서드 등...
}
```

인스턴스 초기화 블록은 객체가 생성될 때 실행되고, 정적 초기화 블록은 클래스가 로딩될 때 실행됩니다.

# Static 변수 (클래스 변수)
{: .notice--warning}

여러 인스턴스에서 공유되는 값을 유지하고 싶을 때. 모든 객체가 동일한 값을 공유하며, 객체 간에 상태를 공유해야 하는 경우에 사용됩니다.

```java
public class Example {
    static int count = 0;
}
```

# Static 메서드
{: .notice--warning}

객체의 인스턴스와 관계없이 클래스 레벨에서 독립적으로 동작해야 할 때. 주로 유틸리티 메서드나 헬퍼 메서드로 활용됩니다.

```java
public class MathUtil {
    public static int add(int a, int b) {
        return a + b;
    }
}
```

# Static 내부 클래스
{: .notice--warning}

외부 클래스의 인스턴스와 독립적인 내부 클래스를 만들 때. 주로 외부 클래스와 강한 결합이 필요하지 않을 때 사용됩니다.

```java
public class OuterClass {
    static class StaticInnerClass {
        // 내부 클래스의 내용
    }
}
```

# Static Import
{: .notice--warning}

특정 클래스의 static 멤버를 사용할 때, 클래스 이름을 지정하지 않고 직접 멤버에 접근할 수 있도록 해줍니다. 코드의 가독성을 높일 수 있습니다.

```java
import static java.lang.Math.PI;

public class Circle {
    double calculateArea(double radius) {
        return PI * radius * radius;
    }
}
```

# Static final 상수
{: .notice--warning}

변하지 않는 상수 값을 정의할 때. 상수 값이 여러 곳에서 참조되는 경우, 중복을 방지하고 유지보수성을 높입니다.

```java
public class Constants {
    static final int MAX_VALUE = 100;
}
```

# Static 메서드 인터페이스
{: .notice--warning}

인터페이스와 관련된 유틸리티 메서드를 정의할 때. Java 8 이후에 인터페이스에 정적 메서드를 추가할 수 있게 되었습니다.

```java
public interface MyInterface {
    static void staticMethod() {
        // 인터페이스의 정적 메서드
    }
}
```

# 변수에 대한 final 키워드
{: .notice--warning}

변수에 final 키워드가 사용되면 해당 변수는 상수로 취급되어 값을 한 번 할당한 후에는 변경할 수 없습니다.

```java
final int myConstant = 10;
// myConstant = 20; // 이 부분은 컴파일 오류가 발생합니다.
```

# 메서드에 대한 final 키워드
{: .notice--warning}

메서드에 final 키워드가 사용되면 해당 메서드는 하위 클래스에서 오버라이드될 수 없습니다.

```java
public class Parent {
    public final void myMethod() {
        // 메서드 내용
    }
}

public class Child extends Parent {
    // 오버라이드 시도
    // 컴파일 오류 발생
    // public void myMethod() { }
}
```

# 클래스에 대한 final 키워드
{: .notice--warning}

클래스에 final 키워드가 사용되면 해당 클래스는 상속될 수 없습니다.

```java
public final class MyFinalClass {
    // 클래스 내용
}

// 아래와 같이 상속 시도
// 컴파일 오류 발생
// public class ChildClass extends MyFinalClass { }
```