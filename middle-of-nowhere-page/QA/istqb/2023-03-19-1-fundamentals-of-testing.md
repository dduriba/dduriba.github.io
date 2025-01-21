---
title: "[Foundation Level] 제 1장. 테스팅의 기초"
excerpt: "Foundation Level Chapter.1 Fundamentals of Testing"
categories: ISTQB
tag: [ISTQB, Foundation Level]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# 1.1 테스팅이란 무엇인가? What is Testing?
{: .notice--warning .text-center}

소프트웨어 시스템은 인터넷 은행과 같은 비즈니스 응용 프로그램부터 자동차와 같은 소비자 제품까지 생활의 많은 부분과 밀접하게 연관되어 있다. 많은 사람들은 소프트웨어를 사용하면서 기대한 것과 다르게 동작하는 걸 느낀 적이 있을 것이다. 올바르게 작동하지 않는 소프트웨어는 금전, 시간, 비즈니스 평판 손실은 물론, 심하게는 부상이나 사망에 이르기까지 심각한 문제를 일으킬 수 있다. 소프트웨어 테스팅은 소프트웨어의 품질을 평가하고, 운영 중 소프트웨어 장애의 발생 가능성을 줄이는 하나의 방법이다.<br>
테스팅에 대해 많이 오해하는 것 중 하나는 테스팅이 단지 소프트웨어를 실행하고 결과를 확인하는 테스트 수행에 국한된다고 생각하는 것이다. 1.4 절에 설명하고 있는 바와 같이, 소프트웨어 테스팅이란 다양한 활동을 포함하는 프로세스이며 테스트 실행(결과 확인 포함)은 그 많은 활동 중 하나일 뿐이다. 테스트 프로세스는 테스트 계획, 분석, 설계, 테스트 구현, 테스트 진행 상황 및 결과 보고, 테스트 대상 품질 평가 등 많은 활동을 포함한다.<br>
<span style="background-color:rgb(237,220,195);">테스팅 활동에는 테스트 대상 컴포넌트나 시스템을 실행하는 것도 있다. 이런 테스팅을 <span style="background-color:rgb(207,228,207);">동적 테스팅</span>이라 부른다.</span> 반면 <span style="background-color:rgb(237,220,195);">테스트 대상 컴포넌트나 시스템을 실행하지 않는 테스팅도 있다. 이런 테스팅은 <span style="background-color:rgb(207,228,207);">정적 테스팅</span>이라 부른다.</span> 따라서 요구사항, 사용자 스토리, 소스 코드와 같은 작업 산출물에 대한 리뷰 역시 테스팅에 포함된다.<br>
<span style="background-color:rgb(232,233,234);">테스팅에 대한 또 다른 오해는 테스팅이 요구사항, 사용자 스토리, 그 외 기타 명세의 베리피케이션(검증 verification)에만 국한된 활동이라는 것이다. 시스템이 주어진 명세를 충족하는지 확인하는 것이 테스팅에 포함되긴 하지만, <span style="color:red">시스템이 운영 환경에서 사용자 또는 기타 이해관계자의 요구를 만족시키는지를 확인하는 밸리데이션(확인 validation) 또한 테스팅에 포함된다.</span></span><br>
테스팅 활동은 수명주기 모델에 따라 다르게 계획하고 수행한다 (2.1 절 참조).

## 1.1.1 테스팅의 일반적인 목적 (Typical Objectives of Testing)
{: .notice--success}

<span style="color:green">(K1) 테스팅의 일반적인 목적을 파악한다.</span>

<span style="background-color:rgb(207,228,207);">일반적인 프로젝트에서 테스팅은 다음과 같은 목적을 가질 수 있다:</span>
- <span style="background-color:rgb(237,220,195);">요구사항, 사용자스토리, 설계, 소스 코드 등과 같은 작업 산출물 평가에 의한 결함 예방</span>
- <span style="background-color:rgb(237,220,195);">명시된 모든 요구사항이 충족됐는지 검증</span>
- <span style="background-color:rgb(237,220,195);">테스트 대상의 완성 여부 확인과 사용자와 기타 이해관계자의 기대치 대로 동작하는지의 확인</span>
- <span style="background-color:rgb(237,220,195);">테스트 대상의 품질 수준에 대한 자신감 획득</span>
- <span style="background-color:rgb(237,220,195);">부적절한 소프트웨어 품질의 리스크 레벨 감소로 장애와 결함을 발견</span>
- <span style="background-color:rgb(237,220,195);">이해관계자가 테스트 대상의 품질 수준을 결정하는 데 필요한 충분한 정보 제공</span>
- <span style="background-color:rgb(237,220,195);">계약/법률/규제 요구사항이나 표준의 준수 및 테스트 대상이 이러한 요구사항이나 표준을 준수하는지 확인</span>

테스팅의 목적은 테스트하고 있는 컴포넌트나 시스템의 정황 즉, 현재의 테스트 레벨과 사용하는 소프트웨어 개발 수명주기 모델 등에 따라 달라질 수 있다. 목적이 정황에 따라 달라지는 예는 다음과 같다:
- <span style="background-color:rgb(207,228,207);">컴포넌트 테스팅의 목적</span> 중 하나는 <span style="background-color:rgb(237,220,195);"><span style="color:red">내재되어 있는 결함을 최대한 조기에 가능한 많이 식별하고 수정하는 것</span></span>일 수 있다. 또 다른 목적은 <span style="background-color:rgb(237,220,195);"><span style="color:red">코드 커버리지를 높이는 것</span></span>일 수도 있다.
- <span style="background-color:rgb(207,228,207);">인수 테스팅의 주요 목적</span> 중 하나는 <span style="background-color:rgb(237,220,195);">시스템이 기대한 대로 동작하는지</span>, 또 <span style="background-color:rgb(237,220,195);">요구사항을 충족하는지</span> 확인하는 것일 수 있다. 또 다른 목적은 <span style="background-color:rgb(237,220,195);"><span style="color:red">특정 시점에 시스템을 배포하는 것에 대한 리스크 정보를 이해관계자에게 제공하는 것</span></span>일 수 있다.

## 1.1.2 테스팅과 디버깅 (Testing and Debugging)
{: .notice--success}

<span style="color:green">(K2) 테스팅과 디버깅을 구별할 수 있다.</span>

테스팅과 디버깅은 다르다. <span style="background-color:rgb(207,228,207);"><span style="color:red">테스트</span></span>를 <span style="background-color:rgb(237,220,195);"><span style="color:red">실행하면 소프트웨어 결함으로 인한 장애를 찾아낼 수 있으며</span></span>, <span style="background-color:rgb(207,228,207);"><span style="color:red">디버깅</span></span>은 <span style="background-color:rgb(237,220,195);"><span style="color:red">그런 장애의 원인을 찾고 분석해서 수정하는 개발 활동</span></span>이다. 이후 실행되는 <span style="background-color:rgb(207,228,207);">확인 테스팅</span>에서 <span style="background-color:rgb(237,220,195);">결함을 제대로 수정했는지 확인</span>한다.
<span style="background-color:rgb(207,228,207);">테스터</span>가 <span style="background-color:rgb(237,220,195);">초기 테스트와 마지막 확인 테스트를 담당</span>하고 <span style="background-color:rgb(207,228,207);"><span style="color:red">개발자</span></span>는 <span style="background-color:rgb(237,220,195);"><span style="color:red">디버깅 관련 컴포넌트 및 컴포넌트 통합 테스팅 (지속적 통합)을 수행</span></span>한다.
반면, <span style="background-color:rgb(207,228,207);">애자일 개발 및 기타 소프트웨어 수명주기 모델</span>에서는 <span style="background-color:rgb(237,220,195);">테스터가 디버깅과 컴포넌트 테스팅에 관여하기도 한다.</span><br>
소프트웨어 테스팅 개념에 대한 추가적인 정보는 ISO 표준(ISO/IEC/IEEE 29119-1)에서 찾을 수 있다.

# 1.2 테스팅이 왜 필요한가? Why is Testing Necessary? 
{: .notice--warning .text-center}

<span style="background-color:rgb(207,228,207);">컴포넌트, 시스템 및 관련 문서에 대한 철저한 테스팅</span>은 <span style="background-color:rgb(237,220,195);">운영 중 장애 발생 가능성을 줄이는 데 도움</span>이 된다.
<span style="background-color:rgb(207,228,207);">결함을 발견하고 또 발견된 결함을 수정하는 것</span>은 <span style="background-color:rgb(237,220,195);">컴포넌트나 시스템의 품질에 기여</span>하는 것이다. 또한, <span style="background-color:rgb(207,228,207);">소프트웨어 테스팅</span>이 <span style="background-color:rgb(237,220,195);">계약/법적 요구사항이나 특정 산업 표준을 만족시키기 위해 필요할 수도 있다.</span>

## 1.2.1 성공을 위한 테스팅의 기여 (Testing’s Contributions to Success)
{: .notice--success}

<span style="color:green">(K2) <span style="background-color:rgb(207,228,207);">테스팅이 왜 필요한지 예</span>를 들 수 있다.</span>

컴퓨터의 역사에서 소프트웨어와 시스템이 운영을 위해 배포된 후로, 결함으로 장애가 발생하거나 이해관계자의 요구를 충족시키지 못하는 상황은 늘 있었다. 하지만 적절한 테스트 기법을 적절한 테스트 전문성을 가지고 적절한 테스트 레벨과 개발 수명주기 단계에 적용하면, 소프트웨어와 시스템이 그런 문제를 안고 배포되는 경우를 줄일 수 있다. 대표적인 예로는:
- <span style="background-color:rgb(237,220,195);">테스터를 요구사항 리뷰 혹은 사용자 스토리 개선에 참여시키면 해당 작업 산출물에서 결함을 발견할 수 있다. 요구사항 결함을 식별하고 제거하면 잘못된 혹은 테스트할 수 없는 기능이 개발되는 리스크를 줄일 수 있다.</span>
- <span style="background-color:rgb(237,220,195);">시스템을 설계하는 동안 테스터가 시스템 설계자와 적극적으로 협업할 경우, 설계와 그것을 어떻게 테스트해야 하는지에 대해 서로 좀 더 깊이 있게 이해하게 된다. 이렇게 이해도가 올라가면 기능 설계에 결함이 유입되는 리스크가 줄어들게 되고, 필요한 테스트를 좀 더 일찍 식별할 수 있다.</span>
- <span style="background-color:rgb(237,220,195);">코드를 개발하는 동안 테스터가 개발자와 적극적으로 협업할 경우, 코드와 그것을 어떻게 테스트해야 하는지에 대해 서로 좀 더 깊이 있게 이해하게 된다. 이렇게 이해도가 높아지면 코드와 테스트에서의 결함 발생 리스크가 줄어든다.</span>
- <span style="background-color:rgb(237,220,195);">테스터가 릴리스 전에 소프트웨어를 확인하고 검증하면, 그러지 않았을 경우 놓쳤을 수 있는 장애를
발견하고 그 장애의 원인인 결함을 제거(즉, 디버깅)하는 데 도움을 줄 수 있다. 이렇게 함으로써 소프트웨어가 이해관계자의 필요와 요구사항을 충족시킬 가능성을 높일 수 있다.</span>

이런 경우뿐만 아니라 정의된 테스트 목적(1.1.1 절 참조)을 충족하는 것은 소프트웨어 개발과 유지보수 전반의 성공 확률을 높여준다.

## 1.2.2 품질 보증과 테스팅 (Quality Assurance and Testing)
{: .notice--success}

<span style="color:green">(K2) 품질 보증과 테스팅의 관계를 설명하고, 높은 품질 확보에 테스팅이 어떻게 기여하는지 예를 들 수 있다.</span>

<span style="background-color:rgb(232,233,234);">일반적으로 사람들이 품질 보증(QA, Quality Assurance)과 테스팅을 혼용해서 사용하는 경우가 많은데 어느 정도 연관성이 있지만 품질 보증과 테스팅은 다른 개념이다. 둘 다 좀 더 포괄적인 개념인 품질 관리(quality management)에 속한다.<br>
품질 관리에는 품질 측면에서 조직이 나아가야 하는 방향을 제시하고 제어하는 모든 활동이 포함된다. 품질 관리는 또한 품질 보증과 품질 제어를 포함한 여러 가지 활동을 포함한다.</span><br>
일반적으로 <span style="background-color:rgb(207,228,207);">품질 보증</span>은 <span style="background-color:rgb(237,220,195);">적절한 품질 수준을 달성했는지 확신을 얻기 위해 적절한 프로세스를 준수하도록 하는 것에 초점을 두고 있다. 프로세스를 따를 경우, 해당 프로세스를 바탕으로 생성되는 작업 산출물의 품질은 더 월등한 경우가 많으며, 높은 작업 산출물 품질은 결함 예방에 도움이 된다. 또한, 결함의 원인을 찾아서 제거하기 위한 근본 원인 분석(root cause analysis)의 활용과 회고 회의(retrospective meetings)의 결과를 적절하게 적용해서 프로세스를 개선하는 것은 효과적인 품질 보증에 매우 중요한 사항들이다.</span><br>
<span style="background-color:rgb(207,228,207);">품질 제어</span>에도 <span style="background-color:rgb(237,220,195);">적합한 품질 수준을 달성하기 위한 다양한 활동이 있으며, 테스트 활동도 여기에 포함된다. 테스트 활동은 전반적인 소프트웨어 개발 및 유지보수 프로세스의 일부이다.</span><br>
품질 보증에서는 전반적인 프로세스의 올바른 수행 여부에 관심을 가지기 때문에 올바른 테스팅의 적용에도 관심을 가진다. 테스팅은 품질을 높이는 데 다양한 방법으로 기여한다.

## 1.2.3 오류, 결함, 장애 (Errors, Defects, and Failures)
{: .notice--success}

<span style="color:green">(K2) 오류(error), 결함(defect), 장애(failure)를 구별할 수 있다.</span>

사람은 프로그램 코드 또는 기타 작업 산출물을 작성하면서 결함(결점, 버그)을 발생시키는 오류(실수)를 범할 수 있다. 특정 작업 산출물 내 결함의 원인이 되는 오류는 연관된 다른 작업 산출물의 결함의 원인이 되는 또 다른 오류의 계기가 될 수 있다. 예를 들어, 요구사항을 도출하면서 범해진 오류는 요구사항 결함이 되며, 이런 요구사항 결함은 프로그램 작성 시 오류를 일으켜 결국 코드 결함의 원인이 된다.<br>
코드의 결함이 실행되면 장애를 일으킬 수 있지만 반드시 그런 것은 아니다. 예를 들어, 결함 중 일부는 발생 가능성이 없거나 매우 낮아서 특수한 입력이나 사전조건이 충족돼야 장애를 일으킬 수 있다.<br>
<span style="background-color:rgb(207,228,207);">대표적인 오류 발생 원인은 다음과 같다:</span>
- <span style="background-color:rgb(237,220,195);">시간적인 압박</span>
- <span style="background-color:rgb(237,220,195);">사람의 실수</span>
- <span style="background-color:rgb(237,220,195);">경험이 적거나 기술이 부족한 프로젝트 참여자</span>
- <span style="background-color:rgb(237,220,195);">요구사항과 설계 등에 대한 프로젝트 참여자 간의 의사소통 문제</span>
- <span style="background-color:rgb(237,220,195);">코드, 설계, 아키텍처의 복잡성, 해결해야 하는 근본 문제, 사용하는 기술의 복잡도</span>
- <span style="background-color:rgb(237,220,195);">시스템 내/외부 인터페이스에 대한 이해 부족, 특히 내/외부 인터페이스 수가 많은 경우</span>
- <span style="background-color:rgb(237,220,195);">새롭고 익숙하지 않은 기술</span>

<span style="background-color:rgb(207,228,207);">장애</span>는 <span style="background-color:rgb(237,220,195);">코드 결함뿐만 아니라 환경 조건으로 인해 발생할 수도 있다. 예를 들어, 방사능, 전자기장, 환경 오염 등은 펌웨어 결함의 원인이 되거나 하드웨어 상태를 변화시킴으로써 소프트웨어 실행에 영향을 줄 수 있다.</span><br>
테스트 결과가 기대한 것과 다르다고 해서 무조건 장애가 있다고 볼 수는 없다. 테스트 실행 방식의 오류나 테스트 데이터, 테스트 환경, 기타 테스트웨어에 결함이 있는 경우, 또는 그 외 다양한 이유로 거짓양성(false positive)이 발생할 수 있다. 비슷한 오류나 결함이 거짓음성(false negative)의 원인이 되는 반대의 경우도 발생할 수 있다. <span style="background-color:rgb(207,228,207);"><span style="color:red">거짓음성</span></span>은 <span style="background-color:rgb(237,220,195);"><span style="color:red">테스트가 발견했어야 할 결함을 발견하지 못하는 경우</span></span>이며, <span style="background-color:rgb(207,228,207);"><span style="color:red">거짓양성</span></span>은 <span style="background-color:rgb(237,220,195);"><span style="color:red">결함으로 보고됐지만 실제 결함이 아닌 경우</span></span>를 말한다.

## 1.2.4 결함, 근본 원인, 결과 (Defects, Root Causes and Effects)
{: .notice--success}

<span style="color:green">(K2) 결함의 근본원인과 그것의 영향을 구별할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">결함의 근본 원인</span>은 <span style="background-color:rgb(237,220,195);">해당 결함을 만들어낸 최초의 행동이나 조건</span>을 말한다. 결함을 분석함으로써 근본 원인을 찾을 수 있으며, 차후 유사한 결함의 발생 가능성을 낮출 수 있다. 가장 근본적인 원인을 분석하고 여기에 집중하기 때문에, 이를 기반으로 이루어지는 프로세스 개선은 이후 발생하는 결함 수를 상당 부분 줄여준다.<br>
예를 들어, 단 한 줄의 잘못된 코드로 인한 이자 지급 오류는 소비자 불만을 초래한다. 제품 소유자가 이자 계산법을 잘못 이해해서 작성한 애매모호한 사용자 스토리를 기반으로 코드가 잘못 작성되었다. 대부분의 결함이 이자 계산식에 존재하며 해당 결함들의 근본 원인 역시 비슷한 오해로 인한 것이라면, 차후 유사한 결함의 발생 가능성을 낮추기 위해 제품 소유자에게 이자 계산에 대한 교육을 제공할 수 있다.<br>
앞의 예제에서의 <span style="background-color:rgb(207,228,207);">결과</span>는 <span style="background-color:rgb(237,220,195);">소비자 불만</span>이며 <span style="background-color:rgb(207,228,207);">장애</span>는 <span style="background-color:rgb(237,220,195);">잘못된 이자 지급</span>이다. <span style="background-color:rgb(207,228,207);">결함</span>은 <span style="background-color:rgb(237,220,195);">코드에 포함된 잘못된 계산식</span>이며, 그것의 <span style="background-color:rgb(207,228,207);">원인이 되는 최초 결함</span>은 <span style="background-color:rgb(237,220,195);">사용자 스토리의 모호성</span>이다. <span style="background-color:rgb(207,228,207);">최초 결함의 근본 원인</span>은 <span style="background-color:rgb(237,220,195);">제품 소유자의 지식 부족</span>이었으며, 그 결과로 <span style="background-color:rgb(237,220,195);">제품 소유자가 사용자 스토리를 작성할 때 <span style="background-color:rgb(207,228,207);">오류</span>를 범했다</span>고 볼 수 있다. 근본 원인 분석 프로세스는 ISTQB-CTFL-TM 및 ISTQB-CTFL-ITP 에서 다루고 있다.

# 1.3 테스팅의 7 가지 원리 Seven Testing Principles
{: .notice--warning .text-center}

<span style="color:green">(K2) 테스팅의 7 가지 원리를 설명할 수 있다.</span>

1. <span style="background-color:rgb(207,228,207);">테스팅은 결함이 존재함을 밝히는 활동이지, 결함이 없음을 밝히는 활동이 아니다 (Testing shows the presence of defects, not their absence)</span><br>
<span style="background-color:rgb(237,220,195);">테스팅은 결함이 존재한다는 것을 보여줄 수 있지만, 결함이 없다는 것을 증명할 수 없다. 테스팅은 소프트웨어에 발견되지 않은 결함의 존재 가능성을 줄일 수는 있지만, <span style="color:red">결함이 전혀 발견되지 않았다 하더라도 해당 소프트웨어가 완벽하다는 뜻은 아니다.</span></span>
2. <span style="background-color:rgb(207,228,207);">완벽한(exhaustive) 테스팅은 불가능하다 (Exhaustive testing is impossible)</span><br>
<span style="background-color:rgb(237,220,195);"><span style="color:red">모든 것(입력과 사전 조건의 모든 조합)을 테스팅 한다는 것은 매우 간단한 소프트웨어를 제외하고는 불가능</span>하다. 따라서, 완벽하게 테스트하고자 하기보다는 <span style="color:red">리스크 분석과 우선순위를 토대로한 테스트에 노력을 집중하는 것이 좋다.</span></span>
3. <span style="background-color:rgb(207,228,207);">조기 테스팅(early testing)으로 시간과 비용을 절약할 수 있다 (Early testing saves time and money)</span><br>
<span style="background-color:rgb(237,220,195);">초기에 결함을 찾기 위해서는 정적 및 동적 테스트 활동 모두 소프트웨어 개발 수명주기 중 가능한 이른 시점에 시작해야 한다. <span style="color:blue">초기부터 시작하는 테스팅을 시프트 레프트(shift left)라고도 부른다.</span> 소프트웨어 수명주기 초기부터 테스팅을 함으로써 나중에 큰 비용이 동반되는 수정을 줄이거나 없앨 수 있다 (3.1 절 참조).</span>
4. <span style="background-color:rgb(207,228,207);">결함은 집중된다 (Defects cluster together)</span><br>
<span style="background-color:rgb(237,220,195);"><span style="color:red">출시 전 테스팅에서 발견하는 대부분의 결함은 소수의 모듈에 집중되어 발생하는 경향을 보이며, 운영상 장애의 대부분 역시 소수의 모듈에서 발생</span>한다. <span style="color:red">예상 결함 집중 영역과 테스트와 운영 중 실제로 관측한 결함 집중 영역은 리스크 분석의 주요 입력값으로 사용</span>된다. 리스크 분석은 테스트 노력을 집중시키는 데 필요하다 (원리 2 참조).</span>
5. <span style="background-color:rgb(207,228,207);">살충제 패러독스(pesticide paradox)에 유의하라 (Beware of the pesticide paradox)</span><br>
<span style="background-color:rgb(237,220,195);">만일 같은 테스트를 계속해서 반복 실행한다면, 결국 해당 테스트로는 결함을 더 이상 발견할 수 없게 된다. 새로운 결함을 발견하기 위해서는 기존 테스트와 테스트 데이터를 바꾸고 새로운 테스트를 작성할 필요가 있다. (살충제를 계속 사용하다 보면 결국 해충을 잡지 못하듯, 테스트도 반복하다 보면 결국 결함을 더 이상 찾지 못하게 된다.) 하지만 살충제 패러독스가 좋은 것을 의미하는 경우도 있다. 자동 리그레션 테스팅의 경우 리그레션 결함이 적다는 것을 의미할 수도 있다.</span>
6. <span style="background-color:rgb(207,228,207);">테스팅은 정황(context)에 의존적이다 (Testing is context dependent)</span><br>
<span style="background-color:rgb(237,220,195);">테스팅은 정황에 따라 다르게 진행된다. 예를 들어, 안전 최우선 산업에서 사용하는 제어 소프트웨어는 이커머스 모바일 애플리케이션과는 다르게 테스트한다. 또, 애자일 프로젝트에서의 테스팅은 순차적 소프트웨어 개발 수명주기 프로젝트에서의 테스팅과는 다르게 진행된다 (2.1 절 참조).</span>
7. <span style="background-color:rgb(207,228,207);">오류 부재는 궤변이다 (Absence-of-errors is a fallacy)</span><br>
<span style="background-color:rgb(237,220,195);">조직에 따라서는 테스터가 모든 가능한 테스트를 실행하고 존재하는 모든 결함을 발견하기를 기대하는 경우도 있지만, 원리 1과 2가 말해주듯 이것은 불가능하다. 뿐만 아니라, 단순히 많은 결함을 발견하고 고쳤다고 해서 시스템의 성공이 보장된다고 생각하는 것은 궤변(즉, 잘못된 믿음)이다. 예를 들어, <span style="color:red">정의된 모든 요구사항을 충분히 테스트하고 발견된 모든 결함을 수정하더라도 여전히 사용하기 어렵거나, 사용자의 요구와 기대를 충족시키지 못하거나, 경쟁 시스템에 비해 부족한 시스템을 만들어낼 수 있다.</span></span>

위에 나열된 원리와 기타 테스팅 원리에 대한 예제를 위해서는 Myers 2011, Kaner 2002, Weinberg 2008, Beizer 1990 을 참조.

# 1.4 테스트 프로세스 Test Process
{: .notice--warning .text-center}

<span style="background-color:rgb(237,220,195);">모두가 사용하는 일반적인 테스트 프로시저는 없지만, 설정한 목적의 달성 가능성을 높여주는 공통적인 테스트 활동 세트(sets)는 존재한다. 이런 테스트 활동 세트를 <span style="background-color:rgb(207,228,207);">테스트 프로세스</span>라 한다.</span> 주어진 상황에 맞는 구체적인 소프트웨어 테스트 프로세스는 다양한 변수에 따라 결정된다.
테스트 프로세스에 속하는 테스트 활동과 이런 활동을 어떻게 구현할지, 또 이런 활동을 언제 수행할지에 대한 내용은 조직의 테스트 전략에서 다룰 수 있다.

## 1.4.1 정황에 따른 테스트 프로세스 (Test Process in Context)
{: .notice--success}

<span style="color:green">(K2) 정황이 테스트 프로세스에 미치는 영향에 대해 설명할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">다음은 조직의 테스트 프로세스에 영향을 줄 수 있는 정황 요소 중 일부이다:</span>
- <span style="background-color:rgb(237,220,195);">사용 중인 소프트웨어 개발 수명주기 모델과 프로젝트 방법론</span>
- <span style="background-color:rgb(237,220,195);">적용하고자 하는 테스트 레벨과 테스트 유형</span>
- <span style="background-color:rgb(237,220,195);">제품 및 프로젝트 리스크</span>
- <span style="background-color:rgb(237,220,195);">비즈니스 도메인</span>
- <span style="background-color:rgb(237,220,195);">다음과 같은 운영상의 제약사항:</span>
  + <span style="background-color:rgb(242,213,214);">예산과 자원 (resource)</span>
  + <span style="background-color:rgb(242,213,214);">일정</span>
  + <span style="background-color:rgb(242,213,214);">복잡도</span>
  + <span style="background-color:rgb(242,213,214);">계약 및 규제 요구사항</span>
- <span style="background-color:rgb(237,220,195);">운영 정책과 프랙티스 (practices)</span>
- <span style="background-color:rgb(237,220,195);">준수해야 하는 내부 및 외부 표준</span>

<span style="background-color:rgb(207,228,207);">다음 절은 아래의 관점에서 조직 테스트 프로세스의 일반적인 요소에 대해 설명하고 있다:</span>
- <span style="background-color:rgb(237,220,195);">테스트 활동과 작업</span>
- <span style="background-color:rgb(237,220,195);">테스트 작업 산출물</span>
- <span style="background-color:rgb(237,220,195);">테스트 베이시스와 테스트 작업 산출물 간의 추적성</span>

테스트 레벨과 유형에 상관없이, 테스트 베이시스에 대한 측정 가능한 커버리지 조건이 설정되어 있으면 매우 유용하다. 커버리지 조건은 소프트웨어 테스트의 목적 달성 여부를 보여주는 활동의 주요 성능 지표(KPI, key performance indicator)로 사용하기 용이하다 (1.1.1 절 참조).
예를 들어, 모바일 애플리케이션에 대해서는 요구사항 목록과 지원 대상 모바일 기기 목록을 테스트 베이시스로 사용할 수 있는데, 각각의 요구사항과 테스트 대상 기기를 하나의 테스트 베이시스 요소로 볼 수 있다. 커버리지 조건은 각 테스트 베이시스 요소를 적어도 하나의 테스트 케이스로 다루어야 한다는 것일 수 있다. 실행한 테스트 케이스의 결과는 명시된 요구사항의 충족 여부와 지원 대상 기기에서 장애가 발생했는지에 대한 정보를 이해관계자에게 제공한다.
테스트 프로세스에 대해서는 ISO 표준(ISO/IEC/IEEE 29119-2)에서 자세히 다루고 있다.

## 1.4.2 테스트 활동과 작업 (Test Activities and Tasks)
{: .notice--success}

<span style="color:green">(K2) 테스트 프로세스의 테스트 활동과 연관된 작업에 대해 설명할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">테스트 프로세스를 구성하는 주요 활동은 다음과 같다:</span>
- <span style="background-color:rgb(237,220,195);">테스트 계획</span>
- <span style="background-color:rgb(237,220,195);">테스트 모니터링과 제어</span>
- <span style="background-color:rgb(237,220,195);">테스트 분석</span>
- <span style="background-color:rgb(237,220,195);">테스트 설계</span>
- <span style="background-color:rgb(237,220,195);">테스트 구현</span>
- <span style="background-color:rgb(237,220,195);">테스트 실행</span>
- <span style="background-color:rgb(237,220,195);">테스트 완료</span>

각 주요 활동은 구성 활동들로 이루어지며, 아래 하위 섹션에서 하나씩 다룹니다. 각 구성 활동은 다시 다수의 개별 작업으로 나눠지며 프로젝트마다 또는 릴리즈마다 달라질 수 있다.
또한, <span style="background-color:rgb(232,233,234);">이러한 주요 활동들이 대부분 순차적으로 이루어지는 것처럼 보일 수 있으나 반복적으로 구현되는 경우가 많다. 예를 들어, 애자일 개발은 지속적인 계획을 바탕으로 소프트웨어 설계, 빌드(build), 테스트로 구성된 작은 주기를 반복해서 배치한다. 따라서, 이런 소프트웨어 개발 접근법에 포함된 테스트 활동 또한 반복적, 지속적으로 이루어지게 된다. 순차적 소프트웨어 개발에서도 개별 활동의 논리적인 순서는 중첩(overlap), 조합(combination), 동시 실행(concurrency) 되거나 누락되기 때문에 시스템과 프로젝트의 정황에 따라 이런 주요 활동들을 어느 정도 조정하는 것이 필요하다.</span>

**<span style="background-color:rgb(207,228,207);">테스트 계획 (test planning)</span>**<br>
<span style="background-color:rgb(237,220,195);">테스트 계획은 테스팅의 목적과 정황으로 인한 제약 사항을 고려해 테스트 목적을 달성하기 위해 필요한 <span style="color:red">접근법을 정의하는 활동을 포함한다. 예를 들어, 적합한 테스트 기법과 작업 명시, 정해진 출시 일정 전에 완료하기 위한 테스트 일정 수립</span> 등이 여기에 포함된다. <span style="color:red">테스트 계획은 모니터링과 제어 활동에서 나온 피드백을 기반으로 수정할 수 있다.</span></span>

**<span style="background-color:rgb(207,228,207);">테스트 모니터링과 제어 (test monitoring and control)</span>**<br>
<span style="background-color:rgb(207,228,207);">테스트 모니터링</span>은 <span style="background-color:rgb(237,220,195);">테스트 계획에 정의된 테스트 모니터링 메트릭을 활용해 실제 진행 상황을 계획한 진척 상황과 지속적으로 비교하는 활동</span>을 말한다. <span style="background-color:rgb(207,228,207);">테스트 제어(test control)</span>는 <span style="background-color:rgb(237,220,195);">시간이 지나면서 업데이트될 수 있는 테스트 계획의 목적 달성을 위해 필요한 활동을 수행하는 것</span>이다. <span style="background-color:rgb(207,228,207);">종료 조건(exit criteria) 평가</span>도 <span style="background-color:rgb(237,220,195);">테스트 모니터링과 제어에 필요한 활동이며, 일부 소프트웨어 개발 수명주기 모델에서는 종료 조건을 완료의 정의(definition of done)로 칭하기도 한다 (ISTQB-CTFL-AT 참조).</span>

<span style="background-color:rgb(237,220,195);">예를 들어, 특정 테스트 레벨에서 이루어진 테스트 실행의 종료 조건 평가는 다음을 포함할 수 있다:</span>
- <span style="background-color:rgb(242,213,214);">명시된 커버리지 조건 대비 테스트 결과와 로그 확인</span>
- <span style="background-color:rgb(242,213,214);">테스트 결과와 로그를 기반으로 컴포넌트나 시스템의 품질 수준 평가</span>
- <span style="background-color:rgb(242,213,214);">추가 테스트 필요 여부 결정 (예: 일정 수준의 제품 리스크 커버리지를 달성하고자 했던 테스트가 그러지 못했을 경우, 추가적인 테스트 작성 및 실행 요구)</span>

<span style="background-color:rgb(237,220,195);">계획 대비 테스트 진행 상황은 이해관계자에게 테스트 진행 상황 보고서의 형태로 전달되며, 여기에는 계획 대비 편차와 테스팅을 그만하기로 결정했다면 그것을 뒷받침해 줄 정보도 포함되어야 한다.</span>

**<span style="background-color:rgb(207,228,207);">테스트 분석 (Test analysis)</span>**<br>
<span style="background-color:rgb(237,220,195);">테스트 분석에서는 테스트 가능한 기능과 연관된 테스트 컨디션을 식별하기 위해 테스트 베이시스를 분석한다. 즉, <span style="color:blue">테스트 분석은 측정 가능한 커버리지 조건의 측면에서 "무엇을 테스트할지"를 결정하는 것</span>이다.</span>

<span style="background-color:rgb(237,220,195);">테스트 분석의 주요 활동은 다음과 같다:</span>
- <span style="background-color:rgb(242,213,214);">고려 중인 테스트 레벨에 적합한 테스트 베이시스 평가. 예를 들어:</span>
  + <span style="background-color:rgb(207,225,232);">요구사항 명세. 여기에 포함되는 것으로는 비즈니스 요구사항, 기능 요구사항, 시스템 요구사항, 사용자 스토리, 에픽(epic), 유스케이스, 요구되는 기능/비기능 컴포넌트나 시스템의 동작이 명시된 유사한 작업 산출물 등이 있다.</span>
  + <span style="background-color:rgb(207,225,232);">설계와 구현 정보. 여기에 포함되는 것으로는 시스템이나 소프트웨어 아키텍처 다이어그램 또는 문서, 설계 명세, 콜흐름도(call flow graphs), 모델링 다이어그램 (예: UML 또는 개체-관계 다이어그램 (entity-relationship diagrams), 인터페이스 명세, 컴포넌트나 시스템 구조를 명시하고 있는 기타 유사한 작업 산출물 등이 있다.</span>
  + <span style="background-color:rgb(207,225,232);">구현한 컴포넌트나 시스템. 여기에 포함되는 것으로는 코드, 데이터베이스 메타데이터(database metadata), 쿼리(queries), 인터페이스 등이 있다.</span>
  + <span style="background-color:rgb(207,225,232);">컴포넌트나 시스템의 기능, 비기능, 구조 측면을 고려한 리스크 분석 보고서</span>
- <span style="background-color:rgb(242,213,214);">테스트 베이시스와 테스트 항목을 평가해서 다양한 형태의 결함 식별. 예를 들어:</span>
  + <span style="background-color:rgb(207,225,232);">모호함 (Ambiguities)</span>
  + <span style="background-color:rgb(207,225,232);">누락 (Omissions)</span>
  + <span style="background-color:rgb(207,225,232);">불일치 (Inconsistencies)</span>
  + <span style="background-color:rgb(207,225,232);">부정확 (Inaccuracies)</span>
  + <span style="background-color:rgb(207,225,232);">모순 (Contradictions)</span>
  + <span style="background-color:rgb(207,225,232);">불필요한 구문 (Superfluous Statements)</span>
- <span style="background-color:rgb(242,213,214);">테스트할 기능과 기능 세트 식별</span>
- <span style="background-color:rgb(242,213,214);">테스트 베이시스를 평가하고 기능, 비기능, 구조 특성, 기타 비즈니스 기술 요소, <span style="color:red">리스크 수준 등을 고려해서 각 기능에 대한 테스트 컨디션의 정의 및 우선순위 선정</span></span>
- <span style="background-color:rgb(242,213,214);">테스트 베이시스의 개별 요소와 연관된 테스트 컨디션 간의 양방향 추적성 포착 (1.4.3 절, 1.4.4 절 참조)</span>

<span style="background-color:rgb(237,220,195);">테스트 분석(4 장 참조)에 블랙박스, 화이트박스, 경험 기반 기법을 적용하면 주요 테스트 컨디션의 누락을 방지하고 더 정확하고 정밀한 테스트 컨디션 도출에 도움이 될 수 있다<br>
<span style="color:blue">테스트 분석의 결과로 테스트 차터(test charter)의 테스트 목적으로 사용할 테스트 컨디션이 생성되는 경우도 있다. 테스트 차터는 일부 경험 기반 테스팅 유형에서 일반적으로 사용하는 작업 산출물이다</span> (4.4.2 절 참조). 테스트 목적과 테스트 베이시스 간의 추적성을 확인할 수 있는 경우, 이런 경험 기반 테스팅으로 달성하는 커버리지를 측정할 수 있다<br>
테스트 분석 중 결함 식별은 큰 잠재적 이점이다. 특히, 사용하는 리뷰 프로세스가 없거나 테스트 프로세스가 리뷰 프로세스와 밀접하게 연관된 경우 더 그렇다. 이런 테스트 분석 활동은 요구사항이 일관성 있게 제대로 설명되고 완성되었는지 검증할 뿐 아니라, 요구사항이 고객, 사용자, 기타 이해관계자의 요구를 제대로 반영하고 있는지 확인하게 해준다. 예를 들면 코딩(coding) 전에 사용자 스토리와 인수 조건으로부터 테스트 컨디션과 테스트 케이스를 도출하는 행위 주도 개발(BDD, Behavior Driven Development)과 인수 테스트 주도 개발(ATDD, Acceptance Test Driven Development)이 있다. 이런 기법에서는 사용자 스토리와 인수 조건에 대해서도 검증, 확인, 결함 발견 활동을 수행한다 (ISTQB CTFL-AT 참조).</span>

**<span style="background-color:rgb(207,228,207);">테스트 설계 (Test design)</span>**<br>
<span style="background-color:rgb(237,220,195);">테스트 설계에서 테스트 컨디션을 기반으로 상위 수준 테스트 케이스, 상위 수준 테스트 케이스 세트, 기타 테스트웨어(testware)를 생성한다. 즉, 테스트 분석은 "무엇을 테스트할 것인가?"라는 질문에 답변하는 반면, <span style="color:blue">테스트 설계는 "어떻게 테스트할 것인가?"를 다루게 된다.</span></span>

<span style="background-color:rgb(237,220,195);">테스트 설계에 속하는 주요 활동은 다음과 같다:</span>
- <span style="background-color:rgb(242,213,214);">테스트 케이스와 테스트 케이스 세트 설계 및 우선순위 선정</span>
- <span style="background-color:rgb(242,213,214);">테스트 컨디션과 테스트 케이스에 필요한 테스트 데이터 식별</span>
- <span style="background-color:rgb(242,213,214);">테스트 환경 설계와 필요한 인프라 및 도구 식별</span>
- <span style="background-color:rgb(242,213,214);">테스트 베이시스, 테스트 컨디션, 테스트 케이스 간의 양방향 추적성 설정 (1.4.4 절 참조)</span>

<span style="background-color:rgb(237,220,195);">테스트 설계 중 테스트 컨디션을 테스트 케이스와 테스트 케이스 세트로 전환할 때 테스트 기법을 사용하는 경우가 많다 (4 장 참조). 테스트 분석과 마찬가지로, 테스트 설계에서도 테스트 베이시스에서 유사한 유형의 결함을 식별할 수 있다. 또한, 테스트 설계 중 결함 식별은 테스트 분석에서와 마찬가지로 큰 잠재적 이점이다.</span>

**<span style="background-color:rgb(207,228,207);">테스트 구현 (Test implementation)</span>**<br>
<span style="background-color:rgb(237,220,195);">테스트 구현 중 테스트 실행에 필요한 테스트웨어를 생성하고 완성하며, <span style="color:blue">테스트 케이스를 배치해서 테스트 프로시저를 만드는 것도 여기에 포함</span>된다. 결국, 테스트 설계는 "어떻게 테스트할 것인가?"라는 질문에 대한 답을 제공하는 반면, <span style="color:blue">테스트 구현은 "테스트를 실행하기 위해 필요한 모든 것이 갖춰져 있는가?"라는 질문에 답하는 활동</span>이다.</span>

<span style="background-color:rgb(237,220,195);">테스트 구현에 속하는 주요 활동은 다음과 같다:</span>
- <span style="background-color:rgb(242,213,214);">테스트 프로시저의 개발과 우선순위 선정, 가능하다면 자동 테스트 스크립트 생성</span>
- <span style="background-color:rgb(242,213,214);">테스트 프로시저와 (있다면) 자동 테스트 스크립트로부터 테스트 스위트(test suite) 생성</span>
- <span style="background-color:rgb(242,213,214);">효과적인 테스트 실행이 가능하도록 테스트 스위트를 테스트 실행 일정 내에 배치 (5.2.4 절 참조)</span>
- <span style="background-color:rgb(242,213,214);">테스트 환경 구축, 가능하다면 테스트 하네스(test harness), 서비스 가상 현실화, 시뮬레이터, 기타 인프라 항목까지, 또 필요한 모든 사항을 제대로 구현했는지 확인</span>
- <span style="background-color:rgb(242,213,214);">테스트 데이터를 준비하고, 테스트 환경에 제대로 입력했는지 확인</span>
- <span style="background-color:rgb(242,213,214);">테스트 베이시스, 테스트 컨디션, 테스트 케이스, 테스트 프로시저, 테스트 스위트 서로 간의 양방향 추적성 검증과 업데이트 (1.4.4 절 참조)</span>

<span style="background-color:rgb(237,220,195);">테스트 설계와 테스트 구현 작업은 합쳐지는 경우가 많다.<br>
탐색적 테스팅과 기타 경험 기반 테스팅 유형에서 테스트 설계와 구현이 테스트 실행의 일부로 이루어지거나 기록될 수 있다. 탐색적 테스팅은 테스트 분석에서 생성되는 테스트 차터를 기반으로 이루어질 수 있으며, 탐색적 테스트는 설계되고 구현되면서 바로 실행된다 (4.4.2 절 참조).</span>

**<span style="background-color:rgb(207,228,207);">테스트 실행 (Test execution)</span>**<br>
<span style="background-color:rgb(237,220,195);">테스트 실행 단계에서는 테스트 스위트를 테스트 실행 일정에 따라 실행한다.</span>

<span style="background-color:rgb(237,220,195);">테스트 실행의 주요 활동은 다음과 같다:</span>
- <span style="background-color:rgb(242,213,214);">테스트 항목, 테스트 대상, 테스트 도구, 테스트웨어 등의 고유번호(ID)와 버전 기록</span>
- <span style="background-color:rgb(242,213,214);">테스트를 수동으로 혹은 테스트 실행 도구를 활용해서 실행</span>
- <span style="background-color:rgb(242,213,214);">기대 결과와 실제 결과 비교</span>
- <span style="background-color:rgb(242,213,214);">이상 현상(anomalies)을 분석해 원인 파악 (예를 들어, 장애가 코드 결함 때문에 발생할 수도 있지만 거짓양성일 수도 있다 (1.2.3 절 참조)).</span>
- <span style="background-color:rgb(242,213,214);">관찰한 장애를 기반으로 결함 보고 (5.6 절 참조)</span>
- <span style="background-color:rgb(242,213,214);">테스트 실행 결과 기록(예:합격, 불합격, 실행할 수 없음)</span>
- <span style="background-color:rgb(242,213,214);">이상 현상 때문에 취한 활동의 결과로 인해 또는 계획된 테스팅의 일부로 테스트 활동 반복(예:수정된 테스트 실행, 확인 테스팅이나 리그레션 테스팅 등)</span>
- <span style="background-color:rgb(242,213,214);">테스트 베이시스, 테스트 컨디션, 테스트 케이스, 테스트 프로시저, 테스트 결과 간의 양방향 추적성 검증과 업데이트</span>

**<span style="background-color:rgb(207,228,207);">테스트 완료 (Test completion)</span>**<br>
<span style="background-color:rgb(237,220,195);">테스트 완료 활동은 완료한 테스트 활동에서 데이터를 수집해서 경험, 테스트웨어, 기타 관련 정보를 축적하는 활동이다. 테스트 완료 활동은 소프트웨어 시스템을 릴리스 했을 때, 테스트 프로젝트를 완료(또는 취소)했을 때, 애자일 반복주기가 끝났을 때, 특정 테스트 레벨을 완료했을 때, 또는 유지보수 릴리스를 완료했을 때와 같은 프로젝트 마일스톤 시점에서 일어난다.</span>

<span style="background-color:rgb(237,220,195);">테스트 완료의 주요 활동은 다음과 같다:</span>
- <span style="background-color:rgb(242,213,214);">모든 결함 보고 처리를 완료했는지, 테스트 실행 후 해결되지 않은 모든 결함에 대해 수정 요청서 또는 프로젝트 백로그 항목을 생성했는지 확인</span>
- <span style="background-color:rgb(242,213,214);">이해관계자에게 전달할 테스트 요약 보고서 생성</span>
- <span style="background-color:rgb(242,213,214);">차후 재사용을 위해 테스트 환경, 테스트 인프라, 기타 테스트웨어의 마무리 및 보관</span>
- <span style="background-color:rgb(242,213,214);">테스트웨어를 유지보수팀, 다른 프로젝트팀, 그것을 활용할 수 있는 기타 이해관계자 등에게 인계</span>
- <span style="background-color:rgb(242,213,214);">완료한 테스트 활동을 통해 얻은 교훈을 분석해서 향후 반복주기, 릴리스, 또는 프로젝트를 위해 수정해야 하는 사항 판단</span>
- <span style="background-color:rgb(242,213,214);">테스트 프로세스 성숙도 개선을 위해 수집된 정보 활용</span>

## 1.4.3 테스트 작업 산출물 (Test Work Products)
{: .notice--success}

<span style="color:green">(K2) 테스트 프로세스를 지원하는 작업 산출물을 구별할 수 있다.</span>

테스트 작업 산출물은 테스트 프로세스의 일부로 생성된다. 조직마다 테스트 프로세스를 구현하는 방법이 다르듯이, 테스트 프로세스 중 생성되는 작업 산출물의 유형, 이 작업 산출물을 정리하고 관리하는 방법과 부르는 명칭 또한 다양하다. 이 실러버스는 위에서 설명한 테스트 프로세스와 이 실러버스 및 ISTQB 용어사전(glossary)의 작업 산출물을 기준으로 설명하고 있다. 작업 산출물에 대한 설명은 ISO 표준 (ISO/IEC/IEEE 29119-3)에서도 찾을 수 있다.
이 절에서 설명하고 있는 테스트 작업 산출물 중 다수는 테스트 관리 도구와 결함 관리 도구를 활용해서 작성 및 관리할 수 있다 (6 장 참조).

**테스트 계획 작업 산출물 (Testing planning work products)**<br>
테스트 계획 작업 산출물에는 일반적으로 하나 이상의 테스트 계획이 포함된다. 테스트 계획은 테스트 베이시스에 대한 정보를 포함한다. 테스트 베이시스는 추적성 정보를 통해 다른 작업 산출물뿐만 아니라, 테스트 모니터링과 제어에 사용되는 종료 조건(또는 완료 기준)과도 연결된다 (아래와 1.4.4 절 참조). 테스트 계획은 5.2 절에서 설명하고 있다.

**테스트 모니터링과 제어 작업 산출물 (Test monitoring and control work products)**<br>
테스트 모니터링과 제어 작업 산출물은 보통 지속적, 정기적으로 생성되는 <span style="color:blue">테스트 진행 현황 보고서</span>와 다양한 <span style="color:blue">테스트 완료 마일스톤에서 생성되는 테스트 요약 보고서</span>와 같은 여러 형태의 테스트 보고서를 포함한다. 모든 테스트 보고서는 작성일 기준 테스트 진행 상황 관련 필요한 정보를 독자에게 제공해야 한다. 테스트 실행 결과가 나오면 그것에 대한 요약도 포함해야 한다.
테스트 모니터링과 제어 작업 산출물은 작업 완료, 리소스 할당과 사용, 공수 등과 같이 프로젝트 관리에서 관심을 가지는 사항에 대해서도 다루어야 한다.

**테스트 분석 작업 산출물 (Test analysis work products)**<br>
<span style="color:blue">분석을 통해 식별되고 우선순위가 선정된 테스트 컨디션</span>은 테스트 분석 작업 산출물에 속한다. 이상적으로는 각 테스트 컨디션과 그것이 커버하는 테스트 베이시스 요소와의 양방향 추적성이 성립되어 있어야 한다. <span style="color:blue">탐색적 테스팅에서는 테스트 분석 중 테스트 차터를 생성</span>할 수 있다. 또, 테스트 분석에서 테스트 베이시스의 결함을 발견, 보고할 수 있다.

**테스트 설계 작업 산출물 (Test design work products)**<br>
테스트 설계의 결과로 <span style="color:blue">테스트 분석에서 정의한 테스트 컨디션을 실행할 수 있는 테스트 케이스와 테스트 케이스 세트</span>가 만들어진다. 입력 데이터와 기대 결과로 사용할 값이 고정되지 않은 상위 수준 테스트 케이스를 먼저 설계하는 것이 좋은 경우가 많다. 이런 상위 수준 테스트 케이스는 입력 데이터와 기대 결과값을 바꿔가면서 다양한 테스트 주기에서 재활용할 수 있으며, 동시에 테스트 케이스의 범위를 충분히 기록할 수 있게 해준다. 이상적으로는 각각의 테스트 케이스와 그것이 커버하는 테스트 컨디션 간의 양방향 추적성이 성립되어 있어야 한다.

<span style="color:blue">테스트 설계는 또한 다음과 같은 결과를 가져온다:</span>
- <span style="color:blue">필요한 테스트 데이터의 설계나 식별</span>
- <span style="color:blue">테스트 환경 설계</span>
- <span style="color:blue">인프라와 도구의 식별</span>

그러나 이런 결과를 문서로 기록하는 정도의 차이는 상당히 큰 편이다.

**테스트 구현 작업 산출물 (Test implementation work products)**<br>
테스트 구현 작업 산출물로는 다음과 같은 것들이 있다:
- <span style="color:blue">테스트 프로시저와 이 프로시저의 배열</span>
- <span style="color:blue">테스트 스위트</span>
- <span style="color:blue">테스트 실행 일정</span>

이상적인 상황에서는 테스트 구현이 끝나면, 테스트 케이스와 테스트 컨디션을 통해 테스트 프로시저와 테스트 베이시스 개별 요소 간의 양방향 추적성을 확인함으로써 테스트 계획에서 정의한 커버리지 조건의 달성 여부를 확인할 수 있다.<br>
테스트 구현이 도구를 사용하거나 도구로 생성되는 작업 산출물을 포함하는 경우도 있다. 예를 들어, 서비스 가상화와 자동 테스트 스크립트가 이런 경우에 해당한다.<br>
테스트 구현의 결과로 테스트 데이터와 테스트 환경을 구현 및 검증할 수도 있다. 데이터나 환경의 검증 결과에 대한 문서의 완성도는 경우에 따라 많이 다를 수 있다.
테스트 데이터는 테스트 케이스의 입력값과 기대 결과값에 확정값을 할당하는 데 사용한다. 해당값의 사용에 대한 세부적인 지침으로 이렇게 확정된 값은 상위 수준 테스트 케이스를 실행 가능한 하위 수준 테스트 케이스로 변화시킨다. 테스트 대상의 다른 릴리스에 대해 같은 상위 수준 테스트 케이스를 실행할 경우 다른 테스트 데이터를 사용할 수 있다. 확정된 테스트 데이터에 대한 확정 기대 결과값은 테스트 오라클(test oracle)을 통해 식별할 수 있다.<br>
탐색적 테스팅에서는 테스트 실행 중 테스트 설계 및 구현 작업 산출물을 생성할 수 있지만, 탐색적 테스트(테스트 베이시스의 개별 요소로의 추적성 포함) 중 무엇이 문서로 기록되는지는 상황에 따라 상당히 달라질 수 있다.<br>
테스트 분석에서 정의한 테스트 컨디션은 테스트 구현 중 추가로 개선할 수 있다.

**테스트 실행 작업 산출물 (Test execution work products)**<br>
테스트 실행 작업 산출물에는 다음과 같은 것들이 있다:
- <span style="color:blue">개별 테스트 케이스나 테스트 프로시저의 상태에 대한 문서</span> (예: 실행 준비 완료, 합격, 불합격, 실행하지 못함, 의도적으로 실행하지 않음 등)
- <span style="color:blue">결함 보고서</span> (5.6 절 참조)
- <span style="color:blue">테스팅에 사용한 테스트 항목, 테스트 대상, 테스트 도구, 테스트웨어 등에 대한 문서</span>

이상적인 상황에서는, 테스트 실행이 끝나면 연관된 테스트 프로시저와의 양방향 추적성을 활용해서 테스트 베이시스 개별 요소의 상태에 대해 판단하고 보고할 수 있다. 예를 들어, 우리는 모든 계획된 테스트에 합격한 요구사항이 무엇인지, 불합격한 테스트나 결함을 가지고 있는 요구사항이 무엇인지, 계획된 것 중 아직 실행하지 못한 테스트를 가지고 있는 요구사항이 무엇인지 얘기할 수 있다. 그 결과로 커버리지 조건 충족 여부를 검증할 수 있으며, 테스트 결과를 이해관계자가 이해할 수 있는 형태로 보고할 수 있다.

**테스트 완료 작업 산출물 (Test completion work products)**<br>
테스트 완료 작업 산출물로는 <span style="color:blue">테스트 요약 보고서, 차후 프로젝트나 반복주기의 개선을 위한 액션 아이템, 수정 요청서 혹은 제품 백로그 항목, 완성된 테스트웨어</span> 등이 있다.

## 1.4.4 테스트 베이시스와 테스트 작업 산출물 간의 추적성 (Traceability between the Test Basis and Test Work Products)
{: .notice--success}

<span style="color:green">(K2) 테스트 베이시스와 테스트 작업 산출물 간의 추적성을 유지하는 것이 어떻게 도움이 되는지 설명할 수 있다.</span>

테스트 작업 산출물과 그 작업 산출물의 명칭은 매우 다양하다. 비록 그렇다 하더라도 <span style="background-color:rgb(237,220,195);">효과적인 테스트 모니터링과 제어를 구현하기 위해서는 위에서 설명한 바와 같이, 테스트 프로세스 전반에 걸쳐 테스트 베이시스의 개별 요소 및 해당 요소와 연관된 다양한 테스트 작업 산출물 간의 추적성을 확립하고 유지하는 것이 중요하다. <span style="background-color:rgb(207,228,207);">좋은 추적성</span>은 테스트 커버리지에 대한 평가를 가능하게 할 뿐만 아니라 아래와 같은 장점도 제공한다:</span>
- <span style="background-color:rgb(242,213,214);">수정으로 인한 영향 평가를 가능하게 한다.</span>
- <span style="background-color:rgb(242,213,214);">테스팅에 대한 감사(audit)를 가능하게 한다.</span>
- <span style="background-color:rgb(242,213,214);">IT 통제(IT governance) 조건을 충족할 수 있게 한다.</span>
- <span style="background-color:rgb(242,213,214);">테스트 베이시스 개별 요소의 상태에 대한 정보(예: 연관된 테스트에 합격한 요구사항, 연관된 테스트에 불합격한 요구사항, 연관된 테스트를 다 실행하지 못한 요구사항)를 포함함으로써 테스트 진행 상황 보고서와 테스트 요약 보고서를 좀 더 쉽게 이해할 수 있게 한다.</span>
- <span style="background-color:rgb(242,213,214);">테스팅의 기술적인 내용을 이해관계자가 이해할 수 있는 형태로 전달한다.</span>
- <span style="background-color:rgb(242,213,214);">비즈니스 목표 대비 제품 품질, 프로세스 역량, 프로젝트 진행 상황 등을 평가할 수 있는 정보를 제공한다.</span>

테스트 관리 도구 중 이 절에서 다룬 테스트 작업 산출물 일부 또는 전부를 포함한 테스트 작업 산출물 모델을 제공하는 것도 있다. 작업 산출물을 정리하고 필요한 추적성 정보를 제공하기 위해 자체 관리 시스템을 구축하는 조직도 있다.

# 1.5 테스팅의 심리학 The Psychology of Testing
{: .notice--warning .text-center}

소프트웨어 테스팅을 포함한 소프트웨어 개발은 사람이 하는 일이다. 따라서, 인간 심리학은 소프트웨어 테스팅에 중요한 영향을 미친다.

## 1.5.1 인간 심리학과 테스팅 (Human Psychology and Testing)
{: .notice--success}

<span style="color:green">(K1) 테스팅의 성공에 영향을 주는 심리 요인을 식별할 수 있다.</span>

요구사항 리뷰나 사용자 스토리 개선 세션에서 결함을 식별하거나 동적 테스트 실행 중 장애를 발견하는 것은 테스트 대상 제품과 제작자에 대한 비판으로 오해 받을 소지가 있다. 인간 심리학의 한 요소인 확증 편향(confirmation bias)은 현재 가지고 있는 믿음과 맞지 않는 정보를 받아들이기 어렵게 만들 수 있다. 예를 들어, 개발자는 자신의 코드가 옳다고 생각하기 때문에 코드가 잘못됐다는 사실을 받아들이기 힘들게 하는 확증 편향을 가지고 있다. 확증 편향 외에도 사람들이 테스팅으로 얻은 정보를 이해하고 받아들이기 힘들게 하는 다른 인지 편향(cognitive biases)들도 있다. 또한, 나쁜 소식을 전달하는 사람을 탓하는 것은 인간이 가지고 있는 기본 성향 중 하나인데 테스팅으로 얻은 정보는 나쁜 소식을 포함하고 있는 경우가 많다.<br>
이런 심리학적인 요소로 인해, 테스팅이 프로젝트 진행과 제품 품질에 상당한 기여를 함에도 불구하고 (1.1 절과 1.2 절 참조) 테스팅을 파괴적인 활동으로 간주하는 사람들도 있다. 이런 편견을 줄이기 위해 결함과 장애에 대한 정보는 건설적인 방법으로 전달할 필요가 있다. 그렇게 함으로써 테스터와 분석가, 제품 소유자, 설계자, 개발자 간의 긴장을 완화할 수 있다. 이것은 정적, 동적 테스팅 모두에 해당한다.<br>
테스터와 테스트 관리자는 결함, 장애, 테스트 결과, 테스트 진행 상황, 리스크 등을 효과적으로 전달하기 위해, 또는 동료와 긍정적인 관계를 구축하기 위해 좋은 대인 관계 기술을 가질 필요가 있다. 다음은 의사소통을 더 잘할 수 있는 방법에 대한 예제이다:
- 다툼보다는 협력으로 시작하라. 더 나은 품질의 시스템을 개발한다는 공통 목표를 모두에게 인식시킨다.
- 테스팅의 이점을 강조하라. 예를 들어, 결함 정보는 저자가 자신의 작업 산출물의 품질과 역량을 향상하는 데 도움이 될 수 있다. 조직 차원에서 본다면, 테스팅 도중 발견하고 수정한 결함은 시간과 비용을 아껴주며 제품 품질의 전반적인 리스크를 낮춰준다.
- 테스트 결과와 기타 발견 사항을 중립적이면서 사실에 기반을 둔 방법으로 전달해야 한다. 결함이 발생한 항목을 제작한 사람을 비판해서는 안 된다. 객관적이고 사실에 기반을 둔 결함 보고서와 리뷰 결과서를 작성하라.
- 상대방이 어떤 느낌을 받을지, 또 해당 정보에 대해 부정적으로 반응하는 이유가 뭔지를 이해하려고 해야 한다.
- 상대방이 전달받은 내용을 이해했는지, 또 반대로 상대방이 하고자 하는 말을 제대로 이해했는지 확인하라.

일반적인 테스트 목적은 앞에서 다루었다 (1.1 절 참조). 올바른 테스트 목표 세트를 명확하게 정의하는 것은 심리학적으로도 중요한 영향을 미친다. 대부분의 사람은 자신의 일정과 행동을 팀, 관리자, 기타 이해관계자가 설정한 목표와 맞추려는 성향을 가진다. 테스터도 개인의 성향은 최대한 배제하고 이런 목표와 부합하려고 하는 자세가 매우 중요하다.

## 1.5.2 테스터와 개발자의 사고방식 (Tester’s and Developer’s Mindsets)
{: .notice--success}

<span style="color:green">(K2) 테스트 활동에 필요한 사고방식과 개발 활동에 필요한 사고방식을 구별할 수 있다.</span>

개발자와 테스터는 생각하는 방식이 다른 경우가 많다. 개발의 일차적인 목표는 제품을 설계하고 구축하는 것이다. 앞서 언급한 바와 같이, 테스팅의 목적은 제품에 대한 밸리데이션(확인 validation)과 베리피케이션 (검증 verification), 릴리스 전 결함 발견 등 다양하다. 이처럼 목적이 다르기 때문에 필요한 사고방식도 다르다. 이런 사고방식을 적절히 조합해서 사용하면 더 높은 수준의 제품 품질을 달성할 수 있다.<br>
사고방식은 개인이 가지고 있는 성향과 선호하는 결정 및 문제 해결 방식을 반영한다. <span style="color:red">테스터는 호기심, 전문적 비평(professional pessimism) 능력, 비판적 시각, 세밀한 것에 주목하는 태도, 긍정적인 의사소통과 관계 수립에 대한 동기 등의 사고방식</span>을 가지고 있어야 한다. 이 테스터의 사고방식은 테스터가 경험을 쌓아감에 따라 점차 확대되고 성숙해지는 경향을 가지고 있다.<br>
개발자의 사고방식에도 테스터의 사고방식과 같은 요소가 일부 있을 수 있지만, <span style="color:blue">성공적인 개발자는 해결책을 설계하고 구축하는 데 더 관심을 기울이며 그런 해결책에 무슨 문제가 있는지에 대해 관심을 가지는 경우는 많지 않다. 또한, 확증 편향(confirmation bias) 때문에 자신이 만든 오류에 대해 인지하기 어렵다.</span><br>
올바른 사고방식을 가지고 있다면, 개발자는 자신이 만든 코드를 직접 테스트할 수 있다. 소프트웨어 개발 수명주기 모델에 따라 테스터 구성 및 테스트 활동 방식이 다르다. 테스트 활동의 일부를 독립적인 테스터가 하면 결함 발견 효과를 높일 수 있는데, 이것은 특히 규모가 크고 복잡하며 안전이 필수적인 시스템일 경우 중요하다. 독립적인 테스터는 저자와는 다른 확증 편향을 가지기 때문에 작업 산출물 작성자(즉, 비즈니스 분석가, 제품 책임자, 설계자, 개발자 등)와는 다른 관점을 갖게 된다.

# ● 용어
{: .notice .text-center}

<details>
<summary>Keywords</summary>
<div markdown="1">

- 커버리지(coverage):<br>
참조 : ISO 29119<br>
유의어 : 테스트 커버리지(test coverage)<br>
커버리지 항목이 식별되거나 테스트 스위트(test suite)에 의해 수행된 정도를 백분율로 표시한 것

- 디버깅(debugging): 소프트웨어의 장애 원인을 찾아 분석하고 제거하는 프로세스

- 결함(defect):<br>
참조 : IEEE 1044<br>
유의어 : 버그(bug), 결점(fault)<br>
요구사항이나 명세를 충족시키지 못하는 작업 산출물의 불완전함 또는 결점

- 오류(error):<br>
참조 : ISO 24765<br>
유의어 : 실수(mistake)<br>
부정확한 결과를 만들어내는 인간의 행동

- 장애(failure):<br>
참조 : ISO 24765<br>
지정된 범위 내에서 요구되는 기능을 컴포넌트나 시스템이 수행하지 못하는 경우

- 품질(quality):<br>
참조 : ISO 24765<br>
컴포넌트나 시스템 또는 프로세스가 특정한 요구사항 및 사용자/고객의 요구와 기대를 충족시키는 정도

- 품질 보증(quality assurance):<br>
참조 : ISO 9000<br>
<span style="color:red">품질 관리의 일환으로, 품질 요구사항이 준수될 것이라는 신뢰를 제공하는 데 중점을 둠</span>

- 품질 제어(quality control):<br>
참조 : ISO 8402<br>
<span style="color:red">품질 관리의 일부로서 품질 요구사항을 준수하는 데 중점을 둔 운영상의 기술과 활동</span>

- 품질 관리(quality management):<br>
참조 : ISO 9000<br>
품질과 관련하여 조직을 감독하고 통제하는 조정 활동. 품질 관련 감독과 통제에는 일반적으로 품질 정책과 품질 목표 수립, 품질 계획, 품질 제어, 품질 보증 및 품질 개선이 포함됨

- 근본 원인(root cause):<br>
참조 : CMMI<br>
결함의 원인 중 제거되면 해당 결함유형 발생이 감소하거나 제거될 수 있는 원인

- 테스트 분석(test analysis): 테스트 베이시스(test basis)를 분석하여 테스트 컨디션을 식별하는 활동

- 테스트 베이시스(test basis):<br>
참조 : TMap<br>
테스트 분석 및 설계의 기초로 사용되는 지식 체계

- 테스트 케이스(test case):<br>
참조 : ISO 29119<br>
<span style="color:red">테스트 컨디션을 기반으로 개발된 사전조건, 입력값, 행동(해당하는 경우), 기대 결과, 사후조건의 집합</span>

- 테스트 완료(test completion):<br>
참조 : ISO 29119<br>
테스트 자산을 향후 이용 가능하게 하고, 테스트 환경을 만족스러운 상황으로 유지하고, 관련 이해당사자들에게 테스팅 결과를 전달하는 활동

- 테스트 컨디션(test condition):<br>
유의어 : 테스트 요구사항(test requirement), 테스트 상황(test situation)<br>
<span style="color:red">특정 테스트 목적 달성과 관련있는 테스트 베이시스(test basis)의 한 측면</span>

- 테스트 제어(test control):<br>
연관 항목 : 테스트 관리(test management)<br>
모니터링 결과 테스트 프로젝트가 계획에서 벗어나고 있다고 판단될 때, 다시 정상 궤도로 돌려놓으려는 시정조치의 개발 및 적용과 관련된 테스트 관리 업무

- 테스트 데이터(test data):<br>
참조 : ISO 29119<br>
<span style="color:red">하나 이상의 테스트 케이스를 실행하기 위한 입력값이면서, 실행 사전조건을 만족하도록 생성 되거나 선택된 데이터</span>

- 테스트 설계(test design):<br>
참조 : ISO 29119<br>
연관 항목 : 테스트 설계 명세(test design specification)<br>
테스트 컨디션으로부터 테스트 케이스를 유도하고 도출하는 활동

- 테스트 실행(test execution): 테스트 대상 컴포넌트나 시스템에 대한 테스트를 실행하고 실제 결과를 생성하는 프로세스

- 테스트 구현(test implementation): 테스트 분석과 설계를 기반으로 테스트 실행에 필요한 테스트웨어를 준비하는 활동

- 테스트 모니터링(test monitoring):<br>
연관 항목 : 테스트 관리(test management)<br>
테스트 활동의 상황을 확인하고, 계획된 또는 예상된 상태와의 편차를 식별하고 상태를 이해 관계자에게 보고하는 테스트 관리 활동

- 테스트 대상(test object):<br>
연관 항목 : 테스트 항목(test item)<br>
테스트할 컴포넌트나 시스템

- 테스트 목적(test objective): 테스트를 설계하고 실행하는 근거나 목적

- 테스트 오라클(test oracle):<br>
참조 : Adrion<br>
유의어 : 오라클(oracle)<br>
테스트중인 시스템의 실제 결과와 비교할 기대 결과를 판단하기 위한 출처

- 테스트 계획(test planning): 테스트 계획서의 수립 또는 수정 활동

- 테스트 절차(test procedure):<br>
참조 : ISO 29119<br>
연관 항목 : 테스트 스크립트(test script)<br>
실행 순서로 나열된 테스트 케이스 순서. 초기 사전조건을 설정하는 데 필요한 모든 관련 동작과 실행 이후의 모든 마무리 활동까지 포함

- 테스트 프로세스(test process): 테스트 계획, 테스트 모니터링 및 제어, 테스트 분석, 테스트 설계, 테스트 구현, 테스트 실행, 테스트 완료로 상호 연관되어 구성된 활동들의 집합

- 테스트 스위트(test suite):<br>
유의어 : 테스트 케이스 세트(test case set), 테스트 세트(test set)<br>
특정 테스트 주기에서 실행해야 하는 테스트 케이스의 집합이나 테스트 절차

- 테스팅(testing): 소프트웨어 제품 및 관련 작업산출물이 특정 요구사항을 충족하는지 확인하고, 목적에 부합하는지 여부를 입증하고, 결함을 발견하기 위해 정적/동적의 모든 계획, 준비, 평가와 관련된 수명주기 활동으로 구성된 프로세스

- 테스트웨어(testware):<br>
참조 : ISO 29119<br>
<span style="color:red">테스팅에 대한 계획, 설계, 실행, 평가, 보고 등에 활용하기위한 목적으로 테스트 프로세스 동안 생성되는 작업 산출물</span>

- 추적성(traceability):<br>
참조 : ISO 19506<br>
연관 항목 : 수평적 추적성(horizontal traceability), 수직적 추적성(vertical traceability)<br>
두 가지 이상의 작업 산출물 사이에 관계가 성립될 수 있는 정도

- 밸리데이션(확인 validation):<br>
참조 : ISO 9000<br>
의도된 특정 용도 또는 용도에 대한 요구사항이 충족되었음을 보증하기 위해 객관적 증거와 조사를 통해 확인하는 것

- 베리피케이션(검증 verification):<br>
참조 : ISO 9000<br>
특정 요구사항이 모두 구현되었는지를 객관적 증거와 조사를 통해 확인하는 것

- 사용자 스토리(user story):<br>
연관 항목 : 애자일 소프트웨어 개발(Agile software development), 요구사항(requirement)<br>
애자일 소프트웨어 개발에서 보편적으로 사용되는 상위 수준의 사용자 또는 비즈니스 요구사항. 일반적으로 일상 언어나 비즈니스 언어로 된 하나의 문장으로 구성되며, 사용자에게 필요한 기능, 필요한 이유, 연관된 비기능적 기준, 인수 조건 등을 설명

- 회고 회의(retrospective meeting):<br>
유의어 : 프로젝트 종료 후 회의(post-project meeting)<br>
프로젝트가 종료될 때 프로젝트 팀원들이 그동안의 프로젝트를 평가하고 다음 프로젝트에 적용할 수 있는 교훈을 공유하는 회의

- 마일스톤(milestone): 정해진 (중간)산출물과 결과가 준비완료되어야 하는 프로젝트의 특정 시점

- 감사(audit):<br>
참조 : IEEE 1028<br>
명세, 표준, 계약상의 합의사항, 그 밖의 기준에 대한 준수 여부를 평가하고자 제3자가 수행하는 작업 산출물, 프로세스 또는 프로세스 집합에 대한 독립적인 검사

</div>
</details>

# ● 샘플문제
{: .notice--danger .text-center}

A - Q1. 다음 중 테스트 컨디션(Test condition)을 설명하고 있는 것은?
- a. 컴포넌트나 시스템의 특이성
- b. 테스팅의 베이시스로 파악된 컴포넌트나 시스템의 테스팅 가능한 측면
- c. 소프트웨어를 특정조건에서 사용할 때 설명/제시된 필요기능을 충족할 수 있는 소프트웨어 제품 능력
- d. 조건의 조합에 따른 행동을 실행하도록 설계된 테스트 케이스

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.x (K1) 제 1 장 용어
- a. 오답- 용어 사전에 따르면 기능(feature)의 정의임
- b. 정답- 용어 사전 참조
- c. 오답- 용어 사전에 따르면 ‘기능 적합성(functionality suitability)’의 정의임
- d. 오답- 용어 사전에 따르면 결정 테이블 테스팅의 정의와 유사

</div>
</details>

---

A - Q2. 다음 중 테스팅의 목적으로 바른 것은?
- a. 좋은 제품 개발을 위해 충분한 시간이 있도록 테스트는 가능한 늦게 시작해야 한다.
- b. 테스트 대상이 사용자와 다른 이해관계자들이 예상한 대로 작동하는지 검증한다.
- c. 모든 가능한 결함이 식별되었다는 것을 증명한다.
- d. 남아있는 결함이 장애를 일으키지 않을 것이라는 것을 증명한다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.1.1 (K1) 테스팅의 일반적인 목적을 식별할 수 있다.
- a. 오답- 테스팅 7 원리의 3 번과 모순됨: “조기 테스팅은 시간과 비용을 절약하게 해준다.”
- b. 정답- 이것은 테스팅의 목적 중에 하나이다.
- c. 오답- 테스팅 7 원리 2번에 따르면, 완벽한 테스팅은 불가능하며 따라서 모든 결함을 찾았다고 말할 수 없다.
- d. 오답- 결함이 장애를 일으켰는지 판단하려면 반드시 먼저 결함을 발견해야 한다. 남아있는 결함이 장애를 일으키지 않을 것이라고 말하는 것은 모든 결함을 찾았다는 것을 의미하므로 테스팅 7 원리의 2 번에 위배되는 내용이다.

</div>
</details>

---

A - Q3. 다음 중 테스팅과 디버깅의 차이를 바르게 설명한 것은?
- a. 테스팅은 결함(defects)의 원인을 식별하고, 디버깅은 결함을 분석하고 예방 활동을 제안한다.
- b. 동적 테스팅은 결함으로 발생하는 장애(failures)를 보여주고, 디버깅은 장애의 원인인 결함을 제거한다.
- c. 테스팅은 결점(faults)을 제거하지만, 디버깅은 결점을 일으키는 결함을 제거한다.
- d. 동적 테스팅은 장애의 원인을 예방하고, 디버깅은 장애를 제거한다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.1.2 (K2) 테스팅과 디버깅을 구별할 수 있다.
- a. 오답- 테스팅으로 결함의 원인을 식별하지는 않으며, 디버깅은 결함의 원인을 식별한다.
- b. 정답- 동적 테스팅으로 소프트웨어에 있는 결함 때문에 장애가 발생한다는 것을 보여줄 수 있다. 디버깅은 결함의 근본 원인이 아닌 장애의 원인인 결함을 제거한다.
- c. 오답- 테스팅은 결점(faults)를 제거하지는 않지만, 디버깅은 결점, 즉 장애를 일으킬 수 있는 결함(defects)을 제거한다.
- d. 오답- 동적 테스팅은 장애(결함)의 원인을 직접적으로 예방하지는 않지만, 결함이 존재함을 찾아낸다.

</div>
</details>

---

A - Q4. 다음 중 테스팅이나 개발과정에서 발견되는 가장 흔한 장애상황을 설명하는 것은?
- a. 사용자가 대화상자에서 옵션을 선택할 때 화면 깨짐 현상이 발생했다.
- b. 빌드에 잘못된 버전의 소스코드 파일이 들어갔다.
- c. 계산 알고리즘에 잘못된 입력값을 사용했다.
- d. 개발자가 요구사항을 알고리즘으로 구현할 때 잘못 구현했다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.2.3 (K2) 오류, 결함, 장애을 구별할 수 있다.
- a. 정답- 화면 깨짐은 사용자에게 명백하게 드러나는 현상이다.
- b. 오답- 코드에 문제가 있으므로 장애가 아닌 결함에 대한 설명이다. 예를 들어, 소스 코드의 주석만 변경되었다면 이 결함은 눈에 띄는 장애를 일으키지 않을 수 있다.
- c. 오답- 잘못된 입력 변수 사용은 눈에 띄는 장애를 가져오지 않을 수 있다. 예를 들어 아무도 이 특정 알고리즘을 사용하지 않거나, 잘못된 입력 변수가 올바른 입력 변수와 유사한 값을 갖는다거나 또는 알고리즘의 FALSE 결과가 사용되지 않았을 경우 등 있다.
- d. 오답- 이런 유형의 오류는 반드시 장애로 이어지지는 않는다. 예를 들면 아무도 이 특이한 알고리즘을 사용하지 않을 경우 등.

</div>
</details>

---

A - Q5. 김태수씨는 5 년간 모바일 장치 소프트웨어 애플리케이션을 테스트했다. 그는 모바일 애플리케이션 테스트에 대한 풍부한 경험을 보유하고 있으며 다른 사람들보다 짧은 시간 내에 더 나은 결과를 얻는다. 몇 개월 동안 김태수씨는 기존의 자동화된 테스트 케이스를 수정하지 않았고 새로운 테스트 케이스를 만들지도 않았다. 이로인해 테스트 수행 시 발견되는 결함이 점점 줄어드는 결과를 가져왔다.

김태수씨는 어떤 테스트 원리를 준수하지 않았는가?
- a. 테스트는 환경에 따라 달라진다.
- b. 완벽한(Exhaustive) 테스팅은 불가능하다.
- c. 동일한 테스트의 반복은 새로운 결함을 발견하지 못할 것이다.
- d. 결함은 서로 군집(cluster)한다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.3.1 (K2) 테스팅의 7 가지 원리를 설명할 수 있다.
- a. 오답- 테스팅은 수동이든 자동이든 상관없이 정황에 의존적이다 (실러버스 1.3, 테스팅 원리 6번 참조). 그러나 위에 설명된 대로 오류의 수가 감소하는 것은 감지하지 못한다.
- b. 오답- 테스팅에 소요되는 노력에 상관없이 완벽한 테스팅은 불가능하다(실러버스 1.3 테스팅 원리 2 번 참조).
- c. 정답- 실라버스 1.3 테스팅 원리 5 번에 따르면, “동일한 테스트를 반복하면 결국 이들 테스트는 더 이상 새로운 결함을 찾지 못한다. 새로운 결함 발견하려면, 기존 테스트와 테스트 데이터를 변경해야 할 수 있으며, 새로운 테스트를 작성해야 할 수 있다”. 같은 테스트 케이스에 대한 자동화된 리그레션 테스팅은 새로운 결과를 가져오지 않는다.
- d. 오답- “결함 집중(Defect cluster together)”(실러버스 1.3 테스팅 원리 테스팅원리 4 번 참조). 적은 수의 모듈에는 보통 대부분의 결함이 포함되지만 점점 적은 결함이 발견된다는 뜻은 아니다.

</div>
</details>

---

A - Q6. 테스팅은 어떤 면에서 품질 보증의 일부가 될 수 있는가?
- a. 테스팅은 요구사항이 충분히 상세하다는 것을 보증한다.
- b. 테스팅은 소프트웨어 품질 저하 리스크 수준을 낮춰준다.
- c. 테스팅은 조직이 표준을 준수했다는 것을 보증한다.
- d. 테스팅은 실행한 테스트 케이스 수로 소프트웨어 품질을 측정한다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.2.2 (K2) 품질 보증과 테스팅의 관계를 설명하고, 높은 품질 확보에 테스팅이 어떻게 기여하는지 예를 들 수 있다.
- a. 오답- 정적 테스팅(리뷰)는 요구사항이 상세한지에 대해 기여는 할 수 있지만 보장할 수는 없다.
- b. 정답- 실러버스 1.2.2 참조. 테스팅은 다양한 방식으로 품질 목표 달성에 기여한다. 예를 들면, 부적당한 소프트웨어 품질 리스크를 줄여준다.
- c. 오답- 테스팅이 아닌 품질 보증에 대한 설명이다.
- d. 오답- 테스트 케이스 실행 결과를 무시하고 테스트 케이스 실행 수만 계산해서는 품질을 측정할 수 없다.

</div>
</details>

---

A - Q7. 다음 중 테스트 프로세스의 주요 활동인 “테스트 분석(Test Analysis)” 에 해당하는 활동은?
- a. 필요한 인프라(infrastructure)와 도구 식별
- b. 테스트 스크립트로 테스트 스위트 생성
- c. 프로세스 개선을 위한 교훈 도출
- d. 테스트 베이시스의 테스트 용이성 평가

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.4.2 (K2) 테스트 프로세스의 테스트 활동과 연관된 작업에 대해 설명할 수 있다.
- a. 오답- 이는 테스트 설계 활동에서 수행한다.
- b. 오답- 이는 테스트 구현 활동에서 수행한다.
- c. 오답- 이는 테스트 완료 활동에서 수행한다.
- d. 정답- 이는 테스트 분석 활동에서 수행한다.

</div>
</details>

---

A - Q8. 각각의 테스트 산출물(1-4 번)과 그에 대한 설명(A-D)을 바르게 연결한 것은?
1. 테스트 스위트
2. 테스트 케이스
3. 테스트 스크립트
4. 테스트 차터

- A. 특정 테스트 주기(run)에서 실행해야 하는 테스트 스크립트 세트
- B. 테스트 실행을 위한 일련의 지침
- C. 기대결과를 포함하고 있음
- D. 세션-기반 탐색적 테스팅에서의 테스트 활동 문서

- a. 1-A, 2-C, 3-B, 4-D
- b. 1-D, 2-B, 3-A, 4-C
- c. 1-A, 2-C, 3-D, 4-B
- d. 1-D, 2-C, 3-B, 4-A

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.4.3 (K2) 테스트 프로세스를 지원하는 작업 산출물을 구별할 수 있다.<br>
용어집(Glossary)은 아래 테스트를 다음과 같이 정의하고 있다:
- 테스트 스위트: “특정 테스트 주기(run)에서 실행해야 하는 테스트 케이스의 집합이나 테스트 절차(procedures).” (1A).
- 테스트 케이스: 테스트 컨디션에 기반하여 개발된 전제 조건, 입력값, 조치(적용 가능한 경우), 기대결과 및 사후 조건의 조합이다 (2C).
- 테스트 스크립트: 테스트 실행을 위한 일련의 지침이다 (3B).
- 테스트 차터: 테스트 목적과 어떤 테스트를 어떻게 수행할지에 대한 아이디어를 적은 것. 세션 기반 탐색적 테스팅에서의 테스트 활동 문서 (4D).

따라서 a) 가 정답이다.

</div>
</details>

---

B - Q1. 다음 중 테스트 케이스의 용어 정의를 설명하는 것은?
- A. 모든 값(value)이 명세 기반으로 동일하게 다루어질 것으로 예상되는 컴포넌트나 시스템 내 변수 값 영역의 부분집합(subset)
- B. 테스트 컨디션(test conditions)에 기초해 개발한 일련의 사전조건, 입력, 행동, 예상 결과 및 사후조건
- C. 테스팅 계획, 설계, 실행, 평가 및 보고에서 사용하기 위해 테스트 프로세스 동안 생산한 작업물 (work products)
- D. 테스트 중인 시스템의 실제 결과와 비교할 예상 결과를 결정하는 소스

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.x (K1) 제 1 장 용어
- A. 오답- 동등 파티션(equivalence partition)의 정의
- B. 정답- 용어 사전에 나오는 테스트 케이스의 정의
- C. 오답- 용어 사전에 나오는 테스트웨어(testware)의 정의
- D. 오답- 용어 사전에 나오는 테스트 오라클(oracle)의 정의

</div>
</details>

---

B - Q2. 다음 중 테스팅의 일반적인 목적 중 하나인 것은?
- A. 결함과 장애 발견
- B. 프로젝트 계획이 요구대로 진행되는지 확인
- C. 완전한 테스팅 보장
- D. 실제 결과와 예상 결과의 비교

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.1.1 (K1) 테스팅의 일반적인 목적을 식별할 수 있다.
- A. 정답- 테스팅의 주요 목적 중 하나이다.
- B. 오답- 프로젝트 계획서를 확인하는 것은 프로젝트 관리 활동이다.
- C. 오답- 원칙 2 번과 모순: 완전한/철저한 테스팅은 불가능하다.
- D. 오답- “실제 결과와 예상 결과의 비교”는 테스트 수행 활동이지 테스트 목표는 아니다.

</div>
</details>

---

B - Q3. 다음 중 자동차의 자동 주행속도 유지 시스템의 장애로 볼 수 있는 것은?
- A. 시스템 개발자가 잘라 붙이기(cut-and-paste) 후 변경된 부분에 대한 이름 수정을 잊어버렸다.
- B. 후진 시 경고음을 울리는 불필요한 코드가 시스템에 들어갔다.
- C. 라디오 볼륨을 키우거나 줄일 때 시스템이 설정 속도를 유지하지 못한다.
- D. 시스템의 설계 명세에 km/h 속도 단위가 잘못 표기되었다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.2.3 (K2) 오류, 결함, 장애을 구별할 수 있다.
- A. 오답- 개발자에 의한 실수의 한 예이다.
- B. 오답- 결함의 예이다 (코드의 문제가 장애를 일으킬 수 있다).
- C. 정답- 예상했던 기능과 다른 부분이다. 자동 주행속도 유지 시스템은 라디오의 영향을 받지 않아야 한다.
- D. 오답- 결함의 예이다(명세서의 문제는 이후 구현 단계에서 장애를 일으킬 수 있다).

</div>
</details>

---

B - Q4. 다음 중 피트니스 추적기(fitness tracker) 앱의 근본원인이기 보다는 결함인 것은?
- A. 요구사항 작성자가 피트니스 교육분야에 익숙하지 않아 사용자가 심장박동을 시간당 박동 수(bph: beat per hour)로 측정하길 원한다고 잘못 가정했다.
- B. 스마트폰 인터페이스를 테스트하는 테스터가 상태 전이 테스팅을 배운 적이 없어 주요 결함을 놓쳤다.
- C. GPS 기능에 들어간 잘못된 구성 변수(configuration variable)로 인해 일광절약시간 동안 위치 문제가 발생할 수 있다.
- D. 인터페이스 설계자가 전에 웨어러블 기기를 사용해본 적이 없어서 사용자 태양광 반사 효과를 잘못 이해했다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.2.4 (K2) 결함의 근본 원인과 그것의 영향을 구별할 수 있다.
- A. 오답- 요구사항 작성자의 피트니스 분야 경험이 적은 것은 근본 원인(root cause)이다.
- B. 오답- 테스터의 상태 전이 테스팅 교육 부족은 결함의 근본 원인 중 하나이다 (개발자가 결함을 초래했을 수 있다).
- C. 정답- 잘못된 구성 데이터는 피트니스 추적기 소프트웨어의 결점(결함)을 나타내며, 장애를 일으킬 수 있다.
- D. 오답- 웨어러블 장비의 사용자 인터페이스 설계에서 경험 부족은 결함 근본원인의 전형적인 예이다.

</div>
</details>

---

B - Q5. 리스크 분석 결과로 초기 테스트에서 평균보다 많은 결함을 발견한 시스템 영역에 대해 추가 테스팅을 진행하기로 했다.<br>
다음 중 위에 적용된 테스팅 원리는?
- A. 살충제 패러독스에 유의하라.
- B. 테스팅은 정황에 의존적이다.
- C. 오류 부재는 궤변이다.
- D. 결함은 집중된다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.3.1 (K2) 테스팅의 7 가지 원리를 설명할 수 있다.
- A. 오답- ‘살충제 패러독스’는 동일한 테스트 재수행 시 결함 발견 효율이 떨어지는 것을 의미한다.
- B. 오답- 이 테스팅 원리는 정황(예: 게임 vs. 안전 최우선)에 따라 테스팅을 달리 수행해야 함을 의미한다.
- C. 오답- 이 테스팅 원리는 테스트 및 수정을 거친 시스템과 확인된(validated) 시스템의 차이를 설명한다. ‘에러’가 없다고 시스템이 사용에 적합하다는 의미는 아니다.
- D. 정답- 결함이 집중된 영역(시스템에서 평균보다 많은 결함이 있는 곳)이 식별되면, 이 영역에 테스팅 노력을 집중해야 한다.

</div>
</details>

---

B - Q6. 다음은 테스트 활동과 업무이다:
- a. 테스트 설계
- b. 테스트 구현
- c. 테스트 실행
- d. 테스트 완료

1. 미해결(open) 결함에 대한 상태 변경 요청
2. 테스트 케이스에서 수행할 테스트 데이터 식별
3. 테스트 프로시저의 우선순위화와 테스트 데이터 생성
4. 불일치를 분석하여 해당 불일치의 원인 판단

다음 중 위의 테스트 활동(a-d)과 각 활동에서 수행하는 일(1-4)을 맞게 연결한 것은?
- A. a-2, b-3, c-4, d-1
- B. a-2, b-1, c-3, d-4
- C. a-3, b-2, c-4, d-1
- D. a-3, b-2, c-1, d-4

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.4.2 (K2) 테스트 프로세스의 테스트 활동과 연관된 작업에 대해 설명할 수 있다.<br>
실러버스 1.4.2 의 내용에 따라 다음과 같이 연결할 수 있다:
- a. 테스트 설계 - (2) 테스트 케이스에서 수행할 테스트 데이터 식별
- b. 테스트 구현 - (3) 테스트 프로시저의 우선순위화와 테스트 데이터 생성
- c. 테스트 실행 - (4) 불일치를 분석하여 원인을 판단
- d. 테스트 완료 - (1) 미해결(open) 결함에 대한 상태 변경 요청

따라서 정답은 A 이다.

</div>
</details>

---

B - Q7. 테스트 베이시스와 테스트 산출물 간 추적성 유지의 가치를 가장 잘 설명한 것은?
- A. 초기 요구사항 변경에 기반해 유지보수 테스팅을 모두 자동화할 수 있다.
- B. 새로운 테스트 케이스가 요구사항 커버리지를 증가시켰는지 판단할 수 있다.
- C. 테스트 관리자는 어느 테스터가 가장 심각한 결함을 찾았는지 알 수 있다.
- D. 변경으로 인한 부작용(side-effect)의 영향을 받는 영역을 확인 테스팅 대상으로 선정할 수 있다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.4.4 (K2) 테스트 베이시스와 테스트 작업 산출물 간의 추적성을 유지하는 것이 어떻게 도움이 되는지 설명할 수 있다.
- A. 오답- 새로운 요구사항에 대한 지원이 없어도 추적성을 통해 기존의 테스트 케이스를 수정 또는 삭제된 요구사항과 연결할 수 있지만, 유지보수 테스팅의 자동화를 돕는 것은 아니다.
- B. 정답- 모든 테스트 케이스가 요구사항과 연결되어 있다면, 새로운 테스트 케이스를 추가할 때마다 전에 커버되지 않았던 요구사항이 새로운 테스트 케이스로 커버되었는지 확인할 수 있다.
- C. 오답- 테스트 베이시스와 테스트 산출물 간의 추적성으로 어느 테스터가 심각도 높은 결함을 찾았는지 알 수 없고, 이런 정보를 안다 해도 그 가치는 제한적이다.
- D. 오답- 추적성은 변경에 영향을 받는 테스트 케이스 식별에 도움을 주지만, 부작용에 영향을 받는 영역은 리그레션 테스팅에서 중요한 부분이다.

</div>
</details>

---

B - Q8. 다음 중 개발자보다는 테스터에게서 더 잘 발견되는 특성은?
- A. 테스터는 경험을 쌓아가면서 마음가짐(mindset)이 성장하고 성숙하는 경향이 있다.
- B. 무엇이 잘못될지 예견할 수 있는 능력
- C. 팀원들과의 원만한 의사소통
- D. 모든 작업을 완수하는 것에 집중

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.5.2 (K2) 테스트 활동에 필요한 사고방식과 개발 활동에 필요한 사고방식을 구별할 수 있다.
- A. 오답- 개발자와 테스터 모두 경험으로부터 배운다.
- B. 정답- 개발자들은 종종 어떤 부분이 잘못 될 수 있다는 생각보다는 제품/서비스를 설계하고 구축하는 데 더 관심이 있다.
- C. 오답- 개발자와 테스터 모두 원만한 의사소통 능력이 있어야 한다.
- D. 오답- 테스터는 양이 아니라 질에 집중해야 한다.

</div>
</details>

---

C - Q1. 품질이란 무엇인가?
- a. 품질 요구사항을 충족하는지에 대한 자신감 제공에 중점을 두는 활동들
- b. 컴포넌트나 시스템이 다양한 이해관계자의 명시적/묵시적 요구를 충족시키는 정도
- c. 개인 또는 다른 컴포넌트/시스템이 권한의 유형과 수준에 적당한 접근성을 갖도록 컴포넌트/시스템이 얼마나 정보와 데이터를 보호하는지의 정도
- d. 품질 활동이나 품질 문제로 인해 발생하는 총 비용으로, 예방 비용, 평가 비용, 내부 장애 비용, 외부 장애 비용으로 나뉘어짐

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

용어, K1
- a. 오답- 품질 보증의 정의이다.
- b. 정답- 품질의 정의이다.
- c. 오답- 보안의 정의이다.
- d. 오답- 품질 비용의 정의이다.

</div>
</details>

---

C - Q2. 다음 중 일반적인 테스트 목적에 해당하는 것은?
- a. 결함 예방
- b. 결함 수정
- c. 실제 결과와 기대 결과의 비교
- d. 장애 원인 분석

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.1.1, K1
- a. 정답- 테스팅의 목적 중 하나이다.
- b. 오답- 이는 디버깅에 대한 설명이다.
- c. 오답- 이는 테스트 프로세스의 테스트 실행 활동 중 하나이다.
- d. 오답- 이는 디버깅 활동의 일부를 설명하는 것이다.

</div>
</details>

---

C - Q3. 옆 자리에서 울리는 전화 소리 때문에 개발자가 입력값의 상위 경계값을 확인하는 로직의 프로그램을 잘못 작성한다. 그 후 시스템 테스팅 수행 중에 테스터는 이 입력 필드에 잘못된 값이 입력되는 것을 발견한다.<br>
상위 경계값 확인을 위해 잘못 코딩된 로직은 다음 중 무엇에 해당하는가?
- a. 근본 원인
- b. 장애
- c. 오류
- d. 결함

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.2.4, K2
- a. 오답- 근본 원인은 프로그래머가 프로그램을 작성할 때 도출하는 것이다.
- b. 오답- 유효하지 않은 입력값을 허용하는 것이 장애이다.
- c. 오답- 오류는 코드에 결함을 일으키는 잘못된 사고이다.
- d. 정답- 코드에 있는 문제점이 결함이다.

</div>
</details>

---

C - Q4. 프로젝트 담당자는 애자일팀의 테스터인 당신의 역할이 매 반복주기가 끝나기 전에 모든 결함을 찾는 것이라고 말한다.<br>
다음 중 이런 (잘못된) 설명에 대한 대답으로 사용할 수 있는 테스팅 원리는?
- a. 결함은 집중된다(Defect clustering).
- b. 테스팅은 결함의 존재를 보여준다(Testing shows the presence of defects).
- c. 오류 부재는 궤변이다(Absence of error fallacy).
- d. 근본 원인 분석(Root cause analysis)

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.3.1, K2
- a. 오답- 결함 집중은 결함이 발견될 가능성이 높은 영역과 관련이 있다. 모든 결함을 다 찾을 수 있는 것은 아니다.
- b. 정답- 테스팅은 결함이 존재함을 보여주지만 결함이 없다는 것을 증명할 수는 없으므로 모든 결함을 다 찾아냈는지는 확인할 수 없다. 게다가, 완벽한 테스팅은 불가능하므로 테스팅으로 모든 결함을 찾는 것 자체가 불가능하다.
- c. 오답- 이 원리는 많은 결함을 찾아내고 제거할 수는 있지만 제품 소유자가 보증하도록 요청한 제품이 아닌 성공적이지 못한 소프트웨어 제품을 출시할 수도 있음을 의미한다.
- d. 오답- 근본 원인 분석은 테스팅의 원리가 아니다.

</div>
</details>

---

C - Q5. 단위 테스팅을 하는 동안, 개발자는 종종 작성한 코드에 대한 단위 테스트를 만들고 실행한다.<br>
이렇게 자체 테스팅을 하는 동안, 개발자가 단위 테스팅을 효과적으로 수행하기 위해 채택해야 하는 테스터적 사고방식(mindset)은 무엇인가?
- a. 원활한 의사소통 능력
- b. 코드 커버리지
- c. 코드 결함 평가
- d. 세밀한 것에 집중하는 태도

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.5.2. K2
- a. 오답- 단위 테스팅은 프로그래머가 자신의 코드에 대해 수행하는 것으로 보여진다.
- b. 오답- 코드 커버리지는 단위 테스팅에는 유용하지만 이는 테스터의 사고방식(mindset)은 아니다.
- c. 오답- 프로그래머의 사고 방식에 코드에 무슨 문제가 있는지 고려하는 것이 포함되어 있지만 테스터의 사고 방식은 아니다.
- d. 정답- 세밀한 것에 집중하는 태도는 테스터의 사고 방식으로 프로그래머가 단위 테스팅을 수행할 때 결함을 찾을 수 있도록 도움을 준다.

</div>
</details>

---

C - Q6. 다음 중 아래 테스팅 활동과 추적성이 해당 활동을 어떻게 지원하는지를 가장 잘 연결한 것은?

**테스팅 활동**:
1. 리그레션 테스트 선택
2. 테스트 실행의 완전성 평가
3. 수정되지 않은 결함이 있는 사용자 스토리 식별
4. 각 요구사항에 대한 테스트 수가 제품 리스크 수준과 일치하는지 평가

**추적성이 테스팅 활동을 돕는 방식**:
- A. 테스트 베이시스 항목의 상태를 포함하는 테스트 상태 보고서의 이해도 개선
- B. 테스팅이 감사(audit) 가능하도록 함
- C. 프로세스 품질을 평가하기 위한 정보 제공
- D. 변경에 따른 영향 분석

- a. 1D, 2B, 3C, 4A
- b. 1B, 2D, 3A, 4C
- c. 1D, 2C, 3A, 4B
- d. 1D, 2B, 3A, 4C

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.4.4, K2<br>
추적성은 다음과 같은 활동을 지원한다:
- 변경에 따른 영향을 분석하는 관점에서 리그레션 테스트 선택 (1D)
- 테스팅이 감사 가능하도록 하는 테스팅 실행의 완전성 평가 (2B)
- 테스트 베이시스 항목 상태를 포함하도록 테스트 상태 보고서를 쉽게 이해할 수 있는 오픈 결함 보고서가 있는 사용자 스토리의 식별 (3A)
- 각 요구사항에 대한 테스트의 수가 테스트 프로세스 품질 평가를 위해 정보를 제공하는 제품 리스크 수준과 일치하는지 평가 (4C)

따라서, 1.4.4절 내용에 따라 d.가 정답이다.

</div>
</details>

---

C - Q7. 데이터베이스 구조 제안 관련 논의에 참여한 테스터가 특정한 일반 사용자 검색과 관련된 잠재적인 성능 문제를 발견했으며, 이를 개발팀에 알렸다.<br>
테스팅이 성공에 기여한다는 측면에서 다음 중 이 상황을 가장 잘 설명한 것은?
- a. 초기 단계에 필요한 테스트를 식별했다.
- b. 프로세스가 제대로 수행되는지 확인했다.
- c. 기본적 설계 결함의 리스크를 줄였다.
- d. 테스트되지 않은 기능의 리스크를 줄였다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.2.1, K2
- a. 오답- 필요한 테스트를 초기 단계에 식별할 수 있다는 것은 테스트가 (프로젝트) 성공에 어떻게 기여하는지에 대한 내용이지만, 주어진 문제에서 테스터가 그랬다는 내용은 없다.
- b. 오답- 프로세스가 적절히 수행되었는지 확인하는 것은 품질 보증 활동의 하나이며, 테스팅이 성공에 기여하는 경우는 아니다.
- c. 정답- 기본 설계 결함의 리스크를 줄이는 것은 테스팅이 성공에 기여하는 경우이다. 데이터베이스 구조는 설계와 관련이 있고 성능 문제는 심각한 제품 리스크가 될 수 있다.
- d. 오답- 테스트 불가능한 기능의 리스크를 줄이는 것으로 테스팅이 성공에 기여할 수 있지만, 여기서 이 테스터는 테스트 불가능한 것을 식별했다기 보다 성능 테스트가 실패할 수도 있는 요인을 찾아냈다고 볼 수 있다.

</div>
</details>

---

C - Q8. 다음 중 테스트 프로세스의 일환으로 수행하는 작업의 예는?
- a. 결함 분석
- b. 테스트 데이터 설계
- c. 테스트 항목에 버전 할당
- d. 사용자 스토리 작성

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-1.4.2, K2
- a. 오답- 결함 분석은 테스팅이 아닌 디버깅 활동의 일부이다.
- b. 정답- <span style="color:red">테스트 데이터 생성은 테스트 구현 활동이다.</span>
- c. 오답- 테스터는 결과 보고의 목적으로 테스트 항목의 버전을 파악할 필요가 있지만, 테스트 항목에 버전을 부여하는 것은 형상관리 활동의 일부이다.
- d. 오답- <span style="color:red">사용자 스토리 작성은 테스팅 활동이 아니며 제품 소유자가 수행해야 한다.</span>

</div>
</details>

# ● 자료참고
{: .notice--info .text-center}

[실러버스 본문](http://www.kstqb.org/board_skin/board_view.asp?idx=426&page=1&bbs_code=4&key=0&word=&etc=ISTQB){: .btn .btn--info}
[실러버스 용어](http://www.kstqb.org/board_skin/board_view.asp?idx=342&page=2&bbs_code=4&key=0&word=&etc=ISTQB){: .btn .btn--info}
[샘플문제](http://www.kstqb.org/board_skin/board_view.asp?idx=433&page=2&bbs_code=5&key=0&word=&etc=){: .btn .btn--info}