---
title:  "Servlet,JSP & Spring"
excerpt: "Servlet,JSP & Spring"
categories: Java
tag: [Servlet, JSP, Spring]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# Servlet
{: .notice--warning .text-center}

서블릿(Servlet)은 자바 언어를 기반으로 하는 서버 측 프로그래밍 기술 중 하나로, 주로 웹 애플리케이션 개발에 사용됩니다. 서블릿은 클라이언트의 요청에 대해 동적으로 서비스를 제공하고, 주로 웹 서버에서 실행됩니다. 아래는 서블릿에 대한 주요 특징과 개념에 대한 간략한 설명입니다.

생명주기(Life Cycle): 서블릿은 자체적인 생명주기를 가지고 있습니다. 이 생명주기에는 초기화(Initialization), 서비스(Service), 소멸(Destruction) 등의 단계가 포함됩니다. 이러한 생명주기 메소드들을 구현하여 서블릿이 특정 이벤트에 어떻게 반응할지를 제어할 수 있습니다.

HTTP 프로토콜 지원: 대부분의 서블릿은 HTTP 프로토콜을 기반으로 동작하며, 주로 웹 브라우저와 통신합니다. 클라이언트의 HTTP 요청을 받아 처리하고, 그에 따른 응답을 생성하여 전송합니다.

자바 언어 기반: 서블릿은 자바 언어로 작성되며, Java EE(Enterprise Edition) 표준의 일부로 제공됩니다. 이는 자바의 풍부한 기능과 객체 지향 프로그래밍의 장점을 활용할 수 있게 합니다.

웹 애플리케이션 구조: 서블릿은 주로 웹 애플리케이션에서 사용되며, 웹 애플리케이션은 여러 서블릿과 JSP(JavaServer Pages) 등의 웹 구성 요소들로 이루어집니다.

스레드 기반 처리: 각 클라이언트 요청에 대해 서블릿 컨테이너는 별도의 스레드를 생성하여 처리합니다. 이를 통해 여러 클라이언트 요청을 동시에 처리할 수 있습니다.

Servlet Container: 서블릿은 서블릿 컨테이너(또는 서블릿 엔진)에서 실행됩니다. 대표적인 서블릿 컨테이너로는 Apache Tomcat, Jetty, 그리고 웹로직 등이 있습니다.

웹 애플리케이션 배포: 서블릿은 WAR(웹 애플리케이션 아카이브) 파일 형태로 패키징되어 배포됩니다. WAR 파일은 여러 서블릿, JSP, 정적 자원 등을 포함하고 있으며, 이를 서블릿 컨테이너에 배포하여 실행할 수 있습니다.

# JSP
{: .notice--warning .text-center}

JavaServer Pages(JSP)는 동적 웹 페이지를 개발하기 위한 기술로, 주로 웹 애플리케이션에서 사용됩니다. JSP는 HTML 코드 안에 자바 코드를 삽입하여 웹 페이지를 동적으로 생성할 수 있게 해주는 서버 측 기술입니다. 아래는 JSP에 대한 주요 특징과 개념에 대한 간략한 설명입니다.

HTML 내부에 자바 코드 삽입: JSP 페이지는 기본적으로 HTML 문서와 유사하며, 그 안에 자바 코드를 삽입하여 동적인 부분을 처리합니다. 자바 코드는 <% %> 태그로 감싸져 있습니다.

```jsp
<html>
<body>
    <% 
        String name = "World";
        out.println("Hello, " + name);
    %>
</body>
</html>
```

JSP 태그: JSP는 여러 종류의 태그를 제공하여 서버 측 로직, 반복문, 조건문, 선언 등을 쉽게 작성할 수 있습니다. 대표적인 JSP 태그로는 <%@ %>(디렉티브), <%= %>(표현식), <%-- --%>(주석) 등이 있습니다.

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<html>
<body>
    <% 
        String name = "World";
        out.println("Hello, " + name);
    %>
</body>
</html>
```

JSP 표현언어(EL, Expression Language): JSP EL은 간단한 표현식 언어로, 변수, 속성, 컬렉션 등에 접근하기 위해 사용됩니다. ${ } 형식으로 표현식을 작성하여 값을 출력하거나 연산을 수행할 수 있습니다.

```jsp
<html>
<body>
    <% 
        String name = "World";
        request.setAttribute("myAttribute", name);
    %>
    <p>Hello, ${myAttribute}</p>
</body>
</html>
```

JSP 컴파일: JSP 페이지는 서버에 의해 컴파일되어 Java Servlet으로 변환되고 실행됩니다. 이렇게 변환된 서블릿은 서블릿 컨테이너에서 실행되어 동적인 콘텐츠를 생성하고 웹 클라이언트에 제공합니다.

웹 애플리케이션에서 사용: JSP는 주로 웹 애플리케이션에서 사용되며, 서블릿과 함께 사용하여 웹 애플리케이션의 프레젠테이션 로직을 구현합니다.
간단한 JSP의 예제는 다음과 같습니다:

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<html>
<body>
    <% 
        String name = "World";
        out.println("Hello, " + name);
    %>
</body>
</html>
```

# Spring
{: .notice--warning .text-center}

Spring은 자바 기반의 오픈 소스 프레임워크로, 엔터프라이즈급 애플리케이션을 개발하기 위한 다양한 모듈과 기능을 제공합니다. Spring은 경량이면서도 강력한 제어 역전(IoC, Inversion of Control)과 의존성 주입(DI, Dependency Injection)을 중심으로 하는 디자인 패턴을 기반으로 합니다. Spring 프레임워크는 주로 서블릿(Servlet)과 JSP(JavaServer Pages)를 기반으로 한 웹 애플리케이션 개발을 위한 프레임워크입니다. Spring은 서블릿과 JSP의 기능을 보완하고 확장하여 개발자가 더 효과적으로 웹 애플리케이션을 구축할 수 있도록 도와줍니다. 아래는 Spring 프레임워크에 대한 주요 특징과 개념에 대한 간략한 설명입니다.

제어 역전 (IoC, Inversion of Control): Spring은 제어의 역전을 지원하여 개발자가 객체의 생명주기와 관리를 할 필요 없이, Spring 컨테이너가 객체를 생성하고 관리합니다. 이를 통해 객체 간의 결합도를 낮추고 유연한 애플리케이션을 구현할 수 있습니다.

의존성 주입 (DI, Dependency Injection): Spring은 의존성 주입을 통해 객체 간의 의존성을 컨테이너가 주입해줍니다. 이를 통해 코드의 유연성과 테스트 용이성을 향상시키며, 객체 간의 결합도를 낮춥니다.

모듈화: Spring은 각종 기능을 제공하는 다양한 모듈로 구성되어 있습니다. 예를 들어, Spring MVC는 웹 애플리케이션의 모델-뷰-컨트롤러 아키텍처를 지원하며, Spring Data는 데이터 액세스를 단순화하는데 사용됩니다.

스프링 컨테이너: Spring은 여러 가지 컨테이너를 제공하는데, 그 중에서도 가장 널리 사용되는 것은 ApplicationContext입니다. ApplicationContext는 Bean의 생성, 관리, 생명주기 등을 관리하며, 애플리케이션의 핵심적인 컨테이너 역할을 합니다.

스프링 MVC: Spring MVC는 모델-뷰-컨트롤러 아키텍처를 제공하여 웹 애플리케이션을 구축하는 데 사용됩니다. 웹 요청과 응답을 처리하고, MVC 패턴을 따라 비즈니스 로직과 사용자 인터페이스를 분리합니다.

트랜잭션 관리: Spring은 선언적 트랜잭션 관리를 제공하여 개발자가 트랜잭션 처리에 대한 세부 사항을 명시하지 않고도 트랜잭션을 관리할 수 있게 합니다.

AOP (Aspect-Oriented Programming): Spring은 관점 지향 프로그래밍을 지원하여, 핵심 비즈니스 로직과 횡단 관심 사항(로깅, 트랜잭션 관리 등)을 분리할 수 있게 합니다.

데이터 액세스 지원: Spring은 JDBC, ORM 프레임워크(예: Hibernate), 데이터 액세스 추상화를 통해 데이터베이스와의 상호 작용을 단순화하는 기능을 제공합니다.

보안: Spring Security는 보안 기능을 제공하여 인증과 권한 부여를 관리합니다.