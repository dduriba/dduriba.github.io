---
title: "[Foundation Level] 제 5장. 테스트 관리"
excerpt: "Foundation Level Chapter.5 Test Management"
categories: ISTQB
tag: [ISTQB, Foundation Level]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# 5.1 테스트 조직 (Test Organization)
{: .notice--warning .text-center}

## 5.1.1 독립적인 테스팅 (Independent Testing)
{: .notice--success}

<span style="color:green">(K2) 독립적 테스트의 장단점을 설명할 수 있다.</span>

테스팅 작업은 특정 테스팅 역할을 부여 받은 사람이나 다른 역할을 하는 사람도 수행할 수 있다 (예: 고객). 저자와 테스터가 가지는 인지편향(1.5 절 참조)의 차이 때문에 <u>일정 수준의 독립성은 테스터가 결함을 더 효과적으로 찾게 해 준다. 그러나 독립성이 친숙함을 대체할 수 없으며 개발자도 자신이 작성한 코드에서 많은 결함을 효율적으로 찾아낼 수 있다.</u>

<span style="background-color:rgb(207,228,207);">테스팅의 독립성 수준은 다음과 같다 (낮은 수준에서 높은 수준까지):</span>
- <span style="background-color:rgb(237,220,195);">독립적인 테스터 없음: 유일하게 개발자가 자신의 코드를 직접 테스트하는 형태</span>
- <span style="background-color:rgb(237,220,195);">개발팀이나 프로젝트팀에 속한 독립적인 개발자나 테스터: 개발자가 동료의 제품을 테스트하는 형태도 포함</span>
- <span style="background-color:rgb(237,220,195);">조직 내 독립적 테스트팀이나 그룹이 프로젝트 관리자나 상위 관리자에게 직접 보고</span>
- <span style="background-color:rgb(237,220,195);">비즈니스 조직 또는 사용자 커뮤니티 소속이거나 사용성, 보안성, 성능, 준수성(regulatory/compliance), 이식성 등 특정 테스트 분야를 전문으로 하는 독립적인 테스터</span>
- <span style="background-color:rgb(237,220,195);">현장(in-house) 또는 현장 외(outsourcing)에서 일하는 조직 외부의 독립적인 테스터</span>

대부분의 프로젝트에서 보통 여러 테스트 레벨을 두고 그 중 일부는 독립적인 테스터가 담당하도록 하는 것이 최적이다. <u>개발자는 자신의 작업 산출물의 품질을 일정 수준으로 유지하기 위해 테스팅(특히 하위 레벨 테스팅)에 참여해야 한다</u>.<br>
<span style="background-color:rgb(232,233,234);">테스팅의 독립성을 어떻게 구현할지는 사용 중인 소프트웨어 개발 수명주기 모델에 따라 다르다. 예를 들어 애자일 개발에서는 테스터가 개발팀의 일부로 속할 수 있다. 애자일 방법론을 사용하는 일부 조직에서는 이런 테스터가 보다 큰 독립 테스트팀의 일부로 간주되기도 한다. 또 이런 조직에서는 제품 책임자가 각 반복주기(iteration) 말미에 인수 테스팅을 수행함으로써 사용자 스토리를 검증할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">테스트 독립성의 잠재적 이점</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">독립적인 테스터는 그들이 가지고 있는 다양한 배경, 기술적인 관점, 성향이 달라 개발자와는 다른 유형의 장애를 찾아낼 수 있다.</span>
- <span style="background-color:rgb(237,220,195);">독립적인 테스터는 <span style="color:red">이해관계자가 시스템 명세를 정의하고 구현하면서 만든 가정(assumptions)에 대해 확인하고 이의를 제기하고 틀렸음을 입증</span>할 수 있다.</span>
- <span style="background-color:rgb(237,220,195);">벤더(vendor)의 독립 테스터는 테스트할 시스템을 고용한 회사의 (정치적) 압박 없이 똑바로 그리고 객관적으로 보고할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">테스트 독립성의 잠재적 단점</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">개발팀과의 고립으로 협업이 어려울 수 있고, 개발팀에게 피드백 전달이 늦어지고, 개발팀과 적대적인 관계가 형성될 수 있다.</span>
- <span style="background-color:rgb(237,220,195);">개발자가 품질에 대한 책임감을 잃을 수 있다.</span>
- <span style="background-color:rgb(237,220,195);">독립적인 테스터가 병목 현상의 장본인으로 비쳐질 수 있다.</span>
- <span style="background-color:rgb(237,220,195);">독립적인 테스터는 중요한 정보(예: 테스트 대상에 대한 정보)를 전달받지 못할 수 있다.</span>

테스트 독립성의 단점은 피하면서 그것이 가져오는 이점을 성공적으로 취하고 있는 조직도 많다.

## 5.1.2 테스트 관리자 및 테스터의 역할 (Tasks of a Test Manager and Tester)
{: .notice--success}

<span style="color:green">(K1) 테스트 관리자와 테스터의 역할을 식별할 수 있다.</span>

이 실러버스에서는 테스트 역할 두 가지 즉, 테스트 관리자와 테스터를 다룬다. 두 역할담당자의 활동과 업무는 프로젝트와 제품의 정황, 담당자의 역량, 조직 상황에 따라 달라진다.<br>
<span style="background-color:rgb(207,228,207);">테스트 관리자의 업무</span>는 <span style="background-color:rgb(237,220,195);">테스트 프로세스에 대한 전반적인 책임과 테스트 활동을 성공적으로 이끄는 것이다.</span> <u>테스트 관리자는 전문 테스트 관리자, 프로젝트 관리자, 개발 관리자, 품질 보증 관리자 역할을 맡을 수 있다. 규모가 큰 프로젝트나 조직인 경우 몇 개 테스트팀이 테스트 관리자, 테스트 코치, 테스트 코디네이터에게 보고하고, 각 팀은 테스트 리더나 리드 테스터(lead tester)가 책임진다</u>.

일반적으로 <span style="background-color:rgb(207,228,207);">테스트 관리자의 역할과 업무</span>는 다음과 같다:
- <span style="background-color:rgb(237,220,195);">조직의 테스트 정책과 테스트 전략을 개발하고 리뷰</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">정황을 고려한 테스트 활동과 테스트 목적과 리스크 이해를 바탕으로 테스트 활동을 계획. 예를 들어, 테스트 접근법 선택, 테스트 추정(테스트 시간, 노력, 비용), 리소스 획득, 테스트 레벨과 테스트 주기 정의, 결함 관리 등이 계획에 포함될 수 있다.</span></span>
- <span style="background-color:rgb(237,220,195);">테스트 계획서 작성과 업데이트</span>
- <span style="background-color:rgb(237,220,195);">프로젝트 관리자, 제품 책임자, 기타 관계자와 테스트 계획 관련 협의</span>
- <span style="background-color:rgb(237,220,195);">통합 계획 등과 같은 다른 프로젝트 활동과 테스팅 관점 공유</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">테스트 분석, 설계, 구현, 실행 활동을 개시하고, 테스트 진행과 결과를 모니터링하며 종료 조건(또는 종료 조건 정의)의 상태를 점검하고 테스트 완료 활동을 촉진</span></span>
- <span style="background-color:rgb(237,220,195);">수집한 정보를 바탕으로 테스트 진행 상황 보고서와 테스트 요약 보고서 작성과 배포</span>
- <span style="background-color:rgb(237,220,195);">테스트 결과와 진행 상황(테스트 진행 상황 보고서나 이미 완료된 다른 테스트 프로젝트의 테스트 요약 보고서에서 문서화된)에 따라 계획을 조정하고 테스트 제어에 필요한 모든 조치를 취함</span>
- <span style="background-color:rgb(237,220,195);">결함 관리 시스템과 테스트웨어에 적합한 형상 관리 체제 구축 지원</span>
- <span style="background-color:rgb(237,220,195);">테스트 진척 상황 측정과 테스팅 및 제품 품질 평가를 위한 적절한 메트릭 도입</span>
- <span style="background-color:rgb(237,220,195);">테스트 프로세스 지원용 도구 선택과 구현 지원. 예를 들자면, 도구 선택 예산(경우에 따라 구입이나 지원 비용까지)에 대한 권고, 파일럿 프로젝트에 시간과 노력 할당, 도구 사용에 대한 지속적인 지원 제공 등</span>
- <span style="background-color:rgb(237,220,195);">테스트 환경 구축에 관한 결정</span>
- <span style="background-color:rgb(237,220,195);">조직에 테스터, 테스트팀, 테스트 활동을 홍보하고 지지를 요청</span>
- <span style="background-color:rgb(237,220,195);">테스터의 역량과 경력 개발 (예: 교육계획, 성과평가, 코칭 등)</span>

<u>테스트 관리자의 역할은 소프트웨어 개발 수명주기의 영향을 받는다. 예를 들어, 애자일 개발에서 애자일팀은 위에서 언급한 일부 역할을 수행한다. 특히, 팀 내에서 매일 이루어지는 테스팅 관련 작업이 그러하며 팀에 속한 테스터가 수행하는 경우가 많다</u>. <u>여러 팀에 걸쳐 있거나 전체 조직 또는 인력 관리와 관련한 일부 직무는 개발팀에 속하지 않은 테스트 관리자가 수행하기도 한다. 이런 테스트 관리자를 테스트 코치라고도 한다</u>.<br>
테스트 프로세스 관리에 대한 추가 정보는 Black 2009 에서 찾을 수 있다.

일반적으로 <span style="background-color:rgb(207,228,207);">테스터의 역할과 업무</span>는 다음과 같다:
- <span style="background-color:rgb(237,220,195);">테스트 계획을 리뷰하고 계획 작성에 참여</span>
- <span style="background-color:rgb(237,220,195);">요구사항, 사용자 스토리와 인수 조건, 명세, 모델(즉, 테스트 베이시스)의 테스트 용이성을 분석, 리뷰, 평가</span>
- <span style="background-color:rgb(237,220,195);">테스트 컨디션을 식별 및 기록하고, 테스트 케이스, 테스트 컨디션, 테스트 베이시스 간의 추적성 설정</span>
- <span style="background-color:rgb(237,220,195);">테스트 환경을 설계, 구축, 검증하고 필요한 경우 시스템 관리자, 네트워크 관리자와 협업</span>
- <span style="background-color:rgb(237,220,195);">테스트 케이스와 테스트 프로시저를 설계 및 구현</span>
- <span style="background-color:rgb(237,220,195);">테스트 데이터를 준비하고 획득</span>
- <span style="background-color:rgb(237,220,195);">상세 테스트 실행 일정 수립</span>
- <span style="background-color:rgb(237,220,195);">테스트를 실행하고 결과를 평가해, 기대 결과와 차이 기록</span>
- <span style="background-color:rgb(237,220,195);">테스트 프로세스에 적합한 도구 사용</span>
- <span style="background-color:rgb(237,220,195);">필요한 경우 테스트 자동화 (개발자나 테스트 자동화 전문가의 도움을 받을 수 있음)</span>
- <span style="background-color:rgb(237,220,195);">수행 효율성, 신뢰성, 사용성, 보안성, 호환성, 이식성과 같은 비기능 품질 특성 평가</span>
- <span style="background-color:rgb(237,220,195);">테스트 산출물 리뷰</span>

테스트 분석, 테스트 설계, 특정 테스트 유형, 테스트 자동화에 관련해 일하는 사람은 각자의 역할에 전문가일 수 있다. 제품과 프로젝트의 리스크나 선택한 소프트웨어 개발 수명주기 모델에 따라 테스트 레벨별로 테스터의 역할이 다를 수 있다. 예를 들어, <u>컴포넌트 테스팅 레벨과 컴포넌트 통합 테스팅 레벨에서는 개발자가 테스터의 역할을 수행</u>한다. <u>인수 테스트 레벨에서는 테스터 역할을 주로 비즈니스 분석가, 해당 분야 전문가나 사용자가 수행</u>한다. <u>시스템 테스트 레벨과 시스템 통합 테스트 레벨에서는 주로 독립적인 테스트팀이 테스터의 역할을 담당</u>한다. <u>운영 인수 테스트 레벨에서는 운영이나 시스템 관리 담당자가 테스터의 역할</u>을 하는 경우가 많다.

# 5.2 테스트 계획과 추정 (Test Planning and Estimation)
{: .notice--warning .text-center}

## 5.2.1 테스트 계획의 목적과 내용 (Purpose and Content of a Test Plan)
{: .notice--success}

<span style="color:green">(K2) 테스트 계획의 목적과 내용을 요약할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">테스트 계획</span>은 <span style="background-color:rgb(237,220,195);">개발 및 유지보수 프로젝트의 테스트 활동에 대한 전반적인 내용을 담고 있다. 계획에 영향을 주는 요소로는 조직의 테스트 정책과 테스트 전략, 사용하는 개발 수명주기 및 방법(2.1 절 참조), 테스팅의 범위, 목적, 리스크, 제약, 심각도, 테스트 용이성, 자원의 가용성 등이 있다.<br>
프로젝트와 테스트 계획 작업을 진행함에 따라 더 많은 정보를 알게 되고 테스트 계획에 더 많은 세부 정보를 추가할 수 있다. 테스트 계획 활동은 제품의 수명주기 전반에 걸쳐 이루어지는 지속적인 활동이다 (제품의 수명주기는 프로젝트 범위를 넘어서 유지보수 단계까지 포함할 수 있다). 테스트 활동의 피드백으로 리스크의 변화를 인지하고 테스트 계획을 수정해야 한다. 계획은 마스터 테스트 계획의 일부로 작성하거나 시스템 테스팅, 인수 테스팅과 같은 테스트 레벨별 또는 사용성 테스팅, 성능 테스팅과 같은 테스트 유형별 테스트 계획으로 나눠서 작성할 수도 있다.</span> 테스트 계획에는 <span style="background-color:rgb(237,220,195);">다음과 같은 활동이 있고 이 중 일부는 테스트 계획서에 기록할 수 있다.</span>
- <span style="background-color:rgb(242,213,214);">테스팅의 범위 정의, 목적, 리스크 결정</span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">전반적인 테스팅 접근법 정의</span></span>
- <span style="background-color:rgb(242,213,214);">테스트 활동을 소프트웨어 수명주기 활동에 통합하고 조정</span>
- <span style="background-color:rgb(242,213,214);">테스트 대상 다양한 테스트 활동에 필요한 인력과 기타자원, 테스트 활동 수행 방법 결정</span>
- <span style="background-color:rgb(242,213,214);">테스트 분석, 설계, 구현, 실행, 평가 활동의 일정 조정. 일정은 특정 날짜(예: 순차적 개발에서)나 반복주기 단위(예: 반복적 개발)로 편성할 수 있다.</span>
- <span style="background-color:rgb(242,213,214);">테스트 모니터링과 제어에 사용할 메트릭 선정</span>
- <span style="background-color:rgb(242,213,214);">테스트 활동 예산 결정</span>
- <span style="background-color:rgb(242,213,214);">테스트 문서의 구조와 상세화 정도 정의 (예를 들어, 템플릿이나 예제 문서를 제공함으로써)</span>

테스트 계획에 들어가는 내용은 다양하며 위에 나열한 외의 내용도 추가할 수 있다. 테스트 계획 구조와 테스트 계획의 예제는 ISO 표준(ISO/IEC/IEEE 29119-3)을 참고하라.

## 5.2.2 테스트 전략과 테스트 접근법 (Test Strategy and Test Approach)
{: .notice--success}

<span style="color:green">(K2) 여러 테스트 전략을 구별할 수 있다.</span>

테스트 전략은 테스트 프로세스의 일반적인 모습을 반영한다. <u>주로 제품이나 조직 수준에서 작성</u>된다. 대표적인 <span style="background-color:rgb(207,228,207);">테스트 전략 유형</span>에는 다음과 같은 것들이 있다:
- **<span style="background-color:rgb(237,220,195);">분석적 (Analytiacl)</span>**: <span style="background-color:rgb(242,213,214);">특정 요소(예: 요구사항이나 리스크)에 대한 분석을 기반으로 한 테스트 전략. 리스크 수준에 따라 테스트를 설계하고 우선순위를 결정하는 <span style="color:red">리스크 기반 테스팅이 분석적 접근법의 예</span>이다.</span>
- **<span style="background-color:rgb(237,220,195);">모델 기반 (Model-Based)</span>**: <span style="background-color:rgb(242,213,214);">이러한 유형의 테스트 전략에서 테스트는 요구되는 제품의 특정 측면에 대한 모델을 기반으로 만들어진다. 특정 측면에는 기능, 비즈니스 프로세스, 내부 구조, 비기능 특성(예: 신뢰성) 등이 있다. <span style="color:red">모델에는 비즈니스 프로세스 모델, 상태 모델, 신뢰성 성장 모델</span> 등이 있다.</span>
- **<span style="background-color:rgb(237,220,195);">방법론적 (Methodical)</span>**: <span style="background-color:rgb(242,213,214);">이 테스트 전략은 <span style="color:red">사전에 정의한 테스트 셋이나 테스트 컨디션을 체계적으로 사용하는 데 의존</span>한다. 예를 들어, 보편적이고 발생 가능성이 높은 장애 분류, 주요 품질 특성 목록, 모바일 애플리케이션이나 웹페이지에 대한 전사 룩앤필(look-and-feel) 표준 등이 있다.</span>
- **<span style="background-color:rgb(237,220,195);">프로세스 준수 ((Process-compliant), 또는 표준 준수(standard-compliant))</span>**: <span style="background-color:rgb(242,213,214);">이 테스트 전략은 외부 규정이나 표준을 기반으로 테스트를 분석, 설계, 구현한다. 예를 들어, 특정 산업 표준에서 제시하는 규정이나 표준, 프로세스의 문서화, 테스트 베이시스의 엄격한 식별과 사용, 조직이 강제하거나 조직에 강요된 모든 프로세스나 표준을 기반으로 한다.</span>
- **<span style="background-color:rgb(237,220,195);">전문가 조언 ((Directive), 또는 자문(consultative))</span>**: <span style="background-color:rgb(242,213,214);">이 테스트 전략은 주로 이해관계자, 비즈니스 도메인 전문가, 기술 전문가 등의 조언, 지도, 지시를 바탕으로 이루어진다. 이 사람들은 외부 테스트팀이나 외부 조직 소속일 수 있다.</span>
- **<span style="background-color:rgb(237,220,195);">리그레션-기피 (Regression-averse)</span>**: <span style="background-color:rgb(242,213,214);">기존 기능에 대한 리그레션 테스트 기피를 목표로 한다. 이 테스트 전략에는 기존 테스트웨어(특히 테스트 케이스와 테스트 데이터)의 재사용, 리그레션 테스트 자동화 확대, 테스트 스위트 표준화가 포함된다.</span>
- **<span style="background-color:rgb(237,220,195);">반응적 (Reactive)</span>**: <span style="background-color:rgb(242,213,214);">지금까지 소개한 사전 계획에 따라 실행하는 테스트 전략과는 달리 테스트 대상 컴포넌트나 시스템에 따라 대응하고 테스트 실행 중 발생하는 이벤트에 따라 반응적으로 수행하는 테스트 접근법이다. 이전 테스트 결과에서 얻은 지식을 바탕으로 테스트를 설계하고 구현하며 즉각 테스트를 실행할 수 있다. <span style="color:red">탐색적 테스팅이 반응적 전략에서 일반적으로 사용하는 기법</span>이다.</span>

<span style="background-color:rgb(232,233,234);"><u>앞서 나열한 테스트 전략의 일부를 조합해 적절한 테스트 전략을 만든다.</u> 예를 들어 분석적 전략인 리스크 기반 테스팅을 반응적 전략인 탐색적 테스팅과 조합할 수 있다; 서로 다른 접근법을 조합해 적용했을 때 각 접근법은 서로를 보완하며 더 효과적으로 테스팅을 수행할 수 있게 한다.</span><br>
테스트 전략은 테스트 프로세스를 종합해 개괄적으로 설명하는 반면, <span style="background-color:rgb(207,228,207);">테스트 접근법</span>은 <span style="background-color:rgb(237,220,195);">특정 프로젝트나 릴리스용으로 테스트 전략을 조정(tailoring)한 것이다. 테스트 접근법은 테스트 기법, 테스트 레벨, 테스트 유형을 선택하는 출발점이고, 시작 조건과 종료 조건(시작 조건과 종료 조건은 준비의 정의와 완료의 정의라고 부르기도 함)을 정의하는 출발점이다. 프로젝트의 복잡도와 목표, 개발하는 제품 유형, 제품 리스크 평가에 관한 결정을 기반으로 테스트 전략을 조정한다. 테스트 접근법은 정황(context)을 기반으로 선택하고 리스크, 안전 사항, 사용 가능한 자원과 역량, 기술, 시스템 특성(예: 맞춤형 개발 vs 상용 소프트웨어), 테스트 목적과 규정 같은 요소를 고려한다.</span>

## 5.2.3 시작 조건과 종료 조건 (준비의 정의와 완료의 정의) Entry Criteria and Exit Criteria (Definition of Ready and Definition of Done)
{: .notice--success}

<span style="color:green">(K2) 시작 조건과 종료 조건에 대한 예제를 들 수 있다.</span>

소프트웨어 품질과 테스팅을 효과적으로 통제하려면 특정 테스트 활동의 시작 시점과 완료 시점에 대한 조건을 정의해 놓는 것이 좋다. 시작 조건(애자일 개발에서는 준비의 정의라고 하는 경우가 많음)은 특정 테스트 활동을 시작하기 위해 정의한 사전 조건이다. <u>시작 조건을 충족하지 못하면 해당 활동을 수행하기 더 어렵고 더 많은 시간을 필요로 하며 더 많은 비용이 들고 리스크에 노출될 가능성이 더 높아진다</u>. 종료 조건(애자일 개발에서는 완료의 정의라고 부르는 경우가 많음)은 특정 테스트 레벨이나 테스트 세트가 끝났음을 선언하기 위해 만족해야 할 조건을 정의한다. 각 테스트 레벨과 테스트 유형의 시작과 종료 조건을 정의해야 하고 이는 테스트 목적에 따라 달라진다.

일반적인 <span style="background-color:rgb(207,228,207);">시작 조건</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">테스트 가능한 요구사항, 사용자 스토리나 모델(예: 모델 기반 테스트 전략을 따르는 경우)의 가용 여부</span>
- <span style="background-color:rgb(237,220,195);">이전 테스트 레벨의 종료 조건을 충족한 테스트 항목의 가용 여부</span>
- <span style="background-color:rgb(237,220,195);">테스트 환경 가용 여부</span>
- <span style="background-color:rgb(237,220,195);">필요한 테스트 도구 가용 여부</span>
- <span style="background-color:rgb(237,220,195);">테스트 데이터와 기타 필요한 자원의 가용 여부</span>

일반적인 <span style="background-color:rgb(207,228,207);">종료 조건</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">계획한 테스트 실행 완료</span>
- <span style="background-color:rgb(237,220,195);">정의한 커버리지 수준 (예: 요구사항, 사용자 스토리, 인수 조건, 리스크, 코드 등의 커버리지)의 도달</span>
- <span style="background-color:rgb(237,220,195);">해결하지 못한 결함 수가 합의된 수보다 적음</span>
- <span style="background-color:rgb(237,220,195);">추정 잔존 결함의 수가 충분히 적음</span>
- <span style="background-color:rgb(237,220,195);">신뢰성, 수행 효율성, 사용성, 보안성, 기타 관련된 품질 특성의 수준이 원하는 수준에 도달</span>

종료 조건을 충족하지 못한 상황에서도 예산 소진, 예정된 시간 경과, 시장 출시 압박 등의 이유로 테스트 활동을 조기에 마감하는 경우도 많다. 추가 테스팅 없이 출시하는 상황이라도 프로젝트 이해관계자와 비즈니스 책임자가 리스크를 검토하고 수용하면 테스트를 종료할 수 있다.

## 5.2.4 테스트 실행 일정 (Test Execution Schedule)
{: .notice--success}

<span style="color:green">(K3) 우선순위, 기술적 및 논리적 의존성 정보를 이용해 테스트 케이스 실행 일정을 수립할 수 있다.</span>

<span style="background-color:rgb(232,233,234);">테스트 케이스와 테스트 프로시저를 작성하고(일부 프로시저는 가능하다면 자동화) 테스트 프로시저와 테스트 케이스를 조합해 테스트 스위트를 생성한 후 테스트 스위트의 순서를 정해 실행 일정을 만들 수 있다. 테스트 실행 일정에서 테스트 스위트를 어떤 순서로 실행할지 정의한다. 테스트 실행 일정을 만들 때는 우선순위, 종속 관계, 확인 테스트, 리그레션 테스트, 가장 효율적인 테스트 실행 순서 등을 고려해야 한다.<br>
이상적인 <span style="color:red">테스트 케이스 실행 순서는 가장 우선순위가 높은 테스트 케이스를 먼저 실행</span>하는 것이다. 그러나 실제로 테스트 케이스 간에 종속 관계가 있거나 테스팅 대상의 기능 자체가 종속 관계라면 우선순위에 따라 실행하지 못할 수도 있다. <span style="color:red">우선순위가 높은 테스트 케이스가 우선순위가 낮은 테스트 케이스에 종속되어 있다면 낮은 우선순위를 가진 테스트 케이스를 먼저 실행</span>해야 한다.<br>
마찬가지로 테스트 케이스가 <span style="color:red">서로 종속 관계를 가지고 있다면 각자의 우선순위와 상관없이 필요에 따라 배치</span>해야 한다. 확인 및 리그레션 테스트 역시 수정에 대한 피드백의 중요도에 따라 우선순위를 정해야 하고 이 경우에도 종속 관계를 적용할 수 있다.<br>
상황에 따라 테스트를 다양한 순서로 배치할 수 있으며 각 순서 배치에 따라 효율성 수준이 다를 수 있다. 이런 경우, 테스트 실행 효율성과 우선순위 준수 간의 절충을 고려한 결정이 필요하다.</span>

## 5.2.5 테스트 노력에 영향을 미치는 요소 (Factors Influencing the Test Effort)
{: .notice--success}

<span style="color:green">(K1) 테스팅과 연관된 노력에 영향을 주는 요소를 식별할 수 있다.</span>

<u>테스트 노력 추정은 테스트 관련 작업에 필요한 노력의 양을 예측하는 활동으로 이는 특정 프로젝트, 릴리스, 반복주기에서 테스팅의 목적을 충족하는 데 필요</u>하다. <span style="background-color:rgb(207,228,207);">테스트 노력에 영향을 주는 요소</span>는 아래와 같이 제품 특성, 개발 프로세스 특성, 관련 인물의 특성, 테스트 결과 등이 있다.

**<span style="background-color:rgb(237,220,195);">제품 특성 (Product characteristics)</span>**
- <span style="background-color:rgb(242,213,214);">제품과 관련된 리스크</span>
- <span style="background-color:rgb(242,213,214);">테스트 베이시스의 품질</span>
- <span style="background-color:rgb(242,213,214);">제품의 크기</span>
- <span style="background-color:rgb(242,213,214);">제품 도메인의 복잡도</span>
- <span style="background-color:rgb(242,213,214);">품질 특성 요구사항 (예: 보안성, 신뢰성)</span>
- <span style="background-color:rgb(242,213,214);">요구되는 테스트 문서의 상세화 정도</span>
- <span style="background-color:rgb(242,213,214);">법적, 규제 준수 요구사항</span>

**<span style="background-color:rgb(237,220,195);">개발 프로세스 특성 (Development process characteristics)</span>**
- <span style="background-color:rgb(242,213,214);">조직의 안정성과 성숙도</span>
- <span style="background-color:rgb(242,213,214);">사용하는 개발 모델</span>
- <span style="background-color:rgb(242,213,214);">테스트 접근법</span>
- <span style="background-color:rgb(242,213,214);">사용하는 도구</span>
- <span style="background-color:rgb(242,213,214);">테스트 프로세스</span>
- <span style="background-color:rgb(242,213,214);">시간적 압박</span>

**<span style="background-color:rgb(237,220,195);">인력 특성 (People characteristics)</span>**
- <span style="background-color:rgb(242,213,214);">관련된 인원의 역량과 경험, 특히 유사한 프로젝트나 제품 관련 (예: 도메인 지식)</span>
- <span style="background-color:rgb(242,213,214);">팀 응집력과 리더십</span>

**<span style="background-color:rgb(237,220,195);">테스트 결과 (Test results)</span>**
- <span style="background-color:rgb(242,213,214);">발견한 결함 수와 심각도</span>
- <span style="background-color:rgb(242,213,214);">필요한 재작업 규모</span>

## 5.2.6 테스트 추정 기법 (Test Estimation Techniques)
{: .notice--success}

<span style="color:green">(K2) 메트릭 기반 추정 기법과 전문가 기반 추정 기법의 차이를 설명할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">충분한 테스팅을 하는 데 필요한 노력을 추정하는 예측 기법</span> 몇 가지가 있다. 가장 많이 사용하는 두 가지 기법은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">메트릭 기반 기법</span>: <span style="background-color:rgb(242,213,214);">기존 유사한 프로젝트에서 얻은 메트릭에 기반하거나 보편적인 값을 바탕으로 테스트 노력 예측</span>
- <span style="background-color:rgb(237,220,195);">전문가 기반 기법</span>: <span style="background-color:rgb(242,213,214);">테스팅 작업의 책임자나 전문가의 경험을 기반으로 테스트 노력 예측</span>

예를 들어, <span style="background-color:rgb(207,228,207);">애자일 개발</span>의 <span style="background-color:rgb(237,220,195);">번다운 차트(Burndown charts)를 메트릭 기반 접근법</span>의 예로 볼 수 있는데, 이는 <span style="background-color:rgb(242,213,214);">남아있는 노력을 파악하고 보고함으로써 팀이 다음 반복주기에서 할 수 있는 작업의 양을 산정하는 데 사용할 팀의 업무진행 속도를 계산할 수 있게 해주기 때문</span>이다. 반면 <span style="background-color:rgb(237,220,195);">플래닝 포커(Planning poker)는 전문가 기반 접근법</span>의 예로, <span style="background-color:rgb(242,213,214);">팀원이 자신의 경험을 기반으로 특정 기능을 인도하는 데 드는 노력을 추정</span>한다 (ISTQB-CTFL- AT).<br>
<span style="background-color:rgb(207,228,207);">순차적 개발 프로젝트</span>에서의 <span style="background-color:rgb(237,220,195);">메트릭 기반 접근법의 예로는 결함 제거 모델(Defect Removal Models)</span>을 들 수 있다. <span style="background-color:rgb(242,213,214);">결함의 양과 결함을 제거하는 데 드는 시간을 파악하고 보고해서 차후 비슷한 성격의 프로젝트를 추정하는 기준으로 사용</span>한다. <span style="background-color:rgb(237,220,195);">와이드밴드 델파이(Wideband Delphi) 추정 기법은 전문가 기반 접근법</span>의 예로, <span style="background-color:rgb(242,213,214);">전문가 집단의 경험을 기반으로 추정치를 제공</span>한다 (ISTQB-CTAL-TM).

# 5.3 테스트 모니터링과 제어 (Test Monitoring and Control)
{: .notice--warning .text-center}

<span style="background-color:rgb(207,228,207);">테스트 모니터링</span>의 <span style="background-color:rgb(237,220,195);">목적</span>은 <span style="background-color:rgb(242,213,214);">정보 수집 및 테스트 활동에 대한 피드백과 가시성 제공</span>이다. <span style="background-color:rgb(237,220,195);">모니터링 대상 정보</span>는 <span style="background-color:rgb(242,213,214);">수동 혹은 자동으로 수집할 수 있고, 테스트 진행 상황을 평가하는 데 활용한다. 그리고 테스트 종료 조건(예: 제품 리스크 커버리지, 요구사항 커버리지, 인수 기준)을 만족하는지 또는 애자일 프로젝트에서 완료의 정의와 관련된 테스팅 작업을 만족하는지 측정하는 데 이용</span>한다.

<span style="background-color:rgb(207,228,207);">테스트 제어</span>는 <span style="background-color:rgb(237,220,195);">수집하고 보고된 정보와 메트릭의 결과로 취해진 수정 조치나 가이드를 의미한다. 수정 조치(활동)는 어떤 테스트 활동을 커버하거나 소프트웨어 수명주기 활동에 영향을 미칠 수 있다.</span><br>
<span style="background-color:rgb(237,220,195);">테스트 제어 활동의 예</span>는 다음과 같다:
- <span style="background-color:rgb(242,213,214);"><span style="color:red">식별한 리스크(예: 소프트웨어 인도 지연) 발생 시 테스트 우선순위의 변경</span></span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">테스트 환경이나 기타 자원의 가용 여부에 따라 테스트 일정 변경</span></span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">재작업으로 인해 테스트 항목이 시작 조건이나 종료 조건 만족하는지 재평가</span></span>

## 5.3.1 테스팅에 사용하는 메트릭 (Metrics Used in Testing)
{: .notice--success}

<span style="color:green">(K1) 테스팅에 사용하는 메트릭을 상기할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">테스팅 활동 중이나 종료 시점에 아래와 같은 사항을 평가하기 위해 메트릭을 수집</span>할 수 있다:
- <span style="background-color:rgb(237,220,195);">계획한 일정과 예산 대비 진행 상황</span>
- <span style="background-color:rgb(237,220,195);">테스트 대상의 현재 품질</span>
- <span style="background-color:rgb(237,220,195);">테스트 접근법의 타당성</span>
- <span style="background-color:rgb(237,220,195);">목적 대비 테스트 활동의 효과</span>

일반적인 <span style="background-color:rgb(207,228,207);">테스트 메트릭</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">계획 대비 테스트 케이스 준비 작업 완료율 (또는 계획 대비 테스트 케이스 작성률)</span>
- <span style="background-color:rgb(237,220,195);">계획 대비 테스트 환경 준비 작업 완료율</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">테스트 케이스 실행률 (예: 수행한/수행하지 않은 테스트 케이스 수, 테스트 케이스 합격/불합격 수, 테스트 컨디션 합격/불합격 수)</span></span>
- <span style="background-color:rgb(237,220,195);">결함 정보 (예: 결함 밀도, 발견한 결함, 수정한 결함, 실패율, 확인 테스트 결과)</span>
- <span style="background-color:rgb(237,220,195);">요구사항 커버리지, 사용자 스토리 커버리지, 인수 기준 커버리지, 리스크 커버리지, 코드 커버리지</span>
- <span style="background-color:rgb(237,220,195);">작업 완료, 자원 할당과 사용, 노력</span>
- <span style="background-color:rgb(237,220,195);">다음 결함을 발견하면 얻는 이익 대비 비용이나 테스트를 계속 실행해 얻게 되는 이익 대비 비용 등을 포함하는 테스팅 비용</span>

## 5.3.2 테스트 보고의 목적, 내용, 독자 (Purposes, Contents, and Audiences for Test Reports)
{: .notice--success}

<span style="color:green">(K2) 테스트 보고서의 목적, 내용, 독자를 요약할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">테스트 보고의 목적</span>은 <span style="background-color:rgb(237,220,195);">테스트 활동(예: 테스트 레벨) 중이나 마무리 시점의 테스트 활동 정보 요약과 공유</span>이다. <span style="background-color:rgb(207,228,207);">테스트 활동 중 작성하는 테스트 보고서</span>는 <span style="background-color:rgb(237,220,195);">테스트 진행 상황 보고서</span>, <span style="background-color:rgb(207,228,207);">테스트 활동 종료 시점에 작성하는 테스트 보고서</span>는 <span style="background-color:rgb(237,220,195);">테스트 요약 보고서</span>라고 부르기도 한다.<br>
<u>테스트 관리자는 테스트 모니터링과 제어 과정 중에 이해관계자에게 정기적으로 테스트 진행 상황을 보고</u>한다. 테스트 진행 상황 보고서와 테스트 요약 보고서에 공통으로 들어가는 보고 내용 외에, 일반적인 <span style="background-color:rgb(207,228,207);">테스트 진행 상황 보고서</span>에 들어가는 정보는 아래와 같다:
- <span style="background-color:rgb(237,220,195);"><span style="color:red">테스트 계획 대비 테스트 활동과 진행 상황</span></span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">진행을 방해하는 요소</span></span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">다음 보고 기간에 진행하기로 계획한 테스팅</span></span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">테스트 대상의 품질</span></span>

<u>종료 조건을 만족하면 테스트 관리자는 테스트 요약 보고서를 작성한다. 이 보고서에는 최근 테스트 진행 상황과 기타 관련 정보에 근거해 테스팅 수행 요약 정보를 기록</u>한다.<br>
일반적인 <span style="background-color:rgb(207,228,207);">테스트 요약 보고서</span>는 다음과 같은 내용을 포함한다:
- <span style="background-color:rgb(237,220,195);">테스팅 수행 내용 요약</span>
- <span style="background-color:rgb(237,220,195);">테스트 기간 도중에 발생한 상황 정보</span>
- <span style="background-color:rgb(237,220,195);">계획 대비 편차 (예: 일정, 기간, 테스팅 활동 노력)</span>
- <span style="background-color:rgb(237,220,195);">종료 조건 및 완료의 정의에 대한 테스팅 현황과 제품 품질</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">진행을 방해했거나 계속해서 방해하고 있는 요소</span></span>
- <span style="background-color:rgb(237,220,195);">메트릭 (5.3.1 에서 설명한 결함, 테스트 케이스, 테스트 커버리지, 활동 진행 상황, 소비한 자원)</span>
- <span style="background-color:rgb(237,220,195);">잔존 리스크 (5.5 절 참조)</span>
- <span style="background-color:rgb(237,220,195);">재사용 가능한(만들어 낸) 테스트 작업 산출물</span>

테스트 보고서의 내용은 프로젝트, 조직 요구사항, 소프트웨어 개발 수명주기에 따라 달라진다. 예를 들어 이해관계자나 규제가 많은 복잡한 프로젝트는 간단한 소프트웨어 업데이트 프로젝트보다 훨씬 상세하고 철저한 보고가 필요하다. 또 다른 예로, 애자일 개발에서 테스트 진행 상황 보고를 작업 보드, 결함 요약, 번다운 차트에 통합할 수 있고 일일 스탠드업(stand-up) 회의에서 공유할 수 있다 (ISTQB-CTFL-AT 참조).<br>
<span style="background-color:rgb(207,228,207);">테스트 보고서는 프로젝트의 정황뿐 아니라 보고의 대상자에 따라서도 조정해야 한다. 기술적인 배경이 있거나 테스트팀을 대상으로 하는 보고서의 형식이나 내용은 경영층을 대상으로 하는 요약 보고서와 달라야 한다.</span> <span style="background-color:rgb(207,228,207);">전자</span>에서는 <span style="background-color:rgb(237,220,195);">결함 유형과 추세에 대한 상세한 정보가 중요</span>하고, <span style="background-color:rgb(207,228,207);">후자</span>에서는 <span style="background-color:rgb(237,220,195);">상위 수준으로 작성된 보고서(예: 우선순위별 결함 상태 요약, 예산, 일정, 테스트 컨디션별 합격/불합격/미실행 정보)가 더 적절</span>할 수 있다.<br>
ISO 표준(ISO/IEC/IEEE 29119-3)은 테스트 진행 상황 보고서와 테스트 완료 보고서(본 실러버스는 테스트 요약 보고서라고 함), 두가지 형식의 보고서 내용 구성과 예제를 제공하고 있다.

# 5.4 형상 관리 (Configuration Management)
{: .notice--warning .text-center}

<span style="color:green">(K2) 형상 관리가 테스팅을 어떻게 지원하는지 요약할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">형상 관리의 목적</span>은 <span style="background-color:rgb(237,220,195);"><span style="color:red">프로젝트와 제품 수명주기 동안 컴포넌트나 시스템, 테스트웨어와 이들 서로간의 관계 통합을 수립하고 유지</span></span>하는 데 있다.<br>
<span style="background-color:rgb(207,228,207);">형상 관리는 테스팅을 적절히 지원하고자 아래 내용을 확인</span>한다:
- <span style="background-color:rgb(237,220,195);">모든 테스트 항목에 <span style="color:red">고유 식별번호를 부여</span>하고, 버전을 관리하고, 변경 이력을 기록한다. 형상 관리에서 테스트 항목은 서로 연관돼 있다.</span>
- <span style="background-color:rgb(237,220,195);">모든 테스트웨어 항목에 고유 식별번호를 부여하고, 버전을 관리하고, 변경사항을 추적하고, 서로 연결해 테스트 항목 버전과도 연결되도록 해서 테스트 프로세스 전반에 걸쳐 <span style="color:red">추적성을 유지</span>할 수 있게 한다.</span>
- <span style="background-color:rgb(237,220,195);">식별한 모든 문서와 소프트웨어 아이템은 테스트 문서 내에서 명확하게 <span style="color:red">상호 참조되도록</span> 한다.</span>

<span style="color:red">테스트 계획을 수립하면서 형상관리 절차와 인프라(도구)를 식별하고 구현</span>해야 한다.

# 5.5 리스크와 테스팅 (Risks and Testing)
{: .notice--warning .text-center}

## 5.5.1 리스크의 정의 (Definition of Risk)
{: .notice--success}

<span style="color:green">(K1) 장애 발생 가능성과 영향도를 이용해 리스크 수준을 정의할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">리스크</span>란 <span style="background-color:rgb(237,220,195);"><span style="color:blue">미래에 부정적 결과를 가져오는 이벤트의 발생 가능성</span></span>이다. <span style="background-color:rgb(207,228,207);">리스크 수준</span>은 <span style="background-color:rgb(237,220,195);"><span style="color:red">이벤트 발생 가능성</span>과 <span style="color:red">이벤트로 인한 영향도(피해)</span>로 결정</span>한다.

## 5.5.2 제품 및 프로젝트 리스크 (Product and Project Risks)
{: .notice--success}

<span style="color:green">(K2) 프로젝트 리스크와 제품 리스크를 구별할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">제품 리스크</span>는 <span style="background-color:rgb(237,220,195);">작업 산출물(예: 명세, 컴포넌트, 시스템, 테스트 등)이 사용자나 이해관계자의 합당한 니즈를 충족하지 못할 가능성이다. <span style="color:red">제품 리스크가 제품의 특정 품질 특성(예: 기능 안전성, 신뢰성, 성능 효율성, 사용성, 보안성, 호환성, 유지 보수성, 이식성)과 연관되는 경우 품질 리스크</span>라고 한다.</span><br>
<span style="background-color:rgb(207,228,207);">제품 리스크의 예</span>는 다음과 같다:
- <span style="background-color:rgb(237,220,195);">소프트웨어가 명세에서 의도한 기능을 수행하지 못함</span>
- <span style="background-color:rgb(237,220,195);">소프트웨어가 사용자, 고객이나 이해관계자가 요구하는 기능을 수행하지 못함</span>
- <span style="background-color:rgb(237,220,195);">시스템 아키텍처가 일부 비기능 요구사항을 충분히 지원하지 못함</span>
- <span style="background-color:rgb(237,220,195);">특정 계산식이 특정 상황에서 올바르게 수행되지 못함</span>
- <span style="background-color:rgb(237,220,195);">루프(loop) 제어 구조 코딩이 잘못됨</span>
- <span style="background-color:rgb(237,220,195);">고성능 거래 처리 시스템의 응답 시간이 적절하지 않음</span>
- <span style="background-color:rgb(237,220,195);">사용자 경험(UX, User eXperience) 피드백이 제품 기대치에 미치지 못함</span>

<span style="background-color:rgb(207,228,207);">프로젝트 리스크</span>는 발생하면 프로젝트 목적 달성 능력에 부정적인 영향을 줄 수 있는 상황이다.<br>
<span style="background-color:rgb(207,228,207);">프로젝트 리스크의 예</span>는 다음과 같다:
- <span style="background-color:rgb(237,220,195);">프로젝트 이슈:</span>
  + <span style="background-color:rgb(242,213,214);">배포, 작업 완료, 종료 조건이나 완료의 정의를 만족하지 못하고 지연된다.</span>
  + <span style="background-color:rgb(242,213,214);">부정확한 추정, 우선순위가 높은 프로젝트에 예산 재배정, 또는 조직 전반에 걸친 예산 삭감으로 예산이 부족할 수 있다.</span>
  + <span style="background-color:rgb(242,213,214);">프로젝트 후반에 발생하는 변경은 상당한 재작업을 불러올 수 있다.</span>
- <span style="background-color:rgb(237,220,195);">조직 이슈:</span>
  + <span style="background-color:rgb(242,213,214);">역량, 교육, 인력이 부족할 수 있다.</span>
  + <span style="background-color:rgb(242,213,214);">개인적인 문제로 갈등이나 문제가 생길 수 있다.</span>
  + <span style="background-color:rgb(242,213,214);">사용자, 비즈니스 인력, 해당 분야 전문가들이 비즈니스 우선순위 마찰로 참여하지 못할 수 있다.</span>
- <span style="background-color:rgb(237,220,195);">정치적 이슈:</span>
  + <span style="background-color:rgb(242,213,214);">테스터가 필요한 사항이나 테스트 결과를 제대로 전달하지 못할 수 있다.</span>
  + <span style="background-color:rgb(242,213,214);">개발자나 테스터가 테스팅과 리뷰 도중 발견한 사항에 대한 후속 조치를 못할 수 있다 (예를 들어, 개발 및 테스팅 프랙티스를 개선하지 못함).</span>
  + <span style="background-color:rgb(242,213,214);">테스팅에 대한 잘못된 태도나 기대가 있을 수 있다 (예를 들어, 테스팅 도중 발견한 결함의 가치를 알아보지 못함).</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:blue">기술적 이슈</span>:</span>
  + <span style="background-color:rgb(242,213,214);">요구사항이 충분히 잘 정의되지 않을 수 있다.</span>
  + <span style="background-color:rgb(242,213,214);">기존 제약 사항으로 요구사항을 만족하지 못할 수 있다.</span>
  + <span style="background-color:rgb(242,213,214);">테스트 환경이 필요한 시점에 준비되지 않을 수 있다.</span>
  + <span style="background-color:rgb(242,213,214);">데이터 변환, 마이그레이션 계획 및 도구 지원이 필요한 시점에 제공되지 않을 수 있다.</span>
  + <span style="background-color:rgb(242,213,214);">개발 프로세스의 약점은 프로젝트 작업 산출물 (예: 설계, 코드, 형상, 테스트 데이터, 테스트 케이스)의 품질이나 일관성에 영향을 줄 수 있다.</span>
  + <span style="background-color:rgb(242,213,214);">결함 관리가 부실하고 기타 유사한 문제 때문에 축적된 결함이나 기타 기술적 부채를 가져올 수 있다.</span>
- <span style="background-color:rgb(237,220,195);">공급자 이슈:</span>
  + <span style="background-color:rgb(242,213,214);">외부 공급자가 필요한 제품이나 서비스를 공급하지 못하거나 파산할 수 있다.</span>
  + <span style="background-color:rgb(242,213,214);">계약 관련 이슈로 프로젝트에 문제가 생길 수 있다.</span>

프로젝트 리스크는 개발 활동과 테스트 활동 양쪽 모두에 영향을 미칠 수 있다. 프로젝트 관리자가 모든 프로젝트 리스크에 대한 책임을 지는 것이 일반적이지만, 테스트와 관련된 프로젝트 리스크는 테스트 관리자가 책임을 지는 경우도 있다.

## 5.5.3 리스크 기반 테스팅과 제품 품질 (Risk-based Testing and Product Quality)
{: .notice--success}

<span style="color:green">(K2) 제품 리스크 분석이 테스팅의 범위와 테스팅의 충분함에 어떻게 영향을 미치는지 예를 들어 설명할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">리스크</span>는 <span style="background-color:rgb(237,220,195);">테스팅 노력을 집중하는 데 사용된다. 리스크는 테스팅을 언제, 어디서 시작할지 결정하고 좀 더 관심을 가져야 할 영역을 식별하는 데 사용</span>된다. <span style="background-color:rgb(207,228,207);">테스팅</span>은 <span style="background-color:rgb(237,220,195);">부정적인 이벤트의 발생 가능성을 줄이거나 부정적인 이벤트의 영향을 줄이기 위해 사용한다. 리스크 완화 활동으로써 테스팅은 식별한 리스크뿐 아니라 잔존(해결하지 못한) 리스크에 대한 정보도 제공</span>한다.<br>
<span style="background-color:rgb(207,228,207);">리스크 기반 접근법</span>은 <span style="background-color:rgb(237,220,195);">제품 리스크 수준을 조기에 낮추는 데 기여</span>한다. <span style="background-color:rgb(207,228,207);">리스크 기반 테스팅</span>은 <span style="background-color:rgb(237,220,195);"><span style="color:red">제품 리스크 식별과 리스크 발생 가능성과 영향을 평가하는 제품 리스크 분석을 포함한다. 제품 리스크 정보로 얻은 결과는 테스트 계획, 명세, 테스트 케이스 준비와 실행, 테스트 모니터링에 사용</span>한다. 초기에 제품 리스크를 평가하면 프로젝트 성공에 기여</span>한다.<br>
<span style="background-color:rgb(207,228,207);">리스크 기반 접근법에서 <span style="color:blue">제품 리스크 분석 결과는 다음에 사용</span></span>된다:
- <span style="background-color:rgb(237,220,195);">사용할 테스트 기법 결정</span>
- <span style="background-color:rgb(237,220,195);">수행할 테스트 레벨과 유형 확정 (예: 보안성 테스팅, 가용성 테스팅)</span>
- <span style="background-color:rgb(237,220,195);">테스트 수행 범위 결정</span>
- <span style="background-color:rgb(237,220,195);">가능한 조기에 심각한 결함을 발견하기 위해 테스트 우선순위 결정</span>
- <span style="background-color:rgb(237,220,195);">기존 테스팅 활동 외 리스크 완화를 위한 다른 활동의 식별 (예: 경험이 부족한 설계자에게 교육 제공)</span>

<span style="background-color:rgb(207,228,207);">리스크 기반 테스팅은 프로젝트 이해관계자의 집단 지식과 통찰력을 기반으로 제품 리스크를 분석한다. 제품 장애 발생 가능성을 최소화하기 위해 <span style="color:blue">리스크 관리 활동은 다음과 같은 절차</span></span>를 따르게 된다:
- <span style="background-color:rgb(237,220,195);">잘못될 수 있는 것(리스크)을 분석 (그리고 정기적으로 재분석)</span>
- <span style="background-color:rgb(237,220,195);">처리해야 할 중요한 리스크가 무엇인지 판단</span>
- <span style="background-color:rgb(237,220,195);">해당 리스크를 완화하기 위한 행동 구현</span>
- <span style="background-color:rgb(237,220,195);">리스크의 실제 발생을 대비한 대책 수립</span>

또 <u>테스팅은 새로운 리스크를 식별하고 어떤 리스크를 완화해야 하는지 판단하는 데 도움을 주며 리스크에 대한 불확실성을 낮춰준다</u>.

# 5.6 결함 관리 (Defect Management)
{: .notice--warning .text-center}

<span style="color:green">(K3) 테스팅하면서 식별한 결함을 결함 보고서로 작성할 수 있다.</span>

<span style="background-color:rgb(232,233,234);">테스팅의 목적 중 하나가 결함을 찾는 것이기 때문에 테스팅 중 발견한 결함은 반드시 기록해야 한다. 결함을 기록하는 방법은 테스트 대상 컴포넌트나 시스템의 정황, 테스트 레벨, 소프트웨어 개발 수명주기 모델에 따라 달라진다. 찾아낸 모든 결함은 조사하고, 발견에서 결함 분류까지 추적해야 한다 (예: 결함 수정과 결함 해결에 대한 확인 테스팅 완료 여부, 다음 릴리스로 연기, 영구적인 제품 제약 사항으로 인정 등). 모든 결함을 해결까지 관리하기 위해 조직은 결함 관리 프로세스(워크플로우와 결함 분류 규칙)를 수립해야 한다. 아키텍처, 설계자, 개발자, 테스터, 제품 책임자 등 결함 관리에 참여하는 모든 사람이 프로세스에 동의해야 한다. 일부 조직에서는 결함 로깅(logging)과 추적이 매우 비공식적일 수 있다.<br>
결함 관리 프로세스를 수행하다 보면 일부 보고는 결함에 의한 실제 장애가 아닌 거짓양성으로 보고되기도 한다. 예를 들어 네트워크 연결이 끊기거나 시간 초과(time out)로 테스트 결과는 불합격이 될 수 있다. 이런 결과는 테스트 대상의 결함 때문이 아니라 이상 현상(anomaly) 때문일 수 있어 조사가 필요하다. 테스터는 결함으로 보고하는 거짓양성의 수를 최소화해야 한다.<br>
결함은 코드 작성 중, 정적 분석, 리뷰, 동적 테스팅 또는 소프트웨어 제품을 사용하는 중에 보고할 수 있다. 결함은 코드나 운영 중인 시스템이나 요구사항, 사용자 스토리와 인수 조건, 개발 문서, 테스트 문서, 사용자 매뉴얼, 설치 가이드 같은 문서에서 이슈로 보고할 수 있다. 효율적이고 효과적인 결함 관리 프로세스를 위해 조직은 결함의 속성, 분류, 워크플로우에 대한 표준을 정의해 놓을 수 있다.</span>

<span style="background-color:rgb(207,228,207);">일반적인 결함 보고서의 목적</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);"><span style="color:red">발생한 모든 부정적인 이벤트 정보를 개발자와 기타 관계자에게 제공해 구체적인 영향을 식별하고, 재현 테스트로 문제를 격리하고, 잠재 결함을 수정하고, 필요에 따라서는 문제를 해결할 다른 방법을 찾을 수 있도록 한다.</span></span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">테스트 관리자에게 작업 산출물의 품질과 테스팅 영향을 추적할 방법을 제공한다 (예: 많은 결함을 보고하면 테스터는 테스트를 수행하는 데 시간을 쓰는 대신에 결함 보고에 많은 시간을 할애하게 되고 필요한 확인 테스팅의 양도 많아진다).</span></span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">개발과 테스트 프로세스 개선에 대한 아이디어를 제공한다.</span></span>

<span style="background-color:rgb(207,228,207);">동적 테스팅에서 작성하는 결함 보고서의 내용</span>은 일반적으로 다음과 같다:
- <span style="background-color:rgb(237,220,195);">식별 번호</span>
- <span style="background-color:rgb(237,220,195);">제목, 보고하는 결함에 대한 짧은 요약</span>
- <span style="background-color:rgb(237,220,195);">결함 보고 날짜, 보고 주체 조직 및 작성자</span>
- <span style="background-color:rgb(237,220,195);">테스트 항목 식별자(테스트 대상 형상 항목)와 환경</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">결함을 발견한 개발 수명주기 단계</span></span>
- <span style="background-color:rgb(237,220,195);">로그, 데이터베이스 덤프, 스크린샷, 녹화 기록(테스트 실행 중 녹화했다면) 등의 결함 재현과 해결을 위한 설명</span>
- <span style="background-color:rgb(237,220,195);">기대 및 실제 결과</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">이해관계자의 관점에서의 결함 영향도(심각도)의 범위와 정도</span></span>
- <span style="background-color:rgb(237,220,195);">수정 우선순위 (긴급하게 처리해야 하는 순서)</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">결함 보고서의 상태 (예: 신규, 연기, 중복, 수정 대기, 확인 테스팅 대기, 재오픈, 완료)</span></span>
- <span style="background-color:rgb(237,220,195);">결론, 의견, 승인 여부</span>
- <span style="background-color:rgb(237,220,195);">글로벌 이슈 (예를 들어, 결함 수정의 결과로 영향을 받는 다른 영역)</span>
- <span style="background-color:rgb(237,220,195);">변경 이력 (예를 들어, 프로젝트 팀원이 결함을 격리하고 복구하고, 수정 여부를 확인하는 데 취한 조치 순서)</span>
- <span style="background-color:rgb(237,220,195);">참조 (문제를 발견하게 해 준 테스트 케이스 포함)</span>

결함 관리 도구를 사용하면 위 정보 중 일부는 자동으로 작성될 수 있다 (예: 고유 식별번호 자동 부여, 결함 상태 자동 할당, 결함 보고 상태 자동 업데이트). 정적 테스팅, 특히 리뷰에서 발견하는 결함은 다양한 방법(예: 리뷰 회의록)으로 문서화한다.<br>
<u>결함 보고서의 내용 관련 예제는 ISO 표준(ISO/IEC/IEEE 29119-3)을 참조한다. 해당 표준은 <span style="color:blue">결함 보고서를 인시던트 보고서</span></u>로 부른다.

# ● 용어
{: .notice .text-center}

<details>
<summary>Keywords</summary>
<div markdown="1">

- 형상 관리(configuration management):<br>
참조 : ISO 24765<br>
형상 항목의 기능적/물리적 특성을 식별/문서화하고, 해당 특성을 제어하며, 변경 처리 및 구현 상황을 기록/보고하고, 명시된 요구사항을 준수하는지 검증하기 위해 기술적, 행정적 지시와 감독을 적용하는 원칙

- 결함 관리(defect management):<br>
연관 항목 : 인시던트 관리(incident management)<br>
결함을 인식하고 기록하며, 분류, 조사, 해결하기 위해 조치를 취하고, 해결되었을 때 이를 처분하는 프로세스

- 결함 리포트(defect report)

- 시작 조건(entry criteria):<br>
참조 : Gilb and Graham<br>
유의어 : 준비의 정의(definition of ready)<br>
정의된 과업을 공식적으로 시작하기 위한 조건의 집합

- 종료 조건(exit criteria)

- 제품 리스크(product risk):<br>
연관 항목 : 리스크(risk)<br>
제품의 <span style="color:red">품질</span>에 영향을 미치는 리스크

- 프로젝트 리스크(project risk):<br>
연관 항목 : 리스크(risk)<br>
프로젝트 성공에 영향을 미치는 리스크

- 리스크(risk): 미래에 부정적인 결과를 초래할 수 있는 요소

- 리스크 수준(risk level):<br>
유의어 : 리스크 노출도(risk exposure)<br>
영향 및 가능성에 의해 정의된 리스크의 질적, 양적 측정치<br>

- 리스크 기반 테스팅(risk-based testing):<br>
참조 : ISO 29119<br>
연관된 리스크 유형과 리스크 수준을 기반으로 테스트 활동 및 리소스의 이용, 관리, 선택, 우선순위 등을 다루는 테스팅

- 테스트 접근법(test approach): 특정 프로젝트에 대한 테스트 전략을 구현한 것

- 테스트 관리자(test manager): 테스팅 활동 및 자원의 프로젝트 관리와 테스트 대상에 대한 평가를 책임지고 있는 담당자 테스트 대상에 대한 평가를 감독 및 통제, 관리, 계획, 규제하는 사람

- 테스트 계획서(test plan):<br>
참조 : ISO 29119<br>
테스팅 활동 조정에 사용되며, 달성할 테스트 목표와 그것을 달성하기 위한 방법과 일정을 설명하는 문서

- 테스트 진행 보고서(test progress report):<br>
유의어 : 테스트 상태 보고서(test status report)<br>
정기적으로 베이스라인(baseline), 리스크, 대안이 필요한 결정 사항과 관련된 테스트 활동의 진행 상황을 작성하는 테스트 보고서

- 테스트 전략(test strategy):<br>
참조 : ISO 29119<br>
유의어 : 조직 테스트 전략(organizational test strategy)<br>
조직 내에서 수행하는 하나 이상의 프로젝트를 테스트하기 위해 포괄적인 요구사항을 나열한 문서. 테스팅을 어떤 방식으로 수행해야 하고, 또 그것이 어떻게 테스트 정책과 연계되는지에 대한 정보를 제공

- 테스트 요약 보고서(test summary report):<br>
참조 : ISO 29119<br>
유의어 : 테스트 보고서(test report)<br>
해당하는 테스트 항목 평가를 완료 조건에 대비해 제공하는 테스트 보고서

- 테스터(tester): 컴포넌트나 시스템의 테스팅에 참여하는 숙련된 전문가

- 가용성(availability):<br>
참조 : ISO 25010<br>
제품을 사용하고자 할 때 컴포넌트나 시스템의 운용 가능하고 접근 가능한 정도

- 플래닝 포커(planning poker):<br>
연관 항목 : 애자일 소프트웨어 개발(Agile software development), 광대역 델파이(Wideband Delphi)<br>
주로 애자일 소프트웨어 개발에서 사용자 스토리에 필요한 노력이나 상대적 크기를 추정하고자 사용하는 합의 기반 추정 기법. 와이드밴드 델파이 기법 중 하나이며, 카드 한 벌을 이용하며 각 카드에는 팀에서 추정하는 단위 값이 표기됨

- 와이드밴드 델파이(Wideband Delphi): 팀원의 집단 지성을 이용하여 정확한 추정을 목표로 수행하는 전문가 기반 테스트 추정 기법

- 테스트 세션(test session):<br> 
연관 항목 : 탐색적 테스팅(exploratory testing)<br>
방해받지 않는 테스트 실행 시간. 탐색적 테스팅에서 각 테스트 세션은 차터(charter)를 기반으로 구성되긴 하지만, 테스터가 세션 중 새로운 기회나 이슈를 탐색할 수 있음. 테스터는 필요에 따라 바로바로 설계하고 실행하며 진행 상황을 기록

- 테스트 정책(test policy):<br>
유의어 : 조직 테스트 정책(organizational test policy)<br>
테스팅과 관련된 조직의 원칙과 접근법, 주요 목표를 설명하는 상위 수준의 문서

- 테스트 차터(test charter):<br>
연관 항목 : 탐색적 테스팅(exploratory testing)<br>
유의어 : 차터(charter)<br>
세션 기반 탐색적 테스팅에서의 테스트 활동에 대한 문서

- 상위 수준 테스트 케이스(high-level test case):<br>
연관 항목 : 하위 수준 테스트 케이스(low-level test case)<br>
유의어 : 추상 테스트 케이스(abstract test case), 논리 테스트 케이스(logical test case) 입력 데이터와 기대 결과에 대한 구체적인 값이 명시되지 않는 테스트 케이스

- 하위 수준 테스트 케이스(low-level test case):<br>
연관 항목 : 상위 수준 테스트 케이스(high-level test case)<br>
유의어 : 구체적인 테스트 케이스(concrete test case)<br>
입력 데이터와 기대 결과에 대한 구체적인 값이 주어진 테스트 케이스

- 익스트림 프로그래밍(Extreme Programming(XP)):<br>
연관 항목 : 애자일 소프트웨어 개발(Agile software development)<br>
애자일 소프트웨어 개발에서 짝 프로그래밍, 철저한 코드 리뷰, 모든 코드에 대한 단위 테스팅, 간단하고 명확한 코드 등과 같은 실천법을 핵심으로 삼는 소프트웨어 공학 방법론

</div>
</details>

# ● 샘플문제
{: .notice--danger .text-center}

A - Q30. 다음 중 테스트 관리자와 테스터의 업무 분장을 가장 잘 설명한 것은?
- a. 테스트 관리자는 테스팅 활동을 계획하고 어떤 표준을 따를지 결정한다. 테스터는 사용할 도구와 가이드라인을 선택한다.
- b. 테스트 관리자는 테스팅 활동을 계획, 조정, 제어한다. 테스터는 테스트를 자동화한다.
- c. 테스트 관리자는 테스팅 활동을 계획, 모니터하고 제어한다. 테스터는 테스트를 설계하고 테스트 완료를 결정한다.
- d. 테스트 관리자는 테스팅을 계획, 체계화하고 테스트 케이스를 작성한다. 테스터는 테스트 우선순위를 정하고 실행한다

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.1.2 (K1) 테스트 관리자와 테스터의 역할을 식별할 수 있다.
- a. 오답: 도구 선택은 테스트 관리자의 역할이다.
- b. 정답: 다른 오답들의 해설 참조
- c. 오답: 테스터는 테스트 대상의 릴리스를 결정하지 않는다.
- d. 오답: 테스터가 테스트 케이스를 체계화하고 테스트 관리자가 우선 순위를 정한다.

</div>
</details>

---

A - Q31. 다음 중 테스트 실행 모니터에 가장 유용한 메트릭은?
- a. 실행된 테스트 케이스의 비율
- b. 테스트 실행에 참여한 평균 테스터 수
- c. 소스 코드에 의한 요구사항 커버리지
- d. 이미 작성되고 검토된 테스트 케이스의 비율

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.3.1 (K1) 테스팅에 사용하는 메트릭을 상기할 수 있다.
- a. 정답: 테스트 케이스 실행(예: 실행한/실행하지 않은 테스트 케이스 수, 통과.실패한 테스트 케이스 수)
- b. 오답: 테스트 실행에 참여한 평균 테스터 수는 측정할 수 있지만 가치는 낮다. 테스터 수는 테스트 대상의 품질이나 테스트 진행 상황에 대한 정보를 제공하지 않는다.
- c. 오답: 소스 코드에 의한 요구사항의 커버리지는 테스트 실행 중에 측정되지 않는다. 기껏해야 코드 또는 요구사항의 테스트(!) 커버리지가 측정된다.
- d. 오답: 이미 작성되고 검토된 테스트 케이스의 비율은 테스트 실행이 아닌 테스트 준비와 관련된 메트릭이다.

</div>
</details>

---

A - Q32. 다음 중 테스트 계획에 영향을 주면서 (초기) 테스트 계획의 일부인 것은?
- a. 예산의 제약 (Budget limitations)
- b. 테스트 로그 (Test log)
- c. 장애 발생률 (Failure rate)
- d. 유스케이스 (Use cases)

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.2.1 (K2) 테스트 계획의 목적과 내용을 요약할 수 있다.
- a. 정답: 무엇을 테스트할 것인지에 대한 결정은 테스트 계획에 문서화한다. 이것은 테스트 계획 시 예산의 제약이 있는 경우, 무엇을 테스트하고 무엇을 테스트하지 않을지 우선순위화가 필요하다는 것을 의미한다.
- b. 오답: 테스트 모니터링과 제어 참조
- c. 오답: 일반적인 테스트 메트릭 참조
- d. 오답: 유스케이스는 테스트 분석의 일부이다.

</div>
</details>

---

A - Q33. 다음 중 테스트의 일반적인 완료 조건만 포함된 목록은 무엇인가?
- a. 측정된 신뢰성, 테스트 커버리지, 테스트 비용, 수정하는 결함과 잔존 리스크에 대한 상태와 일정
- b. 측정된 신뢰성, 테스트 커버리지, 테스터의 독립 수준 및 제품 완성도
- c. 측정된 신뢰성, 테스트 커버리지, 테스트 비용, 테스트 환경의 가용성, 출시 일정 및 제품 완성도
- d. 출시 일정, 결함, 테스터 자격, 테스트 가능한 유스케이스의 가용성, 테스트 커버리지 및 테스트 비용

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.2.3 (K2) 시작 조건과 종료 조건에 대한 예제를 들 수 있다.
- a. 정답: 다른 오답의 해설 참조
- b. 오답: 테스터의 독립 수준은 완료 조건으로 사용하지 않는다.
- c. 오답: “테스트 환경”의 가용성은 시작 조건이다.
- d. 오답: “테스터의 자격”은 일반적인 완료 조건이 아니다.

</div>
</details>

---

A - Q34. 다음 중 테스트 요약 보고서에 들어가는 내용이 아닌 것은?
- a. 통과/실패 기준에 대한 정의, 테스팅의 목적
- b. 테스트 접근법과의 차이
- c. 완료 기준 대비 실제 진척률 측정
- d. 테스트 대상의 품질 평가

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.3.2 (K2) 테스트 보고서의 목적, 내용, 독자를 요약할 수 있다.
- a. 정답- 이 정보는 테스트 프로젝트 초기에 정의돼 있어야 한다.
- b. 오답- 이 정보는 테스트 보고서에 들어가는 내용이다: 테스트 기간 동안 일어난 일에 대한 정보를 테스트 보고서에 작성한다.
- c. 오답- 이 정보는 테스트 보고서에 들어가는 내용이다:
  + 종료 기준이나 완료 정의와 관련된 테스팅과 제품 품질 상태
  + 결함 메트릭, 테스트 케이스, 테스트 커버리지, 활동 진행률 및 리소스 소진상황 지표
- d. 오답- 이 정보는 테스트 보고서에 들어가는 내용이다; 남은 결함 평가, 테스트를 지속했을 때의 경제적 이익, 테스트 대상 소프트웨어에 대한 자신감 정도 등 향후 진행 방안에 대한 조언이나 판단을 돕기 위한 정보와 메트릭을 테스트 보고서에 작성한다.

</div>
</details>

---

A - Q35. “스마트” 가열 온도 조절기를 개발하는 프로젝트가 있다. 온도계의 제어 알고리즘은 Matlab/Simulink 모델로 모델링 되어 인터넷에 연결된 서버에서 실행된다. 온도 조절기는 서버의 명령에 따라 가열 밸브를 동작 시킨다.<br>
테스트 관리자는 테스트 계획에서 다음과 같은 테스트 전략/접근법을 정의했다.
1. 전체 시스템에 대한 인수 테스트는 경험 기반 테스트로 실행한다.
2. 서버의 제어 알고리즘은 에너지 절약 규정 표준에 맞춰 점검한다.
3. 온도계의 기능 테스트는 리스크 기반 테스트로 수행한다.
4. 인터넷을 통한 데이터/통신의 보안 테스트는 외부 보안 전문가와 함께 수행한다.

테스트 관리자가 테스트 계획에서 구현한 네 가지 유형의 테스트 전략/접근법은 무엇인가?
- a. 방법론적, 분석적, 반응적(reactive) 및 리그레션-기피(regression-averse)
- b. 분석적, 표준 준수(standard-compliant), 자문(consultative) 및 반응적
- c. 모델 기반, 방법론적, 분석적 및 자문
- d. 리그레션-기피, 자문, 반응적 및 방법론적

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.2.2 (K2) 여러 테스트 전략을 구별할 수 있다.<br>
1 번부터 4 번까지의 가능한 맵핑(mappings)은 다음과 같다:
1. 3 번 접근법은 분석적이다: 리스크 기반 테스팅은 리스크 수준에 따라 테스트를 설계하고 우선순위를 매기는 분석적 접근법의 예이다.
2. 2번 접근법은 표준 준수다: 제어 알고리즘은 에너지 절약 규정의 산업별 표준에 따라 점검을 받는다.
3. 4 번 접근법은 자문적이다: 이런 유형의 테스트 전략은 주로 테스트팀 외부나 조직 외부에 있을 수 있는 이해관계자/비즈니스 도메인 전문가/기술 전문가의 조언/안내/지침에 의해 진행된다.
4. 1 번 접근법은 반응적이다: “탐색적 테스팅(exploratory testing)은 반응적 전략에 사용되는 일반적인 기법으로, 탐색적 테스팅(explorative testing)이 경험기반 테스팅 범주에 할당돼 진행된다.

따라서:
- a. 오답
- b. 정답
- c. 오답
- d. 오답

</div>
</details>

---

A - Q36. 다음 중 테스트 추정에서 메트릭 기반 접근법의 특징은?
- a. 과거의 유사한 테스트 프로젝트의 예산을 참고한다.
- b. 테스트 관리자를 인터뷰하여 전반적인 경험을 수집한다.
- c. 테스트 자동화를 위한 노력의 추정은 테스트팀에서 합의로 도출한다.
- d. 비즈니스 전문가가 수집한 계산의 평균치를 사용한다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.2.6 (K2) 메트릭 기반 추정 기법과 전문가 기반 추정 기법의 차이를 설명할 수 있다.
- a. 정답: 메트릭 기반 접근: 과거 유사한 프로젝트의 메트릭에 기반해 테스팅 노력을 추정하거나 전형적인 값을 기반으로 한다.
- b. 오답: 전문가 기반 접근에 대한 설명이다. 업무 담당자나 전문가의 추정치에 기반해 업무를 예측한다.
- c. 오답: 전문가 기반 접근에 대한 설명이다. 업무 담당자나 전문가의 추정치에 기반해 업무를 예측한다.
- d. 오답: 전문가 기반 접근에 대한 설명이다. 업무 담당자나 전문가의 추정치에 기반해 업무를 예측한다.

</div>
</details>

---

A - Q37. 테스트 관리자로 당신은 아래의 요구사항 부분들을 테스트해야 한다:
- R1 – 프로세스 이상 (anomalies)
- R2 – 동기화
- R3 – 승인
- R4 – 문제 해결
- R5 – 회계 데이터
- R6 – 다이어그램 데이터
- R7 – 사용자 프로필 변경

<img src="/img/istqbCtfl/QnA_A37.png"/>

다음 중 요구사항의 의존관계에 따라 테스트 실행 일정을 구성한 것은?
- a. R1 -> R3 -> R4 -> R7 -> R2 -> R5 -> R6
- b. R1 -> R3 -> R2 -> R4 -> R7 -> R5 -> R6
- c. R1 -> R3 -> R2 -> R5 -> R6 -> R4 -> R7
- d. R1 -> R2 -> R5 -> R6 -> R3 -> R4 -> R7

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.2.4 (K3) 우선순위, 기술적 및 논리적 의존성 정보를 이용해 테스트 케이스 실행 일정을 수립할 수 있다.
- a. 오답: R4는 R2에 의존하므로 R4 보다 R2를 먼저 테스트해야 한다.
- b. 오답: R4은 R2, R5, R6에 의존하므로R4 보다R5, R6를 먼저 테스트해야 한다.
- c. 정답: 의존성을 고려하여 테스트 순서를 지정했다.
- d. 오답: R2는 R3에 의존하므로 R2보다 R3를 먼저 테스트해야 한다.

</div>
</details>

---

A - Q38. 커피머신을 위한 신규 버전의 소프트웨어를 테스팅하고 있다. 이 커피머신은 4 가지 범주(예: 사이즈, 설탕, 우유, 향 시럽)에 따라 다른 유형의 커피를 준비하며, 각 범주의 기준은 다음과 같다.:
- 사이즈 (S, M, L)
- 설탕 (없음, 1스푼, 2스푼, 3스푼, 4스푼)
- 우유 (있음, 없음)
- 향 시럽 (없음, 카라멜, 헤이즐넛, 바닐라)

당신은 다음과 같은 결함 보고서를 작성하고 있다.:
- 제목: 낮은 커피 온도
- 요약: 우유 추가 커피 선택 시, 커피 준비 시간이 너무 오래 걸리고 음료 온도가 너무 낮다 (40°C 미만)
- 기대 결과: 커피 온도는 표준 온도로 제공되어야 한다 (약 75°C)
- 리스크 수준: 중간
- 우선순위: 보통

다음 중 위의 결함 보고서에서 누락된 중요한 정보는 무엇인가?
- a. 실제 테스트 결과
- b. 테스트한 소프트웨어 버전의 식별
- c. 결함상태
- d. 테스트 케이스 개선 아이디어

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.6.1 (K3) 테스팅하면서 식별한 결함을 결함 보고서로 작성할 수 있다.
- a. 오답: 요약부분에 테스트 결과를 설명하고 있다.
- b. 정답: 다른 버전의 소프트웨어를 테스트할 때 식별 정보는 필수적이다 (실러버스 5.5 “결함 보고서의 내용” 4 번째).
- c. 오답: 결함보고서를 작성한 상태이므로 자동으로 “열림(open)” 상태가 된다.
- d. 오답: 테스트 케이스 개선 아이디어는 테스터에게 유용한 정보이지만 결함 보고서에 포함시킬 필요는 없다.

</div>
</details>

---

B - Q30. 다음 중 테스트의 독립성의 이점을 가장 잘 설명한 것은?
- A. 독립적인 테스트팀을 활용하면 프로젝트 관리자가 최종 산출물의 품질에 대한 책임을 테스트팀에 할당하게 되므로 모든 사람이 품질을 테스트팀의 책임이라고 인식하게 된다.
- B. 조직 외부에 테스트팀을 둘 수 있는 경우, 이 팀이 프로젝트 관리 측의 출시 관련 우려나 엄격한 출시 마감을 맞춰야 하는 필요에 쉽게 좌지우지되지 않는 측면에서 뚜렷한 이점이 있다.
- C. 독립적인 테스트팀은 개발자와 완전히 분리되어 업무를 수행하고, 프로젝트 요구사항 변경에 주의를 기울일 필요가 없으며 결함 관리 시스템을 통해 결함을 보고하므로 개발자와의 의사소통이 제한적일 수 있다.
- D. 요구사항이 모호하거나 일관성이 없는 경우에는 해석 중에 가정이 생기게 되며, 독립적인 테스터는 개발자가 만든 이런 가정과 해석에 대해 의문을 제기하는 데 유용할 수 있다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.1.1 (K2) 독립적 테스트의 장단점을 설명할 수 있다.
- A. 오답- 프로젝트에 참여하는 모든 사람이 품질에 대한 책임을 져야 한다. 품질은 테스트 팀만의 책임이 아니다.
- B. 오답- 우선 외부 테스트팀이 출시 마감을 지키지 못하는 것은 이점이 아니다. 그리고 외부 테스트팀은 납기일을 철저히 지킬 필요가 없다고 믿을 만한 근거도 없다.
- C. 오답- 테스트팀이 완전히 분리되어 일하도록 하는 것은 좋은 사례가 아니다. 사람들은 외부 테스트팀이 프로젝트 요구사항 변경을 인식하고 개발자와 원활히 소통하기를 기대할 것이다.
- D. 정답- 명세는 완벽할 수 없다. 즉 개발자에 의한 가정이 있을 수 있다. 독립적인 테스터는 개발자의 가정과 이후의 해석에 의문을 제기하고 검증할 수 있다는 이점이 있다.

</div>
</details>

---

B - Q31. 다음 중 테스트 관리자가 수행해야 하는 일로 가장 적절한 것은?
- A. 테스팅 수행 중 수집한 정보를 기반으로 테스트 요약 보고서 작성
- B. 다른 사람이 작성한 테스트 (케이스) 리뷰
- C. 테스트 데이터의 준비 및 획득
- D. 요구사항, 명세 및 테스트 용이성 모델의 분석, 리뷰, 평가

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.1.2 (K1) 테스트 관리자와 테스터의 역할을 식별할 수 있다.
- A. 정답- 테스트 관리자의 일반적인 업무이다.
- B. 오답- 테스터의 일반적인 업무이다.
- C. 오답- 테스터의 일반적인 업무이다.
- D. 오답- 테스터의 일반적인 업무이다.

</div>
</details>

---

B - Q32. 다음은 테스트 시작, 종료 조건의 예이다:
1. 초기 예산 30,000 달러와 추가적인 예비비 7,000 달러를 지출했다.
2. 인출 패키지에 대한 테스트를 계획 대비 96%를 수행했고, 남은 테스트는 현재 범위에 해당하지 않는다.
3. 거래 성능 테스트 환경을 설계, 셋업하고 확인했다.
4. 현재 눈에 띄는 심각한 결함은 없으며 2개의 우선순위가 높은 결함이 있다.
5. 자동조종장치 설계 명세를 리뷰하고 재작업했다.
6. 세율 계산 컴포넌트의 단위 테스트가 통과됐다.

다음 중 시작 조건과 종료 조건을 바르게 분류한 것은?
- A. 시작조건–5,6 종료조건–1,2,3,4
- B. 시작조건–2,3,6 종료조건–1,4,5
- C. 시작조건–1,3 종료조건–2,4,5,6
- D. 시작조건–3,5,6 종료조건–1,2,4

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.2.3 (K2) 시작 조건과 종료 조건에 대한 예제를 들 수 있다.<br>
각각의 예를 시작 조건과 종료 조건으로 구분해 보면 다음과 같다:<br>
시작 조건
- (3) 거래 성능 테스트 환경을 설계하고 셋업하고 확인했다 - 테스팅을 시작하기 전에 준비하는 테스트 환경의 필요성에 대한 예이다.
- (5) 자동조종장치 설계 명세를 리뷰하고 재작업했다 - 테스팅을 시작하기 전에 테스트 베이시스를 사용할 수 있어야 하는 필요성에 대한 예이다.
- (6) 세율 계산 컴포넌트의 단위 테스트가 통과되었다 - 테스팅을 시작하기 전에 테스트 대상이 이전 레벨의 테스팅의 종료 조건을 충족해야 할 필요성에 대한 예이다.

종료 조건
- (1) 초기 예산 30,000 달러와 추가적으로 예비비 7,000 달러를 지출했다 - 테스팅 예산을 테스팅 중단 신호로 사용하는 예이다.
- (2) 인출 패키지에 대한 테스트를 계획 대비 96% 수행했고, 남은 테스트는 현재 범위에 해당하지 않는 내용이다.
- (4) 현재 눈에 띄는 심각한 결함은 없으며 2 개의 우선순위가 높은 결함이 있다 - 테스팅 중단 신호로 계획 한도를 달성하는 미해결 결함 수의 예이다(일반적으로 계획한 테스트를 수행했는지에 대한 종료 조건과 함께 사용한다).

따라서 정답은 D 이다.

</div>
</details>

---

B - Q33. 다음은 각 테스트 케이스의 우선순위와 종속성(dependencies)을 나타낸 표이다:

<img src="/img/istqbCtfl/QnA_B33.png"/>

다음 중 우선순위와 기술적/논리적 종속성을 고려한 테스트 실행 계획으로 가장 적절한 것은?
- A. TC1 – TC3 – TC4 – TC6 – TC2 – TC5
- B. TC4 – TC3 – TC1 – TC2 – TC5 – TC6
- C. TC4 – TC1 – TC3 – TC5 – TC6 – TC2
- D. TC4 – TC2 – TC5 – TC1 – TC3 – TC6

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.2.4 (K3) 우선순위, 기술적 및 논리적 의존성 정보를 이용해 테스트 케이스 실행 일정을 수립할 수 있다.<br>
테스트 케이스는 우선순위에 따라 일정을 수립해야 하지만 종속성도 함께 고려해야 한다.<br>
우선순위가 가장 높은 테스트 케이스 두 개(TC1, TC3)가 모두 TC4 에 종속되어 있으므로 먼저 수행할 테스트 케이스의 순서는 TC4 – TC1 – TC3 또는 TC4 – TC3 – TC1 이다(TC1 과 TC3 중 어느 것을 먼저 수행해야 하는지는 알 수 없다).<br>
다음으로, 중간 우선순위를 갖는 TC6을 고려해야 한다. TC6은 TC5에, TC5는 TC2에 종속되어 있으므로 다음으로 이어질 3개의 테스트 케이스의 순서는 TC2 - TC5 – TC6이다.<br>
그러므로, 다음과 같은 2 개의 일정이 가능하다:
- TC4 – TC1 – TC3 – TC2 - TC5 – TC6 또는,
- TC4 – TC3 – TC1 – TC2 - TC5 – TC6

따라서, 정답은 B 이다.

</div>
</details>

---

B - Q34. 다음 중 테스트 추정 접근법(test estimation approaches)에 대한 설명으로 맞는 것은?
- A. 메트릭 기반 접근법은 프로젝트의 테스트 측정값을 기반으로 추정하므로 테스트를 시작한 후에만 사용 가능하다.
- B. 전문가 기반 접근법은 고객이 선별한 전문가 그룹이 필요한 테스트 예산을 권장하는 것이다.
- C. 전문가 기반 접근법은 다양한 테스팅 활동을 담당하는 테스트 리더들이 예상 테스팅 노력을 예측하는 것이다.
- D. 메트릭 기반 접근법은 과거의 여러 프로젝트의 평균 테스팅 비용을 테스팅 예산으로 사용한다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.2.6 (K2) 메트릭 기반 추정 기법과 전문가 기반 추정 기법의 차이를 설명할 수 있다.
- A. 오답- 추가 정보가 있으면 추정에 반영할 수 있겠지만, 추정은 테스팅을 시작하기 전 계획을 돕기 위해 필요한 것이다.
- B. 오답- 전문가 기반 접근법에서 전문가는 테스트 대상 사용에서의 전문가가 아니라 테스팅에서의 전문가여야 한다
- C. 정답- 테스팅을 실질적으로 수행하는 테스터를 이끄는 테스트 리더들은 해당 분야의 전문가로 간주되며 필요한 자원을 예측하는 데 적합하다.
- D. 오답- 과거 프로젝트의 테스팅 비용을 아는 것도 유용하지만 단순히 과거 프로젝트의 평균값을 사용하기보다는 좀더 정교한 기법이 필요하다(새로운 프로젝트가 과거의 프로젝트와 유사하지 않을 수도 있다. 예를 들어, 과거 프로젝트에 비해 규모가 커지거나 작아질 수 있다).

</div>
</details>

---

B - Q35. 다음 중 리스크 수준을 가장 잘 정의한 것은?
- A. 리스크 수준은 모든 문제 상황이 발생할 가능성과 그에 따른 경제적인 손실을 합산하여 계산한다.
- B. 리스크 수준은 시스템의 위험 발생 가능성과 위험이 발생해 경제적 손실이 일어날 가능성을 곱하여 예측한다.
- C. 리스크 수준은 원치 않는 일이 일어날 가능성과 그 영향도의 조합으로 결정한다.
- D. 리스크 수준은 시스템의 모든 잠재적 위험의 합과 그 시스템의 모든 잠재적 손실의 합을 곱한 값이다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.5.1 (K1) 장애 발생 가능성과 영향도를 이용해 리스크 수준을 정의할 수 있다.
- A. 오답- 리스크는 문제 상황이 발생할 가능성과 그 문제로 인한 손실의 조합이다. 이 두 값을 더하는 방식으로는 계산할 수 없다(가능성은 0부터 1까지의 값을 갖고 손실은 보통 금액으로 표시한다).
- B. 오답- 리스크는 발생 가능성과 영향도의 조합으로 결정된다. 이 문장에서는 영향도(또는 손실)에 대한 고려 없이 모두 가능성(둘 다 확률의 형태)만을 고려하고 있다.
- C. 정답- 다른 오답 해설 참조
- D. 오답- 리스크는 발생 가능성과 영향도의 조합을 고려해 결정된다. 이 문장에서는 가능성(또는 확률)은 고려하지 않고 위험과 손실(위험은 안 좋은 일을 의미하므로 리스크와 유사하고 손실은 영향도의 형태이다)만을 고려하고 있다.

</div>
</details>

---

B - Q36. 다음 중 제품 리스크의 예가 될 수 있는 것은?
- A. 시스템 아키텍처가 기대하는 보안기능을 지원하지 않을 수도 있다.
- B. 개발자가 테스트 팀이 발견한 결함을 모두 수정할 시간이 없을 수 있다.
- C. 테스트 케이스가 명시된 요구사항의 커버리지를 모두 만족시키지 못할 수 있다.
- D. 시스템이 전달되는 시점까지 성능 테스트 환경을 준비하지 못할 수 있다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.5.2 (K2) 프로젝트 리스크와 제품 리스크를 구별할 수 있다.
- A. 정답- 시스템 아키텍처가 기대하는 보안 기능을 제공하지 않는 것은 시스템의 심각한 결함이 될 수 있다. 개발하고 있는 시스템의 문제이므로 제품 리스크이다.
- B. 오답- 개발자가 예산을 초과하거나 일정을 맞추지 못하게 되면 프로젝트 수행에 문제가 생기게 된다. 이는 프로젝트 리스크이다.
- C. 오답- 테스트 케이스가 요구사항 커버리지를 충분히 만족하지 못한다는 것은 테스팅이 테스트 계획의 요구사항을 만족하지 못한다는 의미이다. 이는 프로젝트 리스크이다.
- D. 오답- 테스트 환경이 준비되지 않으면 테스팅을 수행할 수 없거나, 다른 환경에서 수행해야 하므로 프로젝트 수행 방법에 영향을 주게 된다. 프로젝트 리스크이다.

</div>
</details>

---

B - Q37. 다음 중 제품 리스크 분석이 테스팅에 바로 영향을 주는 예로 가장 거리가 먼 것은?
- A. 보안 결함으로 인한 잠재적인 영향이 매우 높을 것으로 확인되어, 다른 테스팅 활동보다 보안 테스팅의 우선순위를 높였다.
- B. 테스팅 결과 네트워크 모듈의 품질이 예상보다 높은 것으로 확인돼, 해당 영역에서는 추가 테스트를 수행할 것이다.
- C. 사용자들이 이전 시스템에서 사용자 인터페이스 문제를 겪었으므로 대체 시스템을 위해 추가적인 사용성 테스팅을 계획했다.
- D. 웹페이지 로딩 시간이 새로운 웹사이트 성공에 결정적 요인이므로 이 프로젝트에 성능 테스팅 전문가를 영입했다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.5.3 (K2) 이 문제는 제품 리스크 분석의 부적절한 적용을 다루고 있다.
- A. 오답- 보안 결함으로 인한 영향이 특히 높을 것이라고 말했으므로 보안의 리스크 수준이 높아져 보안성 테스팅의 우선순위도 다른 테스팅보다 높아진다. 따라서 제품 리스크 분석이 적절하게 테스팅에 영향을 주었다.
- B. 정답- 네트워크 모듈에서 예상보다 결함이 적게 나왔다면 이 모듈의 리스크가 낮아지게 되어 이 영역에 추가적인 테스팅이 아니라 더 적게 테스팅을 하게 된다. 따라서 이 상황은 제품 리스크 분석이 테스팅에 영향을 주는 경우가 아니다.
- C. 오답- 사용자가 이전 시스템에서 사용자 인터페이스 문제를 겪었으므로 결과적으로 추가적인 사용성 테스팅이 계획된 것이다. 따라서 제품 리스크 분석이 적절하게 테스팅의 정밀함과 범위에 영향을 주었다.
- D. 오답- 웹페이지 로딩 시간이 새로운 웹사이트 성공에 결정적이라고 했으므로 웹사이트의 성능이 리스크로 간주되며 성능 테스팅 전문가의 영입은 이 리스크를 완화하는 데 도움을 준다. 따라서 제품 리스크 분석이 적절하게 테스팅에 영향을 주었다.

</div>
</details>

---

B - Q38. 열차 예약 시스템의 시스템 테스팅을 수행하고 있다. 수행한 테스트 케이스를 검토하니 시스템에서 사용 가능한 열차가 있음에도 불구하고 없다고 보고하는 경우가 있음을 발견했다. 개발자에게 결함 요약과 테스트한 시스템 버전을 제공했다. 개발자들은 결함의 긴급성을 인식하고 이제 더 자세한 정보를 전달해주길 기다리고 있다.<br>
위에 제공된 정보 외에 다음과 같은 추가 정보들이 주어졌다고 할 때:
1. 결함의 영향(심각성) 정도
2. 테스트 대상의 식별
3. 테스트 환경의 상세 정보
4. 수정 긴급도/우선순위
5. 실제결과
6. 테스트 케이스 명세 참조

다음 중 결함 보고서에 포함하면 가장 유용할 수 있는 추가 정보는?
- A. 1,2,6
- B. 1,4,5,6
- C. 2,3,4,5
- D. 3,5,6

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.6.1 (K3) 테스팅하면서 식별한 결함을 결함 보고서로 작성할 수 있다.<br>
각각의 정보를 살펴보자:
1. 결함의 영향(심각성) 정도- 개발자가 이미 이 문제에 대해 알고 있고 수정하려고 대기하고 있으므로 이 정보는 다른 정보에 비해 덜 중요하다.
2. 테스트 대상의 식별- 개발자가 이미 이 문제에 대해 알고 있고 당신은 시스템 테스팅을 수행하고 있다. 또한 시스템 버전도 이미 제공했으므로 개발자들도 테스트한 대상을 알고 있을 거라고 볼 수 있다. 따라서 이 정보는 다른 정보에 비해 덜 중요하다.
3. 테스트 환경의 상세 정보- 테스트 환경이 어떻게 구성되어 있는지에 따라 테스트 결과에 현저하게 영향을 주기 때문에 상세한 정보를 제공해야 한다. 따라서 이 항목은 중요한 정보이다.
4. 수정 긴급도/우선순위- 개발자가 이미 이 문제에 대해 알고 있고 수정하려고 대기하고 있으므로 이 정보는 다른 정보에 비해 덜 중요하다.
5. 실제 결과- 실제 결과는 개발자가 시스템의 문제점을 파악하는데 도움이 될 수 있으므로 중요한 정보이다.
6. 테스트 케이스 명세 참조- 이 정보는 개발자에게 당신이 실행한 테스트(시스템 실패를 가져온 테스트 입력 및 예상 결과를 포함하는)를 보여주므로 중요한 정보이다.

따라서, 정답은 D 이다.

</div>
</details>

---

C - Q30. 당신은 온라인 뱅킹 시스템의 테스터로 일하고 있다. 가용성(Availability)은 이 시스템의 중요 제품(품질) 리스크 중 하나이다. 일반 유형 계정 간 자금을 이체하고 3-5분 동안 다시 연결되지 않으면 고객의 은행 웹사이트 연결이 끊어지는 장애를 발견했으며 이 문제는 반복적 재현이 가능했다.<br>
다음 중 이 장애를 보고하는 결함 보고서로 장애 필수사항과 이해관계자에게 미치는 영향을 요약한 것으로 가장 적절한 것은?
- a. 07.005 테스트 수행 중 웹서버 로그에 ‘/ tmp’ 파일 시스템에서 예상되는 오류 메시지가 아닌 ‘0x44AB27’이 나타남
- b. 개발자가 고객이 문제를 제기할만한 심각한 가용성 관련 주요 결함을 일으킴
- c. 부하 상태에서 성능이 저하되고 안정성이 떨어짐
- d. 일반적인 자금 이체 거래가 고객 세션을 종료시킴. 재 연결 시도 시 가용성이 지연됨

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.6.1, K3
- a. 오답- 이 정보가 개발자에게는 유용하지만 제품 품질에 끼치는 영향에 대한 의미를 관리자에게 제공하지는 않는다.
- b. 오답- 이 요약은 개발자나 관리자에게 필요한 정보를 제공하지 않으며 개발자를 비난하는 행위이다.
- c. 오답- 이 요약은 개발자나 관리자에게 필요한 정보를 제공하지 않으며 개발자를 비난하는 행위이다.
- d. 정답- 이 요약은 장애와 그 영향에 대한 좋은 예를 제공하고 있다.

</div>
</details>

---

C - Q31. 당신은 고객이 선호하는 음식 유형을 기반으로 고객 근처의 음식점을 찾아주는 모바일 앱을 테스트하고 있다. 아래 목록에는 각 테스트 케이스의 우선순위 (숫자가 작을수록 우선순위가 높음)와 종속성이 표기돼 있다:

<img src="/img/istqbCtfl/QnA_C31.png"/>

다음 중 우선순위와 종속성을 고려한 테스트 실행 일정은?
- a. 01.001, 01.002, 01.003, 01.005
- b. 01.001, 01.002, 01.004, 01.003
- c. 01.003, 01.004, 01.002, 01.001
- d. 01.001, 01.002, 01.004, 01.005

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.2.4, K3<br>
종속성을 충족하기 위해 테스트 01.001을 먼저 실행하고 01.002를 뒤따라 실행해야 한다. 그런 다음 우선순위를 충족하기 위해 01.004와 01.003을 순서대로 실행하고 01.005를 실행해야 한다. 모든 테스트는 정확히 한 번 실행해야 한다.<br>
따라서, b.가 정답이다.(실러버스 문제의 그림에 01.005는 없지만 b로 유추할 수 있다)

</div>
</details>

---

C - Q32. 다음 중 테스트 준비와 테스트 실행 두 가지 모두를 모니터링하는 데 자주 사용하는 공통 테스트 메트릭은?
- a. 테스트 케이스 상태
- b. 결함 발견/수정률
- c. 테스트 환경 준비
- d. 다음 결함을 찾는 데 들어갈 예측 비용

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.3.1, K1
- a. 정답- 테스트 케이스 준비율은 테스트 준비 중에 사용하는 일반적인 메트릭이며 테스트 케이스 성공, 실패, 미실행율 등은 테스트 실행 중에 사용하는 일반적인 메트릭이다.
- b. 오답- 결함 보고서는 일반적으로 발견된 장애를 기반으로 테스트 실행 중에 제출된다.
- c. 오답- 테스트 환경 준비는 구현활동의 일부이며 보통 테스트 실행 전에 완료된다.
- d. 오답- 결함 보고서는 일반적으로 발견된 장애를 기반으로 테스트 실행 중에 제출된다. 따라서 다음 결함을 찾는 데 드는 비용은 테스트 실행 중에만 사용할 수 있다.

</div>
</details>

---

C - Q33. 다음 중 리스크 레벨을 결정하는 데 사용하는 두 가지 요소는?
- a. 테스팅과 개발
- b. 정적인 것과 반응적인 것
- c. 구문과 결정문
- d. 발생가능성과 영향도

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.5.1, K1<br>
리스크 레벨은 부정적인 일이 발생할 가능성과 그 일로 인한 영향(피해)으로 결정한다.<br>
따라서, d.가 정답이다.

</div>
</details>

---

C - Q34. 당신은 사내 뱅킹 소프트웨어 프로젝트의 프로젝트 관리자로 일하고 있다.<br>
과도한 결함 발견/수정/재테스트 반복 업무를 방지하기 위해, 테스트 랩에서 결함이 발견되면 이를 해결하기 위해 다음과 같은 프로세스를 마련했다:
1. 담당 개발자가 결함을 발견하고 수정한 후 실험 빌드(experimental build)를 생성한다.
2. 짝 개발자(peer developer)가 자신의 데스크탑에서 수정한 결함을 리뷰하고, 단위 테스트와 확인 테스트(confirmation tests)를 수행한다.
3. (주로 결함을 발견한) 테스터가 개발자 환경에서 결함이 수정되었는지 확인 테스트를 수행한다.
4. 하루 한 번씩 확인된 모든 결함 수정을 포함한 새 릴리스를 테스트 랩에 설치한다.
5. 3번 절차와 동일한 테스터가 테스트 환경에서 결함이 수정되었는지 확인 테스트를 수행한다.

이런 절차에도 불구하고 테스터가 개발 환경에서 수정된 것으로 확인한(3번 절차) 많은 결함들이 테스트 환경에서 수행하는 확인 테스트에 실패해 결과적으로 재 작업과 반복주기 시간이 필요해졌다. 당신은 테스터들에 대해 높은 신뢰를 가지고 있으며, 3번 절차에서의 실수나 누락은 배제하고 있다.

다음 중 점검해야 할 다음 프로세스로 가장 적합한 것은?
- a. 2번 절차에서 테스트를 제대로 하지 않을 수 있는 개발자의 활동
- b. 5번 절차에서 무얼 테스트할지 혼란스러울 수 있는 테스터의 활동
- c. 4번 절차에서 제품의 무결성을 유지하지 못할 수 있는 형상 관리
- d. 1번 절차에서 결함을 제대로 수정하지 않을 수 있는 개발자의 활동

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.4.1, K2
- a. 오답- 개발자가 테스팅을 제대로 하지 않았다면, 3번 절차에서 확인 테스트를 통과하지 못했을 것이다.
- b. 오답- 3번 절차에서 확인 테스트를 성공적으로 수행한 같은 테스터가 5번 절차에서도 이를 반복하고 있다.
- c. 정답- 형상 관리는 소프트웨어의 무결성을 유지한다. 3번 절차에서 성공한 테스트가 5번 절차에서 실패했다면, 이 두 절차 사이에 뭔가 다른 것이 있는 것이다. 가능한 경우 중 하나는 여기에 언급된 테스트 대상이다. 또 다른 가능한 경우는 개발 환경과 테스트 환경의 차이이지만 이는 여기에 언급돼 있지 않다.
- d. 오답- 개발자가 결함을 수정하지 않았다면 3번 절차에서 확인 테스트를 통과하지 못했을 것이다.

</div>
</details>

---

C - Q35. 신규 모바일 뱅킹 애플리케이션에 들어갈 테스트 노력(test effort)을 산출하고 있다. 추정 활동의 일환으로, 이 프로젝트에 참가할 테스터와 다른 이해관계자들을 처음 만나기로 했다. 이 팀은 협업 능력이 뛰어나고 이미 유사한 프로젝트를 수행한 경험이 있다. 추정 결과를 확인하기 위해 저명한 컨설턴트가 출판한 유사 프로젝트의 테스팅 노력과 비용의 업계 평균치를 참고하려고 한다.<br>
다음 중 이 추정 접근법을 정확히 설명하고 있는 것은?
- a. 전문가 기반과 메트릭 기반 접근을 동시에 사용했다.
- b. 전문가 기반을 주로 사용하고 메트릭 기반 접근이 추가되었다.
- c. 메트릭 기반을 주로 사용하고 전문자 기반 접근이 추가되었다.
- d. 플래닝 포커를 주로 사용하고 번다운 차트에서 속도를 확인했다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.2.6, K2
- a. 오답- 두 가지 방법이 동시에 사용되지 않고 순차적으로 사용된다.
- b. 정답- 정보의 주요 원천은 전문가인 숙련된 테스터이다. 컨설턴트의 업계 평균치는 출판된 메트릭의 원래 추정치를 증가시킨다.
- c. 오답- 전문가 기반 접근법이 메트릭 기반 접근법으로 강화된 주요 접근법이다.
- d. 오답- 이 프로젝트가 애자일 방법을 따르고 있는지는 알 수 없으며 번다운 차트는 외부 컨설턴트가 작성하지 않는다.

</div>
</details>

---

C - Q36. 애자일 방법을 따르는 프로젝트에서 사용자스토리 개선 미팅 중 제기한 인수 조건에 대해 개발자와 제품 담당자의 해석이 다르다는 것을 발견했다.<br>
이런 상황에서 알 수 있는 테스트 독립성의 이점은?
- a. 다른 종류의 결함을 발견할 수 있다.
- b. 품질에 대해 주요 책임을 갖는다.
- c. 결함을 초기에 제거한다.
- d. 이해관계자의 가정에 이의를 제기할 수 있다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.1.1, K2
- a. 오답- 독립적 테스터의 이점은 다른 종류의 장애를 찾아낼 수 있다는 것이다. 이 시나리오에서 실패할 것으로 보이는 코드가 아직 없고, 개발자와 제품 소유자가 모두 인수 기준에 대해 다른 가정을 하고 있다는 것이 문제이다.
- b. 오답- 개발자가 품질에 대한 책임감을 잃어버리는 것은 장점이 아니라 단점이다.
- c. 오답- 이러한 의견 불일치의 발견으로 얻는 효과는 코딩하기 전에 결함을 조기에 제거하는 것이며, 독립적인 테스터뿐만 아니라 다양한 사람들이 초기에 결함을 발견할 수 있다.
- d. 정답- 이해관계자의 가정에 이의를 제기하는 것은 테스터 독립성의 이점이며 여기에서 개발자와 제품 소유자 모두 인수 기준에 대해 다른 가정을 하고 있다.

</div>
</details>

---

C - Q37. 당신은 애자일 프로젝트에서 각 반복주기의 일부로 제품 리스크 분석을 수행하는 프로세스를 정의하고 있다.<br>
다음 중 테스트 계획에서 이 프로세스를 문서화할 가장 적절한 위치는?
- a. 테스팅 범위
- b. 테스팅 접근법
- c. 테스팅 메트릭
- d. 테스트 항목의 형상 관리

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.2.1, K2
- a. 오답- 범위는 테스트 계획에서 다루는 주제이지만, 이 프로젝트에 대한 리스크 기반 테스팅 전략의 구현은 접근 방식이므로 이 항목은 해당 섹션에서 다뤄야 한다.
- b. 정답- <span style="color:red">접근 방식은 테스트 계획에서 다루는 주제이고 이 프로젝트에 대한 리스크 기반 테스팅 전략의 구현은 이 접근 방식이다.</span>
- c. 오답- 테스트 모니터링과 제어를 위한 메트릭은 테스트 계획에서 다루는 주제이지만, 이 프로젝트에 대한 리스크 기반 테스팅 전략의 구현은 접근 방식이므로 이 항목은 해당 섹션에서 다뤄야 한다.
- d. 오답- 형상 관리는 테스트 계획에서 다루는 주제가 아니다.

</div>
</details>

---

C - Q38. 다음은 모바일 앱 개발 시 바람직하지 않은 결과를 나열한 것이다:
- A. 스크린에 보이는 잘못된 합계
- B. 인수 테스팅 도중 인수 조건 변경
- C. 사용자가 앱에서 소프트 키보드 사용이 너무 어렵다고 느낌
- D. 검색어 입력 중 시스템이 사용자 입력에 너무 느리게 응답함
- E. 일일 스탠딩 회의에서 테스터의 결과 보고가 금지되어 있음

다음 중 위의 내용을 제품 리스크와 프로젝트 리스크로 바르게 분류한 것은?

- a. 제품 리스크:B,E 프로젝트 리스크:A,C,D
- b. 제품 리스크:A,C,D 프로젝트 리스크:B,E
- c. 제품 리스크:A,C,D,E 프로젝트 리스크:B
- d. 제품 리스크:A,C 프로젝트 리스크:B,D,E

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-5.5.2, K2<br>
작업 산출물이 합법적인 요구를 충족시키지 못할 때 제품 리스크가 존재하지만, 프로젝트 리스크는 프로젝트의 목표를 달성하는 데 부정적인 영향을 미칠 수 있는 상황이다. 따라서:
- A. 스크린에 보이는 잘못된 합계 오류: 제품 리스크
- B. 인수 테스팅 도중 인수 조건 변경: 프로젝트 리스크
- C. 사용자가 앱과 함께 소프트 키보드를 사용하기가 너무 어려움: 제품 리스크
- D. 검색어 입력 중 시스템이 사용자 입력에 너무 느리게 응답함: 제품 리스크
- E. 일일 스탠딩 회의에서 테스터가 테스트 결과를 보고하지 못함: 프로젝트 리스크

- a. 오답- 제품 리스크와 프로젝트 리스크를 반대로 연결했다.
- b. 정답
- c. 오답- E가 제품 품질과 제품 리스크에 관한 것이지만, 테스트 결과를 전달하는데 실패한 것은 실러버스에 따르면 프로젝트 리스크이다.
- d. 오답- 제품 리스크는 기능과 관련된 것일 수도 있고 비기능과 관련된 것일 수도 있다. 따라서 D는 제품 리스크이다.

</div>
</details>

# ● 자료참고
{: .notice--info .text-center}

[실러버스 본문](http://www.kstqb.org/board_skin/board_view.asp?idx=426&page=1&bbs_code=4&key=0&word=&etc=ISTQB){: .btn .btn--info}
[실러버스 용어](http://www.kstqb.org/board_skin/board_view.asp?idx=342&page=2&bbs_code=4&key=0&word=&etc=ISTQB){: .btn .btn--info}
[샘플문제](http://www.kstqb.org/board_skin/board_view.asp?idx=433&page=2&bbs_code=5&key=0&word=&etc=){: .btn .btn--info}