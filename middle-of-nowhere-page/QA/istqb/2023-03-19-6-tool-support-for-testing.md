---
title: "[Foundation Level] 제 6장. 테스트 지원 도구"
excerpt: "Foundation Level Chapter.6 Tool Support for Testing"
categories: ISTQB
tag: [ISTQB, Foundation Level]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# 6.1 테스트 도구 고려 사항 (Test tool considerations)
{: .notice--warning .text-center}

테스트 도구는 하나 이상의 테스팅 활동을 지원하는데 사용할 수 있으며, 다음과 같은 종류가 있다:
- 테스팅에 직접 사용하는 도구 (예: 테스트 실행 도구, 테스트 데이터 준비 도구)
- 요구사항, 테스트 케이스, 테스트 프로세스, 자동 테스트 스크립트, 테스트 결과, 테스트 데이터, 결함을 관리하고, 테스트 실행 보고와 모니터링을 지원하는 도구
- 분석(analysis)과 평가(evaluation)에 사용하는 도구
- 테스팅을 지원하는 모든 도구 (이런 의미에서 스프레드시트도 테스트 도구임)

## 6.1.1 테스트 도구의 분류 (Test Tool Classification)
{: .notice--success}

<span style="color:green">(K2) 테스트 도구를 사용 목적과 지원하는 테스트 활동에 따라 구별할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">테스트 도구는 정황에 따라 다음과 같은 하나 이상의 목적이 있다:</span>
- <span style="background-color:rgb(237,220,195);">반복적인 작업이나 수동으로 진행했을 때 상당한 리소스를 필요로 하는 작업(예: 테스트 실행, 리그레션 테스팅)을 자동화해서 테스트 활동의 효율성을 높인다.</span>
- <span style="background-color:rgb(237,220,195);">테스트 프로세스 전반에 걸쳐 수동 테스트 활동을 지원해서 테스트 활동의 효율성을 높인다 (1.4 절 참조).</span>
- <span style="background-color:rgb(237,220,195);">테스팅의 일관성과 결함 재현성 향상으로 테스트 활동의 품질을 향상시킨다.</span>
- <span style="background-color:rgb(237,220,195);">수동으로 실행할 수 없는 활동을 자동화(예: 대규모 성능 테스팅)한다.</span>
- <span style="background-color:rgb(237,220,195);">테스팅의 신뢰성을 향상(예: 대규모 데이터 비교 자동화나 동작 시뮬레이션)한다.</span>

도구는 목적, 가격, 라이선스 모델(예: 상용이나 오픈소스), 사용된 기술에 따라 분류할 수 있다. 본 실러버스에서는 테스트 도구가 지원하는 활동에 따라 도구를 분류한다.<br>
어떤 도구는 명확하게 하나의 테스트 활동만을 지원하고 어떤 도구는 하나 이상의 활동을 지원하기도 한다. 본 실러버스에서 분류는 가장 밀접하게 관련 있는 활동을 기준으로 했다. 여러 도구가 함께 동작하도록 설계된 도구를 제공하는 공급자는 통합된 하나의 스위트를 제공할 수 있다. <span style="background-color:rgb(237,220,195);">도구 자체가 테스트의 실제 결과에 영향을 준다는 의미에서 침입적(Intrusive) 도구도 있다. 예를 들어 성능 테스팅 도구가 실행하는 추가 명령 때문에 애플리케이션의 실제 반응 시간이 달라질 수 있고 코드 커버리지 도구를 사용하면 달성하는 코드 커버리지의 측정치가 달라질 수 있다. 이러한 침입적 도구를 사용해 달라진 결과를 <span style="background-color:rgb(207,228,207);">탐사 효과(Probe effect)</span>라고 부른다.</span><br>
또 컴포넌트 테스트나 컴포넌트 통합 테스트 중 개발자에게 더 적절한 도구도 있다. 이런 도구는 아래에 “ 개발자 지원”으로 표기되어 있다.

**<span style="background-color:rgb(207,228,207);">테스팅 및 테스트웨어 관리 지원 도구 (Tool support for management of testing and testware)</span>**<br>
<span style="color:blue">관리 도구는 소프트웨어 수명주기 전체에 걸쳐 모든 테스팅 활동에 사용할 수 있다.</span><br>
테스팅 및 테스트웨어 관리를 지원하는 도구는 다음과 같다:
- <span style="background-color:rgb(237,220,195);">테스트 관리 도구와 애플리케이션 수명주기 관리 도구 (ALM, application lifecycle management tool)</span>
- <span style="background-color:rgb(237,220,195);">요구사항 관리 도구 (예: 테스트 대상의 추적성 관리)</span>
- <span style="background-color:rgb(237,220,195);">결함 관리 도구</span>
- <span style="background-color:rgb(237,220,195);">형상 관리 도구</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">지속적인 통합 도구 (개발자 지원)</span></span>

**<span style="background-color:rgb(207,228,207);">정적 테스팅 지원 도구 (Tool support for static testing)</span>**<br>
정적 테스팅 도구는 제 3 장의 정적 테스팅과 장점에 연관돼 있으며, 다음과 같은 도구가 있다:
- <span style="background-color:rgb(237,220,195);"><span style="color:red">정적 분석 도구 (개발자 지원)</span></span>

**<span style="background-color:rgb(207,228,207);">테스트 설계 및 구현 지원 도구 (Tool support for test design and implementation)</span>**<br>
<span style="color:blue">테스트 설계 도구는 테스트 설계와 구현 단계에서 작업 산출물(예: 테스트 케이스, 테스트 프로시저, 테스트 데이터)을 유지보수하는 데 도움을 주며,</span> 다음과 같은 도구가 있다:
- <span style="background-color:rgb(237,220,195);">모델 기반 테스팅 도구</span>
- <span style="background-color:rgb(237,220,195);">테스트 데이터 준비 도구</span>

테스트 설계와 구현을 지원하는 도구가 테스트 실행과 로깅을 지원하기도 하고 테스트 설계와 구현 도구가 테스트 실행과 로깅을 지원하는 다른 도구에 결과를 제공하기도 한다.

**<span style="background-color:rgb(207,228,207);">테스트 실행 및 로깅 지원 도구 (Tool support for test execution and logging)</span>**<br>
테스트 실행과 로깅 활동을 지원하는 도구는 다양하며 아래와 같은 종류가 있다:
- <span style="background-color:rgb(237,220,195);">테스트 실행 도구 (예: 리그레션 테스트 수행)</span>
- <span style="background-color:rgb(237,220,195);">커버리지 도구 (예: 요구사항 커버리지, <span style="color:red">코드 커버리지 (개발자 지원)</span>)</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">테스트 하네스 (개발자 지원)</span></span>

**<span style="background-color:rgb(207,228,207);">성능 측정과 동적 분석 지원 도구 (Tool support for performance measurement and dynamic analysis)</span>**<br>
<span style="color:blue">성능 측정 및 동적 분석 도구는 성능 및 부하 테스트 활동이 수동으로는 효과적으로 수행할 수 없기 때문에 이를 지원하는 데 필수적이다.</span><br>
관련 도구의 예는 아래와 같다:
- <span style="background-color:rgb(237,220,195);">성능 테스팅 도구</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">동적 분석 도구 (개발자 지원)</span></span>

**<span style="background-color:rgb(207,228,207);">특수 목적 테스팅 지원 도구 (Tool support for specialized testing needs)</span>**<br>
일반적인 테스트 프로세스를 지원하는 도구 외에 비기능적 특징(non-functional characteristics)을 커버하기 위한 보다 특정적인 테스팅을 지원하는 도구도 있다.

## 6.1.2 테스트 자동화의 효과와 리스크 (Benefits and Risks of Test Automation)
{: .notice--success}

<span style="color:green">(K1) 테스트 자동화의 효과와 리스크를 식별할 수 있다.</span>

단순히 도구를 도입했다고 성공이 보장되는 건 아니다. 조직에 새로운 도구를 도입할 때마다 실질적이고 지속적인 가치를 전달하려면 노력이 필요하다. 테스팅에서 도구를 사용해 잠재적인 가치를 얻을 기회가 있는 반면 리스크도 존재한다. 특히 테스트 자동화로 자주 지칭하는 테스트 실행 도구가 특히 그렇다.<br>
<span style="background-color:rgb(207,228,207);">테스트 실행 지원 도구는 아래와 같은 잠재적 가치가 있다:</span>
- <span style="background-color:rgb(237,220,195);">반복적인 수동 업무 (예: 리그레션 테스트 수행, 환경 구축/해체 작업, 같은 테스트 데이터 재입력, 코딩 표준 준수 여부 점검 등)의 감소로 시간 절약</span>
- <span style="background-color:rgb(237,220,195);">월등한 일관성과 반복성 제공 (예: 일관성 있는 테스트 데이터 생성, 같은 순서와 간격의 테스트 실행, 요구사항으로부터의 지속적인 테스트 도출)</span>
- <span style="background-color:rgb(237,220,195);">보다 객관적인 평가 기준 제공 (예: 정적 테스팅 측정치, 커버리지)</span>
- <span style="background-color:rgb(237,220,195);">테스팅 관련 정보에 접근이 쉬움 (예: 테스트 진척도, 결함율, 성능 통계와 그래프)</span>

<span style="background-color:rgb(207,228,207);">테스팅 지원 도구는 아래와 같은 잠재적인 리스크가 있다:</span>
- <span style="background-color:rgb(237,220,195);">도구에 대한 비현실적인 기대 (예: 도구의 기능과 사용성)</span>
- <span style="background-color:rgb(237,220,195);">초기 도구 도입에 필요한 시간, 비용, 노력에 대한 과소 평가 (예: 교육, 외부 전문가 비용)</span>
- <span style="background-color:rgb(237,220,195);">도구로 의미 있고 지속적인 효과를 얻는 데 필요한 시간과 노력을 과소평가 (예: 테스트 프로세스의 수정과 도구의 사용법에 대한 지속적인 개선)</span>
- <span style="background-color:rgb(237,220,195);">도구가 생성하는 테스트 작업 산출물을 유지하기 위한 노력의 과소평가</span>
- <span style="background-color:rgb(237,220,195);">도구에 대한 지나친 의존 (테스트 설계나 실행을 대체한다고 생각하거나 수동 테스팅이 더 효과적인 경우에 자동 테스팅 사용)</span>
- <span style="background-color:rgb(237,220,195);">테스트 작업 산출물에 대한 버전의 관리 소홀</span>
- <span style="background-color:rgb(237,220,195);">요구사항 관리 도구, 형상 관리 도구, 결함 관리 도구, 다수의 공급 업체에서 제공하는 도구 환경에서 주요 도구 간의 관계와 상호운용성 이슈를 관리하지 않음</span>
- <span style="background-color:rgb(237,220,195);">도구 공급 업체의 폐업, 해당 도구의 판매 중단, 해당 도구가 다른 공급 업체에 매각될 수 있음</span>
- <span style="background-color:rgb(237,220,195);">지원, 업그레이드, 결함 수정에 대한 공급 업체의 부적절한 대응</span>
- <span style="background-color:rgb(237,220,195);">오픈소스 프로젝트는 연기되거나 중단될 수 있음</span>
- <span style="background-color:rgb(237,220,195);">도구가 새로운 플랫폼이나 기술을 지원하지 않음</span>
- <span style="background-color:rgb(237,220,195);">도구의 소유권이 명확하지 않음 (예: 멘토링, 업데이트 등의 어려움)</span>

## 6.1.3 테스트 실행 및 테스트 관리 도구 고려 사항 (Special Considerations for Test Execution and Test Management Tools)
{: .notice--success}

<span style="color:green">(K1) 테스트 실행 및 테스트 관리 도구 사용 시 특별히 고려해야 하는 사항을 기억할 수 있다.</span>

조직에 테스트 실행과 테스트 관리 도구를 도입하고 통합해 큰 문제없이 성공적으로 도구를 구현하기 위해 고려해야 할 사항이 많다.

**<span style="background-color:rgb(207,228,207);">테스트 실행 도구 (Test execution tools)</span>**<br>
<span style="color:blue">테스트 실행 도구는 자동화 테스트 스크립트를 사용해 테스트를 실행한다.</span> 보통 이런 종류의 도구에서 의미 있는 가치를 끌어내는 데는 상당한 노력이 필요하다.
- <span style="background-color:rgb(237,220,195);">캡처 기반 테스트 접근법 (Capturing test approach):</span> <span style="background-color:rgb(242,213,214);">테스터의 수동적인 조작을 녹화해 테스트를 캡처하는 것은 매력적으로 보일 수 있지만 이러한 접근 방식은 테스트 스크립트의 수가 많을 경우 적절하지 않다. 캡처한 스크립트마다 특정 데이터와 행위를 1 차원적으로 표현하고 있기 때문에 미처 예상하지 못한 이벤트가 발생하면 취약할 수 있으며, 시스템의 사용자 인터페이스가 시간이 지남에 따라 바뀌게 되면 스크립트도 그에 맞게 계속해서 유지보수를 해 줄 필요가 있다.</span>
- <span style="background-color:rgb(237,220,195);">데이터 주도 테스트 접근법 (Data-driven test approach):</span> <span style="background-color:rgb(242,213,214);">이 접근법은 테스트 입력값과 기대 결과값을 보통 스프레드시트(spreadsheet)에 저장하고 더 많은 공통 스크립트를 활용해 해당 테스트 데이터를 읽어 들여 동일한 테스트 스크립트를 매번 다른 데이터로 반복적으로 실행한다.</span>
- <span style="background-color:rgb(237,220,195);">키워드 주도 테스트 접근법 (keyword-driven test approach):</span> <span style="background-color:rgb(242,213,214);">이 접근법은 해야 할 행동을 설명하는 키워드(액션 워드라고도 함)를 공통 스크립트가 처리해 키워드 스크립트를 호출(call)한다. 키워드 스크립트는 연관된 테스트 데이터를 처리한다.</span>

<span style="background-color:rgb(232,233,234);"><span style="color:blue">위에서 언급한 접근법은 스크립트 언어 전문가(테스터, 개발자 또는 테스트 자동화 전문가)가 필요하다. 데이터 주도 또는 키워드 주도 테스트 접근법을 사용하는 경우 스크립팅 언어에 익숙하지 않은 테스터도 이렇게 사전 정의된 스크립트에 대한 테스트 데이터나 키워드를 작성함으로써 테스팅에 기여할 수 있다.</span> 사용한 스크립트 기술과 상관없이 각 테스트의 기대 결과와 실제 결과를 비교할 필요가 있다. 동적(테스트 실행 도중)으로 아니면 차후(실행 후) 비교할 수 있다.<br>
데이터 주도와 키워드 주도 테스트 접근법에 대한 자세한 내용과 예는 (ISTQB-CTAL-TAE, Fewster 1999 및 Buwalda 2001)에 나와 있다.<br>
<span style="color:blue">모델 기반 테스팅(MBT, Model based testing) 도구는 기능 명세를 액티비티 다이어그램과 같은 모델의 형태로 표현할 수 있도록 해준다. 일반적으로 이 작업은 시스템 설계자가 수행한다. MBT 도구는 모델을 해석해 테스트 케이스 명세를 생성하고, 생성한 명세는 테스트 관리 도구에 저장하거나 테스트 실행 도구로 실행한다 (ISTQB- CTFL-MBT 참조).</span></span>

**<span style="background-color:rgb(207,228,207);">테스트 관리 도구 (Test management tools)</span>**<br>
<span style="background-color:rgb(237,220,195);">테스트 관리 도구는 아래와 같은 여러 이유로 다른 도구나 스프레드시트와 연동해야 하는 경우가 많다:</span>
- <span style="background-color:rgb(242,213,214);">필요한 정보를 생성하기 위해</span>
- <span style="background-color:rgb(242,213,214);">요구사항 관리 도구에 저장된 요구사항과의 추적성을 지속적으로 유지하기 위해</span>
- <span style="background-color:rgb(242,213,214);">형상 관리 도구에 저장된 테스트 대상 버전 정보와 연결하기 위해</span>

<span style="color:blue">이는 통합 도구(예: ALM, Application Lifecycle Management 애플리케이션 수명주기 관리)를 사용할 때 특히 중요하다. 애플리케이션 수명주기 관리 도구에는 조직 내 다양한 그룹에서 사용하는 기타 모듈(예: 프로젝트 일정과 예산 정보)뿐 아니라 테스트 관리 도구 모듈도 들어있다.</span>

# 6.2 도구의 효과적인 사용 (Effective use of tools)
{: .notice--warning .text-center}

## 6.2.1 도구 선택의 주요 원칙 (Main Principles for Tool Selection)
{: .notice--success}

<span style="color:green">(K1) 도구 선택의 주요 원칙을 식별할 수 있다.</span>

<span style="background-color:rgb(207,228,207);"><span style="color:blue">조직에 맞는 도구를 선택</span>하는데 주요 고려 사항은 다음과 같다:</span>
- <span style="background-color:rgb(237,220,195);">조직의 강점, 약점 등 성숙도 수준 평가</span>
- <span style="background-color:rgb(237,220,195);">도구의 지원으로 테스트 프로세스 개선 기회 식별</span>
- <span style="background-color:rgb(237,220,195);">테스트 대상이 이용하는 기술을 이해해 테스트 대상과 호환 가능한 도구 선택</span>
- <span style="background-color:rgb(237,220,195);">호환과 통합이 가능한 도구 확인을 위해, 조직에서 이미 사용하고 있는 빌드와 지속적인 통합 도구 이해</span>
- <span style="background-color:rgb(237,220,195);">명확한 요구사항과 객관적인 기준에 맞는 도구 평가</span>
- <span style="background-color:rgb(237,220,195);">도구를 일정 기간 무료로 시험해 볼 수 있는지 여부</span>
- <span style="background-color:rgb(237,220,195);">공급자 평가(교육, 지원, 상용 제품) 또는 비 상업적(예: 오픈소스) 도구 지원 평가</span>
- <span style="background-color:rgb(237,220,195);">조직이 요구하는 도구 사용 코칭과 멘토 요구사항 식별</span>
- <span style="background-color:rgb(237,220,195);">도구를 직접 사용할 사람의 테스팅(테스트 자동화 포함) 역량을 고려한 훈련 수요 확인</span>
- <span style="background-color:rgb(237,220,195);">다양한 라이센스 모델(예: 상용 제품이나 오픈소스)의 장단점 고려</span>
- <span style="background-color:rgb(237,220,195);">필요 시 구체적인 비즈니스 사례에 근거해 비용 대비 효과 추정</span>

<span style="background-color:rgb(237,220,195);">마지막으로 <span style="color:blue"><span style="background-color:rgb(207,228,207);">사전 검증(proof-of-concept)</span>을 진행</span>해야 한다. 사전 검증으로 테스트 대상 소프트웨어와 현재 인프라 환경에서 도구가 효과적으로 동작하는지 확인하고 필요한 경우에는 효율적으로 도구를 사용하는 데 필요한 요구사항을 식별한다.</span>

## 6.2.2 도구 도입을 위한 파일럿 프로젝트 (Pilot Projects for Introducing a Tool into an Organization)
{: .notice--success}

<span style="color:green">(K1) 도구를 도입할 때 파일럿 프로젝트의 목적을 상기할 수 있다.</span>

<span style="color:blue">도구 선택과 사전 검증이 성공적으로 끝난 다음 선택한 도구를 조직에 도입하는 시점은 주로 <span style="background-color:rgb(207,228,207);">파일럿 프로젝트(pilot project)</span>이다.</span><br>
<span style="background-color:rgb(237,220,195);">파일럿 프로젝트의 목적은 다음과 같다:</span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">깊이 있는 도구 지식의 습득, 장단점 모두 이해</span></span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">도구를 기존 프로세스와 프랙티스에 어떻게 적용할지 평가하고 무엇을 변경할지 결정</span></span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">도구와 테스트 작업 산출물의 사용, 관리, 저장, 유지보수에 대한 기준 결정 (예: 파일과 테스트를 명명하는 규칙 결정, 코딩 표준 선택, 라이브러리 생성, 테스트 스위트의 모듈성 정의)</span></span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">목표한 가치를 적절한 비용으로 달성할 수 있는지 평가</span></span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">도구에서 수집하고 보고하기를 희망하는 메트릭을 이해하고 그런 메트릭을 도출하고 보고할 수 있도록 도구를 설정</span></span>

## 6.2.3 도구 성공 요인 (Success Factors for Tools)
{: .notice--success}

<span style="color:green">(K1) 조직의 테스트 도구에 대한 평가, 시행, 배포, 상시 지원의 성공 요인을 식별할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">조직에 도구의 평가, 구현, 배포, 지속적인 지원을 위한 성공 요인은 다음과 같다:</span>
- <span style="background-color:rgb(237,220,195);">조직의 다른 부서에 도구 사용 전파를 점진적으로 진행</span>
- <span style="background-color:rgb(237,220,195);">도구의 사용법에 맞게 프로세스를 수정하고 개선</span>
- <span style="background-color:rgb(237,220,195);">도구 사용자에게 교육, 코칭, 멘토링 제공</span>
- <span style="background-color:rgb(237,220,195);">도구사용에 필요한 지침을 정의 (예: 사내 자동화 규정)</span>
- <span style="background-color:rgb(237,220,195);">실제 도구 사용에서 얻은 사용법 정보의 수집 방법 구현</span>
- <span style="background-color:rgb(237,220,195);">도구 사용 현황과 성과를 모니터링</span>
- <span style="background-color:rgb(237,220,195);">특정 도구 사용자에게 지원 제공</span>
- <span style="background-color:rgb(237,220,195);">모든 사용자로부터 사용 후 교훈 수집</span>

소프트웨어 개발 수명주기와 도구를 기술적으로, 유기적으로 통합하는 게 중요하다. 가령 운영이나 외부 공급업체를 담당하는 조직을 별도로 둔다. 테스트 실행 도구사용 경험, 사례와 조언은 Graham 2012 를 참조한다.

# ● 용어
{: .notice .text-center}

<details>
<summary>Keywords</summary>
<div markdown="1">

- 데이터 주도 테스팅(data-driven testing): 테스트 입력값과 기대 결과를 표나 스프레드시트에 저장하고, 하나의 제어 스크립트가 표 내 의 모든 테스트를 실행하게 하는 스크립트 기법. 데이터 주도 테스팅은 주로 기록/재생 (capture/playback) 도구와 같은 테스트 실행 도구 적용을 지원하는 데 쓰임

- 키워드 주도 테스팅(keyword-driven testing): 테스트 데이터와 기대 결과뿐만 아니라, 테스트 중인 애플리케이션과 관련된 키워드까지 포함 한 데이터 파일을 사용하는 스크립팅(scripting) 기법. 키워드는 테스트를 진행하고 있는 제어 스크립트가 호출하는 보조 스크립트에 의해 해석

- 테스트 자동화(test automation): 소프트웨어를 사용하여 테스트 관리, 테스트 설계, 테스트 실행, 결과 검사 등의 테스트 활동을 수행하거나 지원하는 것

- 테스트 실행 도구(test execution tool): 지정된 테스트 항목에 대한 테스트를 실행하고, 기대 결과 및 사후조건 대비 결과값을 평가하는 테스트 도구

- 테스트 관리 도구(test management tool): 테스트 프로세스 중 테스트 관리 및 제어 부분에 대한 지원을 제공하는 도구. 테스트 관리 도구는 대부분의 경우 테스트웨어(testware) 관리, 테스트 일정 관리, 결과 기록, 진척도 추적, 인시던트(incident) 관리, 테스트 보고 등 많은 기능을 포함

- 요구사항 관리 도구(requirements management tool): 요구사항과 요구사항 속성(우선순위, 연관된 지식 등), 주석 등의 기록을 지원하고, 요구사항 계층화 및 요구사항 변경 관리를 통해 추적성 확립을 용이하게 해주는 도구. 일관성 검사나 사전에 규정된 요구사항 규칙의 위반과 같은 정적 분석 기능을 제공하는 도구도 있음

- 형상 관리 도구(configuration management tool): 형상 항목의 식별 및 제어, 변경 및 버전에 따른 상태, 형상 항목으로 구성된 베이스라인 (baseline)의 릴리스(release) 등을 지원하는 도구

- 테스트 설계 도구(test design tool): CASE 도구 저장소(요구사항 관리 도구 등)에 보관된 명세, 도구 자체에 보관된 특정한 테스트 컨디션, 또는 코드 자체로부터 테스트 입력값을 생성함으로써 테스트 설계 활동을 지원하는 도구

- 테스트 데이터 준비 도구 (test data preparation tool):<br>
유의어 : 테스트 생성기(test generator)<br>
테스팅에 사용하기 위한 데이터를 기존 데이터베이스에서 선정하거나 데이터의 산출, 생성, 조작, 편집 등이 가능하도록 해주는 테스트 도구 유형

- 테스트 하네스 (test harness): 테스트를 수행하는 데 필요한 스텁(stubs)과 드라이버(drivers)로 구성된 테스트 환경

- 스텁 (stub):<br>
참조 : IEEE 610<br>
특정 소프트웨어 컴포넌트를 호출하거나 의존관계에 있는 다른 컴포넌트를 개발 또는 테스트 하고자, 해당 소프트웨어 컴포넌트를 골격만 또는 특정 목적을 위해 구현한 것. 스텁은 호출 된 컴포넌트를 대체함

- 드라이버 (driver):<br>
참조 : TMap<br>
유의어 : 테스트 드라이버(test driver)<br>
컴포넌트나 시스템의 제어 및 호출을 담당하며 컴포넌트를 대체하는 소프트웨어 컴포넌트나 테스트 도구

- 단위 테스트 프레임워크 (unit test framework):<br>
참조 : Graham<br>
컴포넌트를 개별적으로 또는 적절한 스텁 및 드라이버를 가지고 테스트할 수 있도록 지원하는 단위 또는 컴포넌트 테스팅 환경 도구. 개발자에게 디버깅 기능과 같은 기타 지원도 제공

- 동적 분석 도구 (dynamic analysis tool): 소프트웨어 코드 상태에 관한 런타임(run-time) 정보를 제공하는 도구. 이런 도구는 일반적으로 할당되지 않은 포인터를 식별하고, 포인터 연산을 점검하고, 메모리의 할당, 사용, 반환을 모니터링하고, <span style="color:red">메모리 누수를 확인하는 데 사용</span>됨

- 성능 테스팅 도구 (performance testing tool): 대상 테스트 항목에 필요한 <span style="color:red">부하를 발생</span>시켜, 테스트 실행 동안 성능을 측정하고 기록하는 테스트 도구

- 모니터링 도구 (monitoring tool):<br>
참조 : ISO 24765<br>
연관 항목 : 동적 분석 도구(dynamic analysis tool)<br>
테스트 중인 컴포넌트나 시스템과 병행으로 실행되며, 컴포넌트나 시스템의 동작을 감독, 기록 및 분석하는 소프트웨어 도구 혹은 하드웨어 장치

</div>
</details>

# ● 샘플문제
{: .notice--danger .text-center}

A - Q39. 다음 중 테스트 실행 도구의 가장 큰 이점은 무엇인가?
- a. 리그레션 테스트 생성이 용이하다.
- b. 테스트 자산의 버전 제어 유지가 용이하다.
- c. 보안 테스팅을 위한 테스트 설계에 용이하다.
- d. 리그레션 테스트 수행에 용이하다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-6.1.2 (K1) 테스트 자동화의 효과와 리스크를 식별할 수 있다.
- a. 오답- 테스트 실행 도구는 리그레션 테스트를 생성할 때보다 실행할 때 더 이점이 있다.
- b. 오답- 형상 관리 도구가 하는 일이다.
- c. 오답- 보안 테스팅을 위해서는 특별한 도구가 필요하다.
- d. 정답- 실러버스 6.1.2: 반복적인 수동 업무를 줄여 주어(예: 리그레션 테스트 수행, 환경 구축/해체 작업, 동일 테스트 데이터 재입력, 코딩표준 준수 확인) 시간을 절약하게 된다.

</div>
</details>

---

A - Q40. 다음 테스트 도구 중 테스터보다는 개발자에게 보다 적합한 도구는?
- a. 요구사항 관리 도구
- b. 형상 관리 도구
- c. 정적 분석 도구
- d. 성능 테스팅 도구

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-6.1.1 (K2) 테스트 도구를 사용 목적과 지원하는 테스트 활동에 따라 구별할 수 있다.
- a. 오답- 요구사항 관리 도구는 특별히 개발자에게 적합하지 않다.
- b. 오답- 형상 관리 도구는 특별히 개발자에게 적합하지 않다.
- c. 정답- 정적 분석 도구는 개발자에게 특히 적합하다.
- d. 오답- 성능 테스팅 도구는 테스터보다 개발자에게 더 적합하지는 않다.

</div>
</details>

---

B - Q39. 다음은 테스팅 활동과 테스팅 도구들이다:
1. 성능 측정 및 동적 분석
2. 테스트 실행과 로깅
3. 테스팅 및 테스트웨어 관리
4. 테스트 설계

- a. 코드 커버리지 도구
- b. 동적 분석 도구
- c. 테스트 데이터 생성 도구
- d. 결함 관리 도구

다음 중 테스트 활동과 도구를 바르게 연결한 것은?
- A. 1–b, 2–c, 3–d, 4–a
- B. 1–b, 2–a, 3–c, 4–d
- C. 1–b, 2–a, 3–d, 4–c
- D. 1–a, 2–b, 3–d, 4–c

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-6.1.1 (K2) 테스트 도구를 사용 목적과 지원하는 테스트 활동에 따라 구별할 수 있다.<br>
실러버스(6.1.1)에 따라 테스트 활동과 도구를 연결하면 다음과 같다:
1. 성능 측정 및 동적 분석 (b) 동적 분석 도구
2. 테스트 실행과 로깅 (a) 코드 커버리지 도구
3. 테스팅 및 테스트웨어 관리 (d) 결함 관리 도구
4. 테스트 설계 (c) 테스트 데이터 생성 도구

따라서 정답은 C 이다.

</div>
</details>

---

B - Q40. 다음 중 조직에 도구를 도입하기 위해 파일럿 프로젝트를 수행하는 이유 중 가장 일반적인 것은?
- A. 도구가 기존 프로세스와 프랙티스에 적합한지 평가하고 변경할 사항은 없는지 파악하기 위해
- B. 테스트 자동화 기술을 평가하고 도구를 사용할 테스터의 교육, 멘토링, 코칭 요구를 파악하기 위해
- C. 도구가 필요한 기능을 제공하고 기존 테스트 도구와 중복되지 않는지 평가하기 위해
- D. 도구 제공업체가 제공하는 교육 및 기타 지원사항의 관점에서 업체를 평가하기 위해

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-6.2.2 (K1) 도구를 도입할 때 파일럿 프로젝트의 목적을 상기할 수 있다.
- A. 정답- 실러버스 (6.2.2) 참조
- B. 오답- 테스트 자동화 기술 평가와 도구를 사용할 테스터의 교육, 멘토링, 코칭 요구를 파악하는 것은 테스트 <span style="color:red">도구 선택 활동</span>의 일환으로 수행해야 한다. 실러버스 (6.2.1) 참조
- C. 오답- 도구가 필요한 기능을 제공하고 기존 도구와 중복되지 않는지에 대한 판단은 <span style="color:red">도구 선택 활동</span>의 일환으로 수행해야 한다. 실러버스 (6.2.1) 참조
- D. 오답- 도구 제공업체가 제공하는 교육 및 기타 지원사항의 관점에서의 업체 평가는 <span style="color:red">도구 선택 활동</span>의 일환으로 수행해야 한다. 실러버스 (6.2.1) 참조

</div>
</details>

---

C - Q39. 당신은 리그레션 테스팅 도구의 파일럿 프로젝트를 방금 마쳤다. 이제 도구를 훨씬 잘 이해하고 있고 테스팅 프로세스도 도구에 잘 맞추게 되었다. 당신은 이 도구 및 관련 작업 산출물 사용을 위한 표준을 마련하고 있다.<br>
다음 중 아직 진행이 남은 일반적인 테스트 자동화 파일럿 프로젝트의 목표는?
- a. 도구에 대해 더 상세히 알아보기
- b. 도구가 기존 프로세스와 프랙티스에 어떻게 적용되는지 확인
- c. 도구의 사용, 관리 및 도구와 테스트 자산의 저장, 유지보수
- d. 합리적 비용으로 이익을 달성할 수 있는지 평가

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-6.2.2, K1
- a. 오답- 이는 파일럿의 목적이지만 파일럿때문에 도구를 훨씬 더 잘 이해할 수 있었기 때문에 이미 달성한 것이다.
- b. 오답- 이는 파일럿의 목표이지만 테스트 프로세스를 테일러링했기 때문에 이미 달성한 것이다.
- c. 오답- 이는 파일럿의 목표이지만 도구와 관련 작업 산출물을 사용하는 방법을 표준화했기 때문에 이미 달성한 것이다.
- d. 정답- 이점을 평가하고 메트릭 항목을 구성하는 것이 목록에서 누락된 두 가지 목표이다.

</div>
</details>

---

C - Q40. 다음 중 테스트 메트릭을 보고하는 데 가장 유용한 도구는?
- a. 테스트 관리 도구
- b. 정적 분석 도구
- c. 커버리지 도구
- d. 모델기반 테스팅 도구

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-6.1.1, K2
- a. 정답- 테스트 관리 도구는 메트릭을 포함해 테스트 관리자와 관련된 활동들을 지원한다.
- b. 오답- 정적 코드 분석 메트릭은 테스팅 전체가 아니라 단지 코드와 관련이 있다.
- c. 오답- 이러한 도구들은 테스팅 전체가 아니라 테스트 베이시스의 커버리지와 코드 커버리지만을 보고한다.
- d. 오답- 모델 기반 테스팅 도구는 테스팅 전체가 아니라 특정 부분에 초점을 맞춘다.

</div>
</details>

# ● 자료참고
{: .notice--info .text-center}

[실러버스 본문](http://www.kstqb.org/board_skin/board_view.asp?idx=426&page=1&bbs_code=4&key=0&word=&etc=ISTQB){: .btn .btn--info}
[실러버스 용어](http://www.kstqb.org/board_skin/board_view.asp?idx=342&page=2&bbs_code=4&key=0&word=&etc=ISTQB){: .btn .btn--info}
[샘플문제](http://www.kstqb.org/board_skin/board_view.asp?idx=433&page=2&bbs_code=5&key=0&word=&etc=){: .btn .btn--info}