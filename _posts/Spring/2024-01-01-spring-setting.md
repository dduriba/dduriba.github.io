---
title: "Spring 세팅"
categories: Spring
---

# 0. 사용 도구
{: .notice--warning}

OpenJDK11U-jdk_x64_windows_hotspot_11.0.19_7<br>
spring-tool-suite-3.9.20.CI-B2026-e4.22.0-win32-x86_64<br>
lombok.jar (lombok-1.18.24)

version=<br>
java : 11<br>
STS : 3.9.17<br>
tomcat : 9(apache-tomcat-9.0.71) or 10

# 1. OpenJDK 설치
{: .notice--warning}

[https://adoptium.net/temurin/releases/?version=11](https://adoptium.net/temurin/releases/?version=11)

cmd창에서 java -version 명령어를 이용해 설치 확인

# 2. spring-tool-suite 설치
{: .notice--warning}

IDE : eclipse

# 3. lombok 설치
{: .notice--warning}

## 방법 1.
{: .notice--success}

1. cmd창에서 lombok.jar 파일이 있는 경로로 이동해 java -jar lombok.jar 명령어 사용
2. Specify location을 sts.exe로 설정 후 인스톨

## 방법 2.
{: .notice--success}

sts.ini 파일을 열어 끝에<br>
-javaagent:경로\lombok.jar<br>
기입(sts.exe와 같은 경로에 lombok.jar를 두는걸 추천)

# 4. Spring 세팅
{: .notice--warning}

1. Servers 세팅
- Servers의 디폴트 서버 삭제 후 톰캣으로 세팅(버전과 경로 설정)
- Servers의 톰캣을 더블클릭해 Timeouts Start 를 600 로 설정

2. Spring Legacy Project(jsp를 표준 템플릿으로 사용하기 위해) - Spring MVC Project 생성

3. UTF-8 세팅(Window-Preferences)
- General-Workspace -> UTF-8
- Web-HTML, CSS, JSP -> UTF-8

4. pom.xml의 테스트 구간 아래에 롬복 추가 (메이븐 사이트 참고) https://mvnrepository.com/

```xml
<!-- Test -->
<dependency>
	<groupId>junit</groupId>
	<artifactId>junit</artifactId>
	<version>4.7</version>
	<scope>test</scope>
</dependency>   

<!-- Lombok -->
<!-- https://mvnrepository.com/artifact/org.projectlombok/lombok -->
<dependency>
    <groupId>org.projectlombok</groupId>
    <artifactId>lombok</artifactId>
    <version>1.18.30</version>
    <scope>provided</scope>
</dependency>
```

5. src/main/resources/log4j.xml의 Logger 수정

```xml
<root>
	<priority value="trace" />
	<!-- <priority value="debug" /> -->
	<!-- <priority value="warn" /> -->
	<appender-ref ref="console" />
</root>
```

6. src/main/webapp/WEB-INF/web.xml 세팅

```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app version="2.5" xmlns="http://java.sun.com/xml/ns/javaee"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://java.sun.com/xml/ns/javaee https://java.sun.com/xml/ns/javaee/web-app_2_5.xsd">

	<!-- 서블릿에서 사용하던 xml -->
	
	<!-- The definition of the Root Spring Container shared by all Servlets and Filters -->
	<!-- Spring의 Root 세팅을 호출하는 영역 -->
	<context-param>
		<param-name>contextConfigLocation</param-name>
		<param-value>/WEB-INF/spring/root-context.xml</param-value>
	</context-param>
	
	<!-- Creates the Spring Container shared by all Servlets and Filters -->
	<listener>
		<listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
	</listener>

	<!-- DispatcherServlet (Spring의 유일하게 존재하는 Servlet) -->
	<!-- : 모든 사용자의 request를 받아 필요한 핸들러 메서드를 호출 시켜주는 서블릿 -->
	<!-- ※ 주의 : 기술적으로 추가적인 서블릿이 생성 가능하나 절대 생성하지 않음 -->
	<!-- Processes application requests -->
	<servlet>
		<servlet-name>appServlet</servlet-name>
		<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
		<init-param>
			<param-name>contextConfigLocation</param-name>
			<param-value>/WEB-INF/spring/appServlet/servlet-context.xml</param-value>
		</init-param>
		<load-on-startup>1</load-on-startup>
	</servlet>
	
	<!-- 1. 인코딩 세팅 편리하게 설정하는 방법 -->
	<!--  - Spring에서 제공하는 필터를 통해 간편하게 설정할 수 있음 -->
	<filter>
		<filter-name>encodingFilter</filter-name>
		<filter-class>org.springframework.web.filter.CharacterEncodingFilter
		</filter-class>
		<init-param>
			<param-name>encoding</param-name>
			<param-value>UTF-8</param-value>
		</init-param>
		<init-param>
			<param-name>forceEncoding</param-name>
			<param-value>true</param-value>
		</init-param>
	</filter>
	<filter-mapping>
		<filter-name>encodingFilter</filter-name>
		<url-pattern>/*</url-pattern>
	</filter-mapping>
	
	<!-- 2. Session-config web.xml에서 세션에 대한 설정도 가능 -->
	<!-- Session 시간설정 (단위:분) -->
	<session-config>
		<session-timeout>180</session-timeout>
	</session-config>

	<!-- 3. error-page 에러코드에 따른 에러페이지를 설정 가능 -->
	<!-- <error-page> 
			<error-code>401</error-code> 
			<location>/resources/commons/error/serverError.jsp</location> 
		</error-page> -->

	<!-- 4. Welcome-file-list 어플리케이션 요청 시 시작파일을 지정할 수 있음 -->
	<!-- <welcome-file-list> 
			<welcome-file>/home/home.do</welcome-file> 
		</welcome-file-list> -->
	
		
	<servlet-mapping>
		<servlet-name>appServlet</servlet-name>
		<url-pattern>/</url-pattern>
	</servlet-mapping>

</web-app>
```

7. src/main/webapp/WEB-INF/spring/appServlet/servlet-context.xml 세팅

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans:beans xmlns="http://www.springframework.org/schema/mvc"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xmlns:beans="http://www.springframework.org/schema/beans"
	xmlns:context="http://www.springframework.org/schema/context"
	xsi:schemaLocation="http://www.springframework.org/schema/mvc https://www.springframework.org/schema/mvc/spring-mvc.xsd
		http://www.springframework.org/schema/beans https://www.springframework.org/schema/beans/spring-beans.xsd
		http://www.springframework.org/schema/context https://www.springframework.org/schema/context/spring-context.xsd">

	<!-- DispatcherServlet Context: defines this servlet's request-processing infrastructure -->
	<!-- DispatcherServlet 설정을 시작하는 곳 -->
	
	<!-- 스프링 어노테이션을 사용하겠다는 의미로 건들지 않음 -->
	<!-- Enables the Spring MVC @Controller programming model -->
	<annotation-driven />

	<!-- 프로젝트에 관련된 리소스(xml)파일을 로드하는 부분(** => 모든파일을 칭하는 와일드카드) -->
	<!-- Handles HTTP GET requests for /resources/** by efficiently serving up static resources in the ${webappRoot}/resources directory -->
	<resources mapping="/resources/**" location="/resources/" />


	<!-- "/WEB-INF/views/home.jsp" => HomeController.java의 return "home" 해당 -->
	<!-- ViewResolver를 선언하는 xml부, 컨트롤러의 일반 메서드의 리턴값을 view name으로 자동으로 처리해주는 기능 -->
	<!-- Resolves views selected for rendering by @Controllers to .jsp resources in the /WEB-INF/views directory -->
	<beans:bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
		<beans:property name="prefix" value="/WEB-INF/views/" />
		<beans:property name="suffix" value=".jsp" />
	</beans:bean>
	
	<!-- 어노테이션을 자동으로 scan하는 명령, 만일 없으면 어노테이션 사용이 불가능 -->
	<!-- ex) @Controller라는 어노테이션을 찾으면 자동으로 싱글톤(Singleton)으로 객체를 생성하고 관리  -->
	<context:component-scan base-package="com.multi.basic" />
	
	<!-- 아래는 사용자의 특수 세팅 영역 -->
	
</beans:beans>
```

8. src/main/webapp/WEB-INF/spring/root-context.xml 세팅

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://www.springframework.org/schema/beans https://www.springframework.org/schema/beans/spring-beans.xsd">
	
	<!-- Root Context: defines shared resources visible to all other web components -->

	<!-- Spring이 시작될때 최초로 호출되는 XML 파일, 필요한 resource나 bean을 생성할수 있다. -->
	<!-- 용도 : DB 셋팅, Mybatis, 보안, 파일 다운로드, 업로드, log 등의 셋팅을 XML로 정의 가능 -->
		
</beans>
```