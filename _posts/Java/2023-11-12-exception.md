---
title:  "Exception"
excerpt: "exception"
categories: Java
tag: [exception]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# Exception이란?
{: .notice--warning .text-center}

Exception은 프로그램 실행 중에 예상치 못한 상황이나 오류가 발생했을 때, 그 정보를 전달하고 처리하는 Java에서의 메커니즘입니다. 이러한 상황을 처리함으로써 프로그램은 예외적인 상황에서도 계속해서 실행될 수 있도록 합니다.

# Exception의 계층 구조
{: .notice--warning .text-center}

```plaintext
Object
  └── Throwable
      ├── Error
      └── Exception
```

1) Object:<br>
&nbsp;- 자바의 모든 클래스는 Object 클래스를 상속받습니다.

2) Throwable:<br>
&nbsp;- Throwable 클래스는 모든 예외 클래스와 에러 클래스의 최상위 클래스입니다.<br>
&nbsp;- Throwable 클래스는 예외를 나타내는 데 필요한 메커니즘을 제공합니다.

3) Error:<br>
&nbsp;- Error 클래스는 프로그램이 복구할 수 없는 심각한 오류를 나타냅니다.<br>
&nbsp;- 예를 들어, OutOfMemoryError나 StackOverflowError 등이 Error 클래스에 속합니다.<br>
&nbsp;- 프로그래머가 직접 처리하기 어려운 상황에서 발생하며, 보통 시스템 수준의 문제를 나타냅니다.

4) Exception:<br>
&nbsp;- Exception 클래스는 프로그램이 처리할 수 있는 예외 상황을 나타냅니다.<br>
&nbsp;- RuntimeException을 포함하여 다양한 예외들이 Exception 클래스에서 파생됩니다.<br>
&nbsp;- 예외 처리를 통해 프로그램이 비정상적인 상황에서도 제어를 유지하고 복구할 수 있도록 합니다.

```plaintext
Object
  └── Throwable
      ├── Error
      └── Exception
          ├── RuntimeException
          │   ├── ArithmeticException
          │   ├── NullPointerException
          │   ├── ArrayIndexOutOfBoundsException
          │   └── 기타 등등...
          ├── IOException
          │   ├── FileNotFoundException
          │   ├── EOFException
          │   ├── SocketException
          │   └── 기타 등등...
          ├── SQLException
          ├── ClassNotFoundException
          ├── ParseException
          ├── InterruptedException
          ├── FileNotFoundException
          └── 기타 예외 클래스들...
```

&nbsp;- RuntimeException 및 그 하위 클래스들은 주로 프로그래머의 오류나 잘못된 사용에 의한 예외를 나타냅니다. 이러한 예외들은 명시적인 예외 처리를 강제하지 않습니다. 하지만, 그 외의 Exception 클래스와 그 하위 클래스들은 명시적인 예외 처리를 강제합니다.

# Checked Exception, Unchecked Exception
{: .notice--warning .text-center}

## Checked Exception
{: .notice--success .text-center}

- 컴파일 시점에서 확인되는 예외로, 예외를 처리(try-catch 블록으로 감싸거나 throws 선언을 통해 예외를 위로 전파)하지 않으면 컴파일 오류가 발생합니다.
- Exception 클래스를 상속받은 모든 예외 중에서 RuntimeException 클래스를 상속받지 않은 것들이 여기에 속합니다.
- 입출력 작업, 데이터베이스 연결, 네트워크 통신 등과 관련된 예외들이 주로 이에 해당합니다.

1. IOException : 파일 입출력과 관련된 예외를 처리하는데 사용됩니다. (주요 하위 예외들 : FileNotFoundException, EOFException, SocketException 등)
2. SQLException : 데이터베이스와 관련된 예외를 처리하는데 사용됩니다.
3. ClassNotFoundException : 클래스를 찾을 수 없는 예외를 처리하는데 사용됩니다.
4. ParseException : 날짜나 숫자 등을 파싱하는 과정에서 발생하는 예외를 처리하는데 사용됩니다.
5. InterruptedException : 스레드가 interrupt 되었을 때 발생하는 예외를 처리하는데 사용됩니다.

## Unchecked Exception
{: .notice--success .text-center}

- 컴파일러가 예외 처리 여부를 확인하지 않는 예외로, 개발자의 부주의 또는 프로그램의 논리적 오류로 인해 발생합니다.
- RuntimeException 클래스 및 그 하위 클래스들이 여기에 속합니다.
- 배열 인덱스 오버플로우, 캐스팅 오류, 산술 연산 오류 등이 여기에 해당합니다.

1. ArithmeticException : 산술 연산 중에 발생하는 예외를 처리하는데 사용됩니다.
2. NullPointerException : 객체 참조가 없는 상태에서 발생하는 예외를 처리하는데 사용됩니다.
3. ArrayIndexOutOfBoundsException : 배열의 인덱스가 범위를 벗어나는 경우 발생하는 예외를 처리하는데 사용됩니다.
4. ClassCastException : 잘못된 형변환 시도 시 발생하는 예외를 처리하는데 사용됩니다.
5. NumberFormatException : 숫자로 변환할 수 없는 문자열을 변환하려고 시도할 때 발생하는 예외를 처리하는데 사용됩니다.
6. IllegalArgumentException : 메소드에 전달된 인수가 유효하지 않은 경우 발생하는 예외를 처리하는데 사용됩니다.
7. IllegalStateException : 메소드가 객체의 현재 상태에서 호출될 수 없는 경우 발생하는 예외를 처리하는데 사용됩니다.

이 외에도 많은 예외 클래스들이 있으며, 각각 특정한 예외 상황에서 발생하는 문제를 다룹니다. 위에서 나열한 것은 일부 주요한 Exception 클래스들과 그 하위 예외들입니다.

# Exception 사용 예시
{: .notice--warning .text-center}

## try-catch, finally, printStackTrace()
{: .notice--success .text-center}

```java
public static void main(String[] args) {
    try {
        int result1 = divide(10, 0); // ArithmeticException 발생

        String str = null;
        int length = str.length(); // NullPointerException 발생
    } catch (ArithmeticException arithmeticException) {
        System.out.println("ArithmeticException Caught: " + arithmeticException.getMessage());
        arithmeticException.printStackTrace();
    } catch (NullPointerException nullPointerException) {
        System.out.println("NullPointerException Caught: " + nullPointerException.getMessage());
        nullPointerException.printStackTrace();
    } finally { 
        System.out.println("Finally Block");
    }
}

public static int divide(int a, int b) {
    return a / b;
}
```

1) try 블록 :<br>
&nbsp;- try 블록은 예외가 발생할 가능성이 있는 코드를 감싸는 블록입니다.<br>
&nbsp;- try 블록 내에서 예외가 발생하면 예외 처리 부분으로 이동하고 남은 try 블록의 명령문들은 실행되지 않습니다.

2) catch 블록 :<br>
&nbsp;- catch 블록은 try 블록에서 발생한 예외를 처리하는 부분입니다.<br>
&nbsp;- try 블록에서 발생한 예외의 종류에 따라 적절한 catch 블록이 선택되어 실행됩니다.<br>
&nbsp;- 여러 개의 catch 블록을 사용하여 다양한 종류의 예외를 처리할 수 있습니다.

3) finally 블록 :<br>
&nbsp;- finally 블록은 예외 발생 여부와 관계없이 항상 실행되는 부분입니다.<br>
&nbsp;- try 블록에서 예외가 발생하더라도 finally 블록은 반드시 실행됩니다.
주로 리소스의 해제나 마무리 작업을 위해 사용됩니다. try-catch 블록에서 return 명령이 있어도 실행됩니다.

4) printStackTrace 메서드 :<br>
&nbsp;- printStackTrace는 예외의 스택 트레이스(StackTrace)를 출력하는 메서드입니다.<br>
&nbsp;- 스택 트레이스는 예외가 발생한 위치부터 예외를 던진 지점까지의 호출 스택 정보를 나타냅니다.<br>
&nbsp;- 주로 디버깅이나 예외 정보를 기록할 때 사용됩니다.

## throw, throws
{: .notice--success .text-center}

1) throw :<br>
&nbsp;- throw 키워드는 예외를 명시적으로 발생시킬 때 사용됩니다. 개발자가 직접 예외를 발생시키는 데 사용됩니다.

2) throws :<br>
&nbsp;- throws 키워드는 메소드 선언부에서 해당 메소드가 어떤 종류의 예외를 던질 수 있는지 명시하는 데 사용됩니다.

```java
public static void main(String[] args) {
    try {
        processFile("example.txt");
    } catch (FileNotFoundException e) {
        System.out.println("Caught Exception: " + e.getMessage());
    }
}

public static void processFile(String filename) throws FileNotFoundException {
    // 파일 처리 로직
    // 파일이 없을 경우 FileNotFoundException을 던짐
    throw new FileNotFoundException("File not found: " + filename);
}
```

위의 예제에서 processFile 메소드는 파일이 없을 경우 FileNotFoundException을 던집니다. 메소드 선언부에서는 throws 키워드를 사용하여 해당 예외를 처리할 것임을 나타냅니다.

종합하면, throw는 예외를 발생시키는 데 사용되고, throws는 메소드에서 예외를 처리하지 않고 상위 호출자에게 예외를 전달할 때 사용됩니다.

## 사용자 정의 예외 클래스
{: .notice--success .text-center}

```java
// 사용자 정의 예외 클래스
class CustomException extends Exception {
    public CustomException(String message) {
        super(message);
    }
}

public class CustomExceptionExample {
    public static void main(String[] args) {
        try {
            validateInput(25);
            validateInput(10); // 예외 발생
        } catch (CustomException e) {
            System.out.println("Caught Custom Exception: " + e.getMessage());
        }
    }

    // 사용자 정의 예외를 던지는 메소드
    public static void validateInput(int value) throws CustomException {
        if (value < 18) {
            throw new CustomException("Input value must be 18 or older.");
        } else {
            System.out.println("Input is valid.");
        }
    }
}
```