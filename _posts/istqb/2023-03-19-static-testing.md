---
title: "[Foundation Level] 제 3장. 정적 테스팅"
excerpt: "Foundation Level Chapter.3 Static Testing"
categories: istqb
tag: [ISTQB, Foundation Level]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# 3.1 정적 테스팅 기초 (Static Testing Basics)
{: .notice--warning .text-center}

<span style="color:blue">테스트하고 있는 소프트웨어의 실행이 필요한 동적 테스팅과는 달리 정적 테스팅은 작업 산출물을 수동으로 검사(예: 리뷰)하거나 코드나 다른 작업 산출물을 도구를 기반으로 평가(tool-driven evaluation 예: 정적 분석)하는 방법에 의존한다. 두 가지 유형의 정적 테스팅 모두 테스트 중인 코드 또는 작업 산출물을 실제로 실행하지 않고 평가한다.</span><br>
정적 분석은 안전 최우선 컴퓨터 시스템(예: 항공, 의료, 원자력 소프트웨어)에서 중요하지만 다른 영역에서도 점차 그 중요성이 일반화되고 있다. 예를 들어, 보안 테스팅에서 정적 분석은 중요한 부분이며, 또한 애자일 개발, 지속적 인도(continuous delivery), 지속적 배포(continuous deployment) 등과 같은 자동화된 소프트웨어 빌드나 배포 도구(distribution tools)에 통합되는 경우가 많다.

## 3.1.1 정적 테스팅으로 검토할 수 있는 작업 산출물 (Work Products that Can Be Examined by Static Testing)
{: .notice--success}

<span style="color:green">(K1) 다양한 정적 테스팅 기법으로 확인할 수 있는 소프트웨어 작업 산출물 유형을 인식할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">대부분의 작업 산출물은 정적 테스팅(리뷰나 정적 분석)으로 검사 할 수 있다</span>. 예를 들어:
- <span style="background-color:rgb(237,220,195);">비즈니스 요구사항, 기능 요구사항, 보안 <span style="color:red">요구사항과 같은 명세</span></span>
- <span style="background-color:rgb(237,220,195);">에픽(epic), 사용자 스토리, 인수 기준</span>
- <span style="background-color:rgb(237,220,195);">아키텍처 및 설계 명세</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">코드</span></span>
- <span style="background-color:rgb(237,220,195);">테스트 계획, 테스트 케이스, 테스트 프로시저, 자동화 테스트 스크립트와 같은 테스트웨어</span>
- <span style="background-color:rgb(237,220,195);">사용자 가이드</span>
- <span style="background-color:rgb(237,220,195);">웹 페이지</span>
- <span style="background-color:rgb(237,220,195);">계약, 프로젝트 계획, 일정, 예산 기획</span>
- <span style="background-color:rgb(237,220,195);">형상(configuration) 및 인프라(infrastructure) 셋업</span>
- <span style="background-color:rgb(237,220,195);">액티비티 다이어그램과 같은 모델 기반 테스팅에 사용되는 모델</span> (ISTQB-CTFL-MBT, Kramer 2016) 참조

정적 분석은 적절한 정적 분석 도구가 존재하는 공식 구조를 사용하는 작업 산출물(일반적으로 코드 또는 모델)에 효율적으로 적용할 수 있다. 정적 분석은 요구사항과 같은 자연어로 작성된 작업 산출물을 평가하는 도구로 적용할 수도 있다 (예: 맞춤법, 문법 및 가독성 검사).

## 3.1.2 정적 테스팅의 효과 (Benefits of Static Testing)
{: .notice--success}

<span style="color:green">(K2) 정적 테스팅의 가치를 예제를 통해 설명할 수 있다.</span>

정적 테스팅 기법은 여러 이점이 있다. <span style="color:blue">정적 테스팅을 소프트웨어 개발 수명주기 초반에 적용하면 동적 테스팅을 실행하기 전 결함의 조기 발견을 가능하게 한다</span> (예: 요구사항이나 설계 명세 리뷰, 백로그 재 정의(refinement) 등). 개발 초기에 발견한 결함을 제거하는 데 드는 비용은 수명주기 후반에 발견한 결함을 제거하는 비용에 비해 훨씬 적게 들며, 특히 소프트웨어를 배포하고 실제 사용하는 단계와 비교하면 더 현저하다. 정적 테스팅 기법을 사용해 결함을 발견하고 바로 수정하는 것이 동적 테스팅으로 결함을 발견하고 수정하는 것에 비해 적은 비용이 드는 경우가 대부분이다. 특히, 작업 산출물의 업데이트와 확인, 리그레션 테스팅 수행과 관련된 추가 비용을 고려하면 이는 더 명확해진다.<br>
그 외 <span style="background-color:rgb(207,228,207);">정적 테스팅의 효과</span>에는 다음과 같은 것들이 있다:
- <span style="background-color:rgb(237,220,195);">동적 테스트 실행 전에 보다 효율적으로 결함을 발견하고 수정</span>
- <span style="background-color:rgb(237,220,195);">동적 테스팅으로 발견이 쉽지않은 결함 식별</span>
- <span style="background-color:rgb(237,220,195);">요구사항 불일치, 애매 모호함, 모순, 누락, 부정확, 중복 등을 식별해서 설계나 코딩의 결함 예방</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">개발 생산성 향상</span> (예: 설계 개선, 향상된 코드 유지보수성)</span>
- <span style="background-color:rgb(237,220,195);">개발 비용 및 기간 단축</span>
- <span style="background-color:rgb(237,220,195);">테스팅 비용 및 기간 단축</span>
- <span style="background-color:rgb(237,220,195);">수명주기 후반 또는 출시 후 운영 과정에서 발견되는 장애 감소로 소프트웨어 수명주기 전반에 걸친 총 품질 비용 감소</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">리뷰에 참여하는 팀원 간의 의사소통 개선</span></span>

## 3.1.3 정적 테스팅과 동적 테스팅의 차이 (Differences between Static and Dynamic Testing)
{: .notice--success}

<span style="color:green">(K2) 정적 기법과 동적 기법의 차이를 테스트목적, 식별해야 하는 대상 결함 유형, 소프트웨어 수명주기에서의 역할 등을 고려해 설명할 수 있다.</span>

<span style="color:blue">정적 테스팅과 동적 테스팅의 공통 목적(1.1.1 절 참조)은 작업 산출물의 품질을 평가하고 가능한 빨리 결함을 식별하는 것</span>이다. <span style="color:blue">정적 테스팅과 동적 테스팅은 발견하는 유형의 결함이 서로 달라 상호 보완적</span>이다.<br>
가장 중요한 차이점 중 하나는 정적 테스팅은 소프트웨어를 실행해 결함으로 발생하는 장애를 찾아내기보다는 작업 산출물에서 직접 결함을 발견한다는 것이다. <u>결함은 장애를 일으키지 않고 작업 산출물에 상당히 오랜 기간 숨어 있을 수 있다</u>. 결함이 존재하는 경로가 드물게 실행되거나 접근하기 어려워 이런 경로에 도달하는 동적 테스트를 구축하고 실행하는 것은 쉽지 않다. 반면 정적 테스팅은 훨씬 적은 노력으로 결함을 발견할 수 있다.<br>
또 다른 차이점은 <u>정적 테스팅은 작업 산출물의 일관성과 내부 품질을 향상하기 위해 사용하는 반면, 동적 테스트는 일반적으로 외부에 보이는 동작에 초점을 맞추고 있다</u>는 점이다.<br>
<span style="background-color:rgb(207,228,207);">동적 테스팅과 비교해 정적 테스팅으로 발견하기 쉽고 비용도 적게 들어가는 일반적인 결함 유형</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);"><span style="color:red">요구사항</span> 결함 (예: 불일치, 모호함, 모순, 누락, 부정확, 중복 등)</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">설계</span> 결함 (예: 비효율적인 알고리즘(algorithm)이나 데이터베이스 구조, 높은 결합도(coupling), 낮은 응집도(cohesion)) 등</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">코딩</span> 결함(예: 정의되지 않은 값이 있는 변수, 선언했으나 사용하지 않는 변수, 도달할 수 없는 코드, 중복 코드 등)</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">표준과의 차이</span>(예: 코딩 표준 미준수 등)</span>
- <span style="background-color:rgb(237,220,195);">잘못된 <span style="color:red">인터페이스 명세</span> (예를 들어, 호출하는 시스템과 호출되는 시스템이 서로 다른 측정 단위 사용)</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">보안</span> 취약점 (예를 들어, 버퍼 오버플로우에 대한 취약성)</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">테스트 베이시스 추적성</span>이나 <span style="color:red">불충분한 커버리지 또는 부정확성</span> (예를 들어, 특정 인수 조건에 대한 테스트 누락)</span>

<u>또한 대부분의 유지보수성 결함은 정적 테스팅으로만 발견할 수 있다 (예: 잘못된 모듈화, 낮은 컴포넌트 재사용성, 새로운 결함을 발생시키지 않고는 분석하거나 수정하기 어려운 코드 등)</u>.

# 3.2 리뷰 프로세스 (Review Process)
{: .notice--warning .text-center}

<span style="background-color:rgb(232,233,234);">리뷰 유형은 공식 리뷰에서 비공식 리뷰까지 다양하다. 비공식 리뷰의 특징은 정의된 프로세스를 따르지 않고, 리뷰 결과를 공식적으로 문서화하여 제공하지 않는다는 점이다. 공식 리뷰의 특징은 팀 참여, 문서화된 리뷰 결과, 문서화된 리뷰 진행 절차 등이 있다. 리뷰 프로세스의 형식은 소프트웨어 개발 수명주기 모델, 개발 프로세스의 성숙도, 리뷰 대상 작업 산출물의 복잡도, 다양한 법적 또는 규정 요구사항이나 감사 추정의 필요성과 같은 요소와 관련이 있다.<br>
리뷰의 중점은 합의된 리뷰 목적에 따라 결정된다 (예: 결함 발견, 이해 향상, 테스터와 신규 팀원 등과 같은 참여자에 대한 교육 또는 토론과 합의에 의한 결정).</span><br>
ISO 표준(ISO/IEC 20246)에 역할과 리뷰 기법 포함, 작업 산출물에 대한 리뷰 프로세스의 구체적인 설명이 있다.

## 3.2.1 작업 산출물 리뷰 프로세스 (Work Product Review Process)
{: .notice--success}

<span style="color:green">(K2) 작업 산출물 리뷰 프로세스 활동을 요약할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">리뷰 프로세스의 주요 활동</span>은 다음과 같다:

**<span style="background-color:rgb(237,220,195);">계획 (Planning)</span>**
- <span style="background-color:rgb(242,213,214);">리뷰 목적, 리뷰할 문서가 전체인지 특정 부분인지, 평가할 품질 특성 등을 포함하는 범위의 정의</span>
- <span style="background-color:rgb(242,213,214);">노력과 기간 추정</span>
- <span style="background-color:rgb(242,213,214);">리뷰 유형에 따라 결정되는 역할, 활동, 체크리스트와 같은 리뷰 특성의 식별</span>
- <span style="background-color:rgb(242,213,214);">리뷰에 참석할 인원을 선정하고 역할 할당</span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">인스펙션과 같은 보다 공식적인 리뷰의 경우에는 시작 및 종료 조건 정의</span></span>
- <span style="background-color:rgb(242,213,214);">(공식적인 리뷰 유형의 경우) 시작 조건이 충족되는지 확인</span>

**<span style="background-color:rgb(237,220,195);">리뷰 착수 (Initiate review)</span>**
- <span style="background-color:rgb(242,213,214);">(물리적 또는 전자적 수단에 의한) 작업 산출물과 이슈 기록(issue log) 양식, 체크리스트, 관련된 작업 산출물과 같은 기타 자료 배포</span>
- <span style="background-color:rgb(242,213,214);">참가자에게 범위, 목적, 프로세스, 역할, 작업 산출물을 설명</span>
- <span style="background-color:rgb(242,213,214);">참가자가 리뷰에 대해 가질 수 있는 여러 질문에 답변</span>

**<span style="background-color:rgb(237,220,195);">개별 리뷰 (Individual review 또는 개별 준비)</span>**
- <span style="background-color:rgb(242,213,214);">작업 산출물 전체 혹은 부분 리뷰</span>
- <span style="background-color:rgb(242,213,214);">잠재 결함, 권고사항, 질문 기록</span>

**<span style="background-color:rgb(237,220,195);">이슈 논의 및 분석 (Issue communication and analysis)</span>**
- <span style="background-color:rgb(242,213,214);">식별한 잠재 결함 전달 (예: 리뷰 회의 중 전달)</span>
- <span style="background-color:rgb(242,213,214);">잠재 결함 분석 및 담당자 및 상태 할당</span>
- <span style="background-color:rgb(242,213,214);">품질 특성 평가 및 문서화</span>
- <span style="background-color:rgb(242,213,214);">종료 조건을 기준으로 리뷰 결과를 평가하여 리뷰 결과 결정 (예: 거부(reject), 주요 수정 필요, 약간의 수정 후 수락 등)</span>

**<span style="background-color:rgb(237,220,195);">수정 및 보고 (Fixing and reporting)</span>**
- <span style="background-color:rgb(242,213,214);">작업 산출물에 대한 수정을 요하는 잠재 결함에 대한 결함 보고서 작성</span>
- <span style="background-color:rgb(242,213,214);">리뷰한 작업 산출물에서 발견한 결함 수정 (일반적으로 저자가 수정)</span>
- <span style="background-color:rgb(242,213,214);">결함 정보를 적절한 사람이나 팀과 공유 (리뷰한 작업 산출물과 연관된 다른 작업 산출물이 있는 경우)</span>
- <span style="background-color:rgb(242,213,214);">필요한 경우 주석 작성자(comment originator)의 동의를 포함해 (공식적인 리뷰 유형인 경우) 업데이트 된 결함 상태 기록</span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">메트릭 수집</span> (공식적인 리뷰 유형인 경우)</span>
- <span style="background-color:rgb(242,213,214);">종료 조건의 충족여부 확인 (공식적인 리뷰 유형인 경우)</span>
- <span style="background-color:rgb(242,213,214);">종료 조건이 충족되면 해당 작업 산출물 인수</span>

작업 산출물 리뷰 결과는 리뷰 유형 및 공식성에 따라 다양하게 나타난다.

## 3.2.2 공식 리뷰에서의 역할과 책임 (Roles and responsibilities in a formal review)
{: .notice--success}

<span style="color:green">(K1) 공식 리뷰의 다양한 역할과 책임을 인식할 수 있다.</span>

일반적으로 <span style="background-color:rgb(207,228,207);">공식 리뷰에는 다음과 같은 역할이 포함</span>된다:

**<span style="background-color:rgb(237,220,195);">저자 (Author)</span>**
- <span style="background-color:rgb(242,213,214);">리뷰 대상 작업 산출물 작성</span>
- <span style="background-color:rgb(242,213,214);">리뷰 대상 작업 산출물 결함 수정 (필요한 경우)</span>

**<span style="background-color:rgb(237,220,195);">관리자 (Management)</span>**
- <span style="background-color:rgb(242,213,214);"><span style="color:red">리뷰 계획 담당</span></span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">리뷰 실행 결정</span></span>
- <span style="background-color:rgb(242,213,214);">인력, 예산, 시간 할당</span>
- <span style="background-color:rgb(242,213,214);">진행 비용 대비 효과 모니터링</span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">결과가 만족스럽지 않은 경우 제어 결정(control decisions) 실행</span></span>

**<span style="background-color:rgb(237,220,195);">촉진자 (Facilitator, 종종 중재자(moderator)로 부름)</span>**
- <span style="background-color:rgb(242,213,214);">리뷰 회의 진행 시 <span style="color:red">효과적 회의 진행 보장</span></span>
- <span style="background-color:rgb(242,213,214);">필요한 경우 다양한 관점들에 대한 중재</span>
- <span style="background-color:rgb(242,213,214);">많은 경우 <span style="color:red">리뷰의 성공 여부에 결정적인 역할</span>을 하는 사람</span>

**<span style="background-color:rgb(237,220,195);">리뷰 리더 (Review leader)</span>**
- <span style="background-color:rgb(242,213,214);">전반적으로 리뷰에 대한 책임을 지는 사람</span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">참여자를 결정하고 언제 어디서 진행할지 결정</span></span>

**<span style="background-color:rgb(237,220,195);">검토자 (Reviewers)</span>**
- <span style="background-color:rgb(242,213,214);">해당 주제에 대한 전문가, 프로젝트 참여 인원, 작업 산출물에 관심이 있는 이해관계자나 특정 기술 혹은 비즈니스 배경을 가진 사람 등</span>
- <span style="background-color:rgb(242,213,214);">리뷰 대상 작업 산출물의 잠재적 결함 식별</span>
- <span style="background-color:rgb(242,213,214);">다양한 관점을 대표할 수 있음 (예: 테스터, 개발자, 사용자, 운영자, 비즈니스 분석가, 사용성 전문가 등)</span>

**<span style="background-color:rgb(237,220,195);">서기 (Scribe, 또는 기록자 (Recorder))</span>**
- <span style="background-color:rgb(242,213,214);">개별 리뷰 활동에서 발견한 잠재 결함 수집</span>
- <span style="background-color:rgb(242,213,214);">리뷰 회의가 진행되는 경우 새로운 잠재 결함, 쟁점, 결정 사항 기록</span>

<u>리뷰 유형에 따라 한 사람이 두 개 이상의 역할을 수행할 수 있으며, 각 역할과 관련된 활동 역시 리뷰 유형에 따라 달라질 수 있다. 또한, 리뷰 프로세스를 지원하는 도구, 특히, 결함, 쟁점 및 의사 결정의 기록을 지원하는 도구로 인해 서기가 필요하지 않은 경우가 많다.</u><br>
ISO 표준(ISO/IEC 20246)에서 설명하고 있는 바와 같이 역할이 더 세분화되는 경우도 있다.

## 3.2.3 리뷰 유형 (Review Types)
{: .notice--success}

<span style="color:green">(K2) 서로 다른 리뷰 유형(비공식 리뷰, 워크쓰루, 기술 리뷰, 인스펙션)의 차이를 설명할 수 있다.</span>

리뷰를 다양한 목적으로 활용할 수 있지만, 주된 목적 중 하나는 결함 발견이다. <u>모든 리뷰 유형은 결함 발견에 도움</u>이 될 수 있으며, <u>프로젝트 요구사항, 가용 자원, 제품 유형과 리스크, 비즈니스 도메인, 조직의 문화 등에 따라 적절한 리뷰 유형을 선택</u>해야 한다.<br>
단일 작업 산출물은 여러 유형의 리뷰 대상이 될 수 있다. <u>하나 이상의 리뷰 유형이 사용된 경우에는 그 순서도 다양할 수 있다. 예를 들어, 비공식 리뷰는 작업 산출물이 기술 리뷰를 위해 준비되었는지 확인하기 위해 기술 리뷰 전에 수행될 수 있다</u>.<br>
<u>아래에 설명되어 있는 리뷰 유형은 동료 리뷰(peer reviews), 즉 동일한 작업의 수행 능력이 있는 동료가 수행할 수 있다</u>.<br>
리뷰에서 발견되는 결함 유형은 특히 리뷰 중인 작업 산출물에 따라 다르다 (각기 다른 작업 산출물의 리뷰에서 찾을 수 있는 결함의 예는 3.1.3 을, 공식 인스펙션에 대한 정보는 Gilb 1993 참조).<br>
리뷰는 다양한 특성에 따라 분류될 수 있다. 다음은 가장 일반적인 4가지 <span style="background-color:rgb(207,228,207);">리뷰 유형과 각각의 특성</span>을 나열한 것이다:

**<span style="background-color:rgb(237,220,195);">비공식 리뷰 (Informal review)<br>
(예: 버디 체크 (buddy check), 페어링 (pairing), 짝 리뷰 (pair review))</span>**
- <span style="background-color:rgb(242,213,214);">주요 목적: 잠재적 결함 발견</span>
- <span style="background-color:rgb(242,213,214);">기타 목적: 새로운 아이디어나 해결책 도출, 소소한 문제의 빠른 해결</span>
- <span style="background-color:rgb(242,213,214);">공식 (문서화된) 프로세스를 기반으로 하지 않음</span>
- <span style="background-color:rgb(242,213,214);">리뷰 회의를 진행하지 않을 수 있음</span>
- <span style="background-color:rgb(242,213,214);">저자의 동료 (버디체크) 또는 다른사람이 수행할 수 있음</span>
- <span style="background-color:rgb(242,213,214);">결과는 문서로 기록할 수 있음</span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">검토자에 따라 성과가 달라짐</span></span>
- <span style="background-color:rgb(242,213,214);">체크리스트 사용 여부는 상황에 맞게 판단</span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">애자일 개발에서 매우 일반적으로 사용됨</span></span>

**<span style="background-color:rgb(237,220,195);">워크쓰루 (Walkthrough)</span>**
- <span style="background-color:rgb(242,213,214);">주요 목적: 결함 발견, 소프트웨어 제품 개선, 다른 구현 방법 고려, <span style="color:red">표준이나 규정 준수 평가</span></span>
- <span style="background-color:rgb(242,213,214);">기타 목적: 다양한 기술이나 스타일에 대한 아이디어 교환, 참여자 교육, 합의 도출</span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">리뷰 회의 전 개별 준비는 필요에 따라 수행</span></span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">리뷰 회의는 일반적으로 작업 산출물의 저자가 주도</span></span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">서기 참여 필수</span></span>
- <span style="background-color:rgb(242,213,214);">체크리스트 사용 여부는 상황에 맞게 판단</span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">시나리오, 드라이 런(dry run), 시뮬레이션의 형태로 수행할 수 있음</span></span>
- <span style="background-color:rgb(242,213,214);">잠재 결함 로그와 리뷰 보고서 작성</span>
- <span style="background-color:rgb(242,213,214);">실무에서는 비공식적인 형식에서 매우 공식적인 형식까지 다양할 수 있음</span>

**<span style="background-color:rgb(237,220,195);">기술 리뷰 (Technical review)</span>**
- <span style="background-color:rgb(242,213,214);">주요 목적: 합의 도출, 잠재적 결함 발견</span>
- <span style="background-color:rgb(242,213,214);">기타 목적: 작업 산출물의 품질 평가 및 자신감 획득, 새로운 아이디어 도출, 저자가 미래의 작업 산출물을 개선하도록 지원하고 동기를 부여, 다른 구현 방법 고려</span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">검토자는 저자의 기술 동료이면서, 동일 분야 또는 다른 분야의 기술 전문가여야 함</span></span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">리뷰 회의 전 개별 준비 필요</span></span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">리뷰 회의는 선택 사항이며, 이상적으로는 훈련된 촉진자(일반적으로 저자가 아닌)가 주도</span></span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">서기는 반드시 있어야 하며, 이상적으로는 저자가 아닌 사람이 수행</span></span>
- <span style="background-color:rgb(242,213,214);">체크리스트 사용 여부는 상황에 맞게 판단</span>
- <span style="background-color:rgb(242,213,214);">잠재 결함 로그와 리뷰 보고서 작성</span>

**<span style="background-color:rgb(237,220,195);">인스펙션 (Inspection)</span>**
- <span style="background-color:rgb(242,213,214);">주요 목적: 잠재적 결함 발견, 작업 산출물의 품질 평가 및 자신감 획득, 저자 학습과 근본 원인 분석을 통한 유사 결함의 발생 예방</span>
- <span style="background-color:rgb(242,213,214);">기타 목적: 저자가 앞으로의 작업 산출물과 소프트웨어 개발 프로세스를 개선하고 합의를 이끌어 내도록 동기를 부여</span>
- <span style="background-color:rgb(242,213,214);">규칙 및 <span style="color:red">체크리스트</span>를 기반으로 공식 문서 산출물을 작성하는 정의된 프로세스를 수행</span>
- <span style="background-color:rgb(242,213,214);">3.2.2 절에서 필수(mandatory)로 지정한 바와 같이 <span style="color:red">명확하게 정의된 역할 참여</span>, 낭독자(리뷰 회의 중 작업 산출물을 종종 자신의 말로 의역하고 소리 내어 읽는 사람)의 참여 가능</span>
- <span style="background-color:rgb(242,213,214);">리뷰 회의 전 개별 준비 필요</span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">검토자는 저자의 동료 또는 작업 산출물과 연관된 분야의 전문가</span></span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">명시된 시작 및 종료 조건을 사용</span></span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">서기 참여 필수</span></span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">리뷰 회의는 훈련받은 촉진자(저자가 아닌 사람)가 주도</span></span>
- <span style="background-color:rgb(242,213,214);"><span style="color:red">저자는 리뷰 리더, 글을 읽는 사람 또는 서기가 될 수 없음</span></span>
- <span style="background-color:rgb(242,213,214);">잠재적인 결함 로그 및 리뷰 보고서 작성</span>
- <span style="background-color:rgb(242,213,214);">인스펙션 프로세스 포함 전체 소프트웨어 개발 프로세스를 개선하기 위해 <span style="color:red">메트릭을 수집하고 사용</span></span>

## 3.2.4 리뷰 기법 적용 (Applying Review Techniques)
{: .notice--success}

<span style="color:green">(K3) 작업 산출물에 리뷰 기법을 적용해 결함을 식별할 수 있다.</span>

<span style="color:blue">개별 리뷰(개별 준비) 활동 중에 결함을 발견하기 위해 사용할 수 있는 리뷰 기법에는 여러 가지가 있다. 이런 기법은 위에서 설명한 모든 리뷰 유형에서 사용할 수 있다</span>. 각 기법이 얼마나 효과적인지는 사용하는 리뷰 유형에 따라 달라질 수 있다. 여러 리뷰 유형에서 사용하는 개별 <span style="background-color:rgb(207,228,207);">리뷰 기법</span>들은 다음과 같다:

**<span style="background-color:rgb(237,220,195);">애드혹 (Ad hoc)</span>**
<span style="background-color:rgb(242,213,214);">애드혹 리뷰에서는 검토자에게 리뷰 수행 방법에 대한 안내가 거의 또는 전혀 제공되지 않는다. 검토자는 대부분의 경우 작업 산출물을 순차적으로 읽으면서 이슈를 식별하고 기록한다. 애드혹 리뷰는 특별한 준비 없이 일반적으로 사용되는 기법이다. 이 기법은 검토자의 능력에 크게 의존하며, 여러 검토자가 동일한 문제를 보고할 수 있다.</span>

**<span style="background-color:rgb(237,220,195);">체크리스트 기반 (Checklist based)</span>**
<span style="background-color:rgb(242,213,214);">체크리스트 기반 리뷰는 체계적인 기법으로, 검토자는 리뷰 시작 시점에 배포된(예를 들어, 촉진자에 의해) 체크리스트를 기반으로 이슈를 식별한다. 리뷰 체크리스트는 잠재 결함을 식별하기 위해 경험에서 도출한 일련의 질문으로 구성된다. 체크리스트는 리뷰 대상 작업 산출물 유형별로 작성해야 하며 이전 리뷰에서 누락된 이슈 유형을 다루기 위해 주기적으로 개선할 필요가 있다. 체크리스트 기반 기법의 주요 장점은 일반적인 결함 유형에 대한 체계적인 커버리지를 갖는다는 점이다. 개별 리뷰를 수행할 때 검토자는 체크리스트를 단순히 실행하는 것뿐만 아니라, <u>체크리스트로 식별할 수 없는 결함도 찾기 위해 특별히 주의를 기울여야만 한다</u>.</span>

**<span style="background-color:rgb(237,220,195);">시나리오 및 드라이 런 (Scenarios and dry runs)</span>**
<span style="background-color:rgb(242,213,214);">시나리오 기반 리뷰에서 검토자는 작업 산출물을 어떻게 검토할지에 대한 구조화된 지침을 제공받는다. 시나리오 기반 리뷰는 (작업 산출물이 유스케이스와 같은 적절한 형식으로 문서화된 경우) 작업 산출물의 예상되는 용도를 기반으로 작업 산출물에 대해 “드라이런”을 수행할 수 있도록 검토자를 지원한다. 이러한 시나리오는 검토자에게 단순한 체크리스트 항목보다 특정 결함 유형을 식별하는 방법에 대한 좀 더 나은 지침을 제공한다. <u>체크리스트 기반 리뷰와 마찬가지로, 다른 결함 유형(예: 누락된 기능)을 발견하기 위해 검토자는 기록된 시나리오에만 너무 얽매이지 않아야 한다</u>.</span>

**<span style="background-color:rgb(237,220,195);">관점 기반 (Perspective-based)</span>**
<span style="background-color:rgb(242,213,214);">관점 기반 읽기(perspective-based reading)는 역할 기반 리뷰와 마찬가지로 검토자가 개별 리뷰 중 다양한 이해관계자의 관점을 사용하게 된다. <span style="color:blue">일반적으로 사용되는 이해관계자 관점에는 최종 사용자, 영업, 설계자, 테스터, 운영자 등이 있다</span>. <u>서로 다른 이해관계자 관점을 사용하면, 검토자 간에 중복되는 이슈가 줄어들고 개별리뷰가 좀 더 깊이 있게 진행</u>된다.<br>
또한, 관점 기반 읽기에서는 검토자가 리뷰 대상 작업 산출물로부터 이해관계자의 관점을 기반으로 하는 산출물을 작성해야 한다. 예를 들어, 테스터가 필요한 모든 정보가 존재하는지 확인하기 위해 요구사항 명세에 대한 관점 기반 읽기를 수행하면서 <u>인수 테스트 초안을 작성을 시도할 수 있다</u>. 또한 <u>관점 기반 읽기에서는 체크리스트도 활용</u>한다.<br>
실증적인 연구에 의하면, <u>관점 기반 읽기가 요구사항 및 기술 작업 산출물에 대한 리뷰에 가장 효과적인 기법</u>이다. <u>주요 성공 요인은 리스크를 기반으로 다양한 이해관계자의 관점을 적절하게 포함시키고 평가하는 것</u>이다. 관점 기반 읽기에 대한 자세한 내용은 Shul 2000 을 참조하고, 다양한 리뷰 기법의 효과에 대해서는 Sauer 2000 을 참조한다.</span>

**<span style="background-color:rgb(237,220,195);">역할 기반 (Role-based)</span>**
<span style="background-color:rgb(242,213,214);">역할 기반 리뷰는 검토자가 작업 산출물을 개별 이해관계자 역할의 관점에서 평가하는 기법이다. <span style="color:blue">일반적인 역할에는 특정 최종 사용자 유형(경험 많은, 경험 적은, 노인, 아동 등)과 조직 내 특정 역할(사용자 관리자, 시스템 관리자, 성능 테스터 등)이 있다</span>. 역할이 비슷하기 때문에 같은 원칙이 관점 기반 읽기에도 적용된다.</span>

## 3.2.5 리뷰의 성공 요소 (Success Factors for Reviews)
{: .notice--success}

<span style="color:green">(K2) 리뷰 성공 요소를 설명할 수 있다.</span>

성공적인 리뷰를 위해서는 적절한 리뷰 유형과 기법을 고려해야 한다. 또한, 리뷰의 결과에 영향을 주는 여러 가지 다른 요인도 있다.

<span style="background-color:rgb(207,228,207);">조직 차원의 성공 요인</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">각 리뷰는 명확한 목적이 있어야 한다. 목적은 리뷰 계획 시 정의하며, 측정 가능한 종료 조건으로 사용된다</span>
- <span style="background-color:rgb(237,220,195);">목적을 달성하기에 적합하고, 소프트웨어 작업 산출물 및 참여자 유형 수준에 맞는 리뷰 유형을 적용해야 한다</span>
- <span style="background-color:rgb(237,220,195);">체크리스트 기반 및 역할 기반 리뷰와 같이 사용하는 모든 리뷰 기법은 리뷰 대상 작업 산출물의 결함을 효과적으로 식별하기에 적합해야 한다</span>
- <span style="background-color:rgb(237,220,195);"><u>사용하는 체크리스트는 주요 리스크 식별을 위해 작성해야 하며, 가장 최신의 정보를 반영</u>해야 한다</span>
- <span style="background-color:rgb(237,220,195);">규모가 큰 문서는 작은 단위로 작성하고 리뷰를 수행해 저자에게 결함에 대한 피드백을 조기에 그리고 빈번하게 제공함으로써 품질 관리를 수행한다</span>
- <span style="background-color:rgb(237,220,195);"><u>참여자는 충분한 준비 시간을 갖는다</u></span>
- <span style="background-color:rgb(237,220,195);">충분한 여유를 가지고 리뷰 일정을 수립한다</span>
- <span style="background-color:rgb(237,220,195);">경영진은 리뷰 프로세스를 지원한다 (예: 프로젝트 일정에 리뷰 활동을 위한 충분한 시간을 배정)</span>
- <span style="background-color:rgb(237,220,195);">리뷰는 기업의 품질 및 테스트 정책에 통합된다</span>

<span style="background-color:rgb(207,228,207);">사람과 관련된 성공 요인</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">리뷰 목적 달성을 위해 적절한 사람들이 참여한다 (예를 들어, 문서를 기반으로 작업을 시작해야 하는 서로 다른 기술 세트 또는 관점을 가진 사람들)</span>
- <span style="background-color:rgb(237,220,195);">테스터는 리뷰에 기여하는 중요한 검토자로 간주된다. 테스터는 작업 산출물의 학습을 통해 좀 더 효과적인 테스트를 준비하고 조기에 테스트 준비를 할 수 있게 된다</span>
- <span style="background-color:rgb(237,220,195);">참여자는 세부사항에 충분한 시간과 주의를 기울여야 한다</span>
- <span style="background-color:rgb(237,220,195);">작은 단위로 리뷰를 진행해 개별 리뷰나 리뷰 회의(개최된다면) 중에 검토자가 집중력을 잃지 않도록 해야 한다.</span>
- <span style="background-color:rgb(237,220,195);">식별된 결함은 승인하고 평가하고, 객관적으로 처리해야 한다</span>
- <span style="background-color:rgb(237,220,195);">리뷰 회의를 잘 관리해 참여자가 리뷰에 참여한 시간이 가치 있다고 인식하게 해야한다</span>
- <span style="background-color:rgb(237,220,195);">리뷰는 모든 참여자가 서로 신뢰하는 분위기에서 진행해야 한다. 리뷰 결과를 가지고 참여자들을 평가해서는 안 된다</span>
- <span style="background-color:rgb(237,220,195);">참여자는 지루함, 분노 또는 다른 참여자에 대한 적대감을 나타낼 수 있는 신체 언어 및 행동을 피해야 한다</span>
- <span style="background-color:rgb(237,220,195);">적절한 교육을 제공한다. 특히 인스펙션과 같은 공식적인 리뷰 유형에는 더 필요하다</span>
- <span style="background-color:rgb(237,220,195);">학습 및 프로세스 개선에 대한 조직 문화를 촉진해야한다</span>

성공적인 리뷰에 대한 자세한 내용은 Gilb 1993, Wiegers 2002, van Veenendaal 2004 를 참조한다.

# ● 용어
{: .notice .text-center}

<details>
<summary>Keywords</summary>
<div markdown="1">

- 애드혹 리뷰(ad hoc review):<br>
참조 : ISO 20246<br>
공식 프로세스 없이 독립된 검토자에 의해 비공식으로 실행되는 리뷰 기법

- 체크리스트 기반 리뷰(checklist-based review):<br>
참조 : ISO 20246<br>
질문 목록이나 확인해야 하는 특성을 기반으로 수행하는 리뷰 기법

- 동적 테스팅(dynamic testing): 컴포넌트나 시스템의 소프트웨어 실행을 기반으로 하는 테스팅

- 공식 리뷰(formal review):<br>
참조 : ISO 20246<br>
공식 산출물로 정의된 프로세스를 따르는 리뷰 유형

- 비공식 리뷰(informal review):<br>
참조 : ISO 20246<br>
공식(문서화된) 절차 없이 진행되는 리뷰의 유형

- 인스펙션(inspection):<br>
참조: ISO 20246<br>
작업 산출물의 이슈를 식별하기 위한 공식리뷰 유형. 리뷰 프로세스와 소프트웨어 개발 프로세스를 개선하는 데 필요한 정보를 제공

- 관점 기반 읽기(perspective-based reading):<br>
참조 : ISO 20246<br>
유의어 : 관점 기반 리뷰(perspective-based reviewing)<br>
검토자가 여러 관점에서 작업 산출물을 평가하는 리뷰 기법

- 리뷰(review):<br>
참조 : IEEE 1028<br>
이슈를 발견하고 개선 방법을 제공하기 위해 한 명 이상이 작업 산출물 또는 프로세스를 평가하는 정적 테스팅의 한 유형

- 역할 기반 리뷰(role-based review):<br>
참조 : ISO 20246<br>
리뷰어가 다른 이해관계자의 역할 관점에서 작업 산출물을 평가하는 리뷰 기법

- 시나리오 기반 리뷰(scenario-based review):<br>
참조 : ISO 20246<br>
특정 시나리오를 지원하는 작업 산출물의 능력을 판단해가면서 진행하는 리뷰 기법

- 정적 분석(static analysis):<br>
참조 : ISO 24765<br>
형식이나 구조, 내용, 문서를 기반으로, 컴포넌트나 시스템을 실행하지 않으면서 평가하는 프로세스

- 정적 테스팅(static testing): 코드를 실행하지 않은 상태로 작업 산출물을 테스팅하는 것

- 기술적 리뷰(technical review):<br>
참조 : Gilb and Graham, IEEE 1028<br>
기술 자격을 갖춘 인원으로 구성된 팀에 의해 수행되는 공식적인 리뷰의 한 유형. 작업 산출물이 의도한 용도에 적합한지 적합성을 확인하고 명세 및 표준과의 불일치를 식별

- 워크스루(walkthrough):<br>
참조 : ISO 20246<br>
연관 항목 : 동료 검토(peer review)<br>
유의어 : 구조적 워크스루(structured walkthrough)<br>
작성자가 작업 산출물에 대한 리뷰를 주도하고, 참가자들은 발생 가능 이슈에 대한 질문과 의견을 제시하는 리뷰 유형

- 감사(audit):<br>
참조 : IEEE 1028<br>
명세, 표준, 계약상의 합의사항, 그 밖의 기준에 대한 준수 여부를 평가하고자 제3자가 수행하는 작업 산출물, 프로세스 또는 프로세스 집합에 대한 독립적인 검사

- 번다운 차트(burndown chart):<br>
이터레이션(iteration)의 시간 대비 잔여 작업을 나타내는 차트. 공개적으로 전시되며, 이터레이션 작업이 완료되어가는 상태와 추세를 보여준다. X 축은 보통 스프린트 일수를 나타내고, Y 축은 남은 작업을(일반적으로 추정된 엔지니어링 시간이나 스토리 포인트에 의해) 나타냄

- 중재자(moderator):<br>
연관 항목 : 조력자(facilitator)<br>
유의어 : 인스펙션 리더(inspection leader)<br>
사용성 테스트 세션을 수행하는 중립적인 사람

- 리뷰어(reviewer):<br>
참조 : ISO 20246<br>
유의어 : 확인자(checker), 검사자(inspector)<br>
작업 산출물의 이슈를 식별하는 리뷰 작업 참여자

- 서기(scribe):<br>
참조 : IEEE 1028<br>
유의어 : 기록자(recorder)<br>
리뷰 회의 중에 정보를 기록하는 사람

</div>
</details>

# ● 샘플문제
{: .notice--danger .text-center}

A - Q14. 다음 중 공식 리뷰의 역할 담당자들로 구성된 것은?
- a. 개발자, 중재자, 리뷰 리더, 리뷰어, 테스터
- b. 작성자, 중재자, 관리자, 리뷰어, 개발자
- c. 작성자, 관리자, 리뷰 리더, 리뷰어, 설계자
- d. 작성자, 중재자, 리뷰 리더, 리뷰어, 서기

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-3.2.2 (K1) 공식 리뷰의 다양한 역할과 책임을 인식할 수 있다.
- a. 오답- 테스터와 개발자는 리뷰 활동 담당자가 아니다.
- b. 오답- 개발자는 리뷰 활동 담당자가 아니다.
- c. 오답- 설계자는 리뷰 활동 담당자가 아니다.
- d. 정답- 오답의 설명 참조

</div>
</details>

---

A - Q15. 다음 중 공식 리뷰 계획 중에 수행하는 활동은 무엇인가?
- a. 리뷰의 유효성 평가를 위한 메트릭 수집
- b. 참가자가 문의할 수 있는 질문에 답변
- c. 리뷰를 위한 시작 조건(entry criteria)의 정의 및 시작 조건의 충족여부 확인
- d. 종료 조건(exit criteria)에 대한 리뷰 결과 평가

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-3.2.1 (K2) 작업 산출물 리뷰 프로세스 활동을 요약할 수 있다.
- a. 오답- ‘메트릭 수집’ 은 “수정 및 보고”의 주요 활동이다.
- b. 오답- ‘여러 질문에 대한 답변’은 “리뷰 착수”의 주요 활동이다.
- c. 정답- 실러버스 3.2.1 참조: 시작 조건(entry criteria)을 확인하는 것은 공식 리뷰의 계획에서 이루어진다.
- d. 오답- 종료 조건에 대한 리뷰결과의 평가는 “이슈 논의 및 분석”의 주요 활동이다.

</div>
</details>

---

A - Q16. 다음 중 규정과 체크리스트에 기반한 공식 프로세스를 따라야 하는 리뷰 수행 시 선택할 수 있는 리뷰 유형으로 가장 적합한 것은?
- a. 비공식 리뷰 (Informal Review)
- b. 기술적 리뷰 (Technical Review)
- c. 인스펙션 (Inspection)
- d. 워크쓰루 (Walkthrough)

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-3.2.3 (K2) 서로 다른 리뷰 유형(비공식 리뷰, 워크쓰루, 기술 리뷰, 인스펙션)의 차이를 설명할 수 있다.
- a. 오답- 비공식 리뷰는 공식 프로세스를 따르지 않는다.
- b. 오답- 기술적 리뷰에서 체크리스트는 선택적으로 사용한다.
- c. 정답- 인스펙션은 규정과 체크리스트에 기반한 공식 프로세스이다.
- d. 오답- 워크쓰루에서 공식 프로세스를 따라야 한다는 명시적인 요구는 없다.

</div>
</details>

---

A - Q17. 다음 중 정적 테스팅에 대해 가장 잘 설명한 것은?
- a. 결함을 발견하고 제거하는 경제적인 방법이다.
- b. 동적 테스팅의 부담을 줄여준다.
- c. 수명주기 초기에 런타임 문제를 찾을 수 있게 해준다.
- d. 안전 최우선(safety-critical) 시스템을 테스트할 때는 동적 테스팅으로 결함을 더 잘 찾아내기 때문에 정적 테스팅은 덜 중요하다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-3.1.2 (K2) 정적 테스팅의 가치를 예제를 통해 설명할 수 있다.
- a. 정답- 개발 수명주기 후반에 결함을 발견하는 것보다 초기에 결함을 발견해 제거하는 것이 경제적이다.
- b. 오답- 동적 테스팅은 다른 유형의 결함을 찾아내므로 여전히 쉽지 않다.
- c. 오답- 동적 테스팅에 대한 설명이다.
- d. 오답- 정적 분석은 안전 최우선(safety-critical) 컴퓨터 시스템에서 중요한 활동이다.

</div>
</details>

---

A - Q18. 당신은 사내 문서 제작관리 절차에 대한 작업물을 검토하는 리뷰에 참여할 예정이다. 이 절차 문서의 목표는 절차와 관련한 여러 역할 간의 업무 분담을 모든 관련자들이 명확하게 이해할 수 있는 방식으로 보여주는 것이다.<br>
당신은 체크리스트 기반 리뷰에도 참여할 것이며, 아래의 내용을 가지는 체크리스트가 사용될 예정이다:
- i. 역할을 수행하는 사람이 각 역할에 대해 명확하게 파악하고 있는가?
- ii. 각 활동의 시작 조건(entry criteria)이 명확하게 정의되어 있는가?
- iii. 각 활동의 종료 조건(exit criteria)이 명확하게 정의되어 있는가?
- iv. 각 활동을 지원하는 역할과 활동 범위가 명확하게 정의되어 있는가?

다음은 위 체크리스트를 사용해서 리뷰해야 할 사내 문서관리 지침에서 발췌한 내용이다:<br>
"고객 문서의 완전성(completeness)과 정확성(correctness)에 대한 검증이 끝나면 소프트웨어 아키텍트는 시스템 사양서를 작성한다. 시스템 사양서가 작성되고 나면 아키텍트는 테스터와 검증수행원(verifiers)을 리뷰에 초대한다. 검토자의 자격 기준은 체크리스트로 제공된다. 초대된 모든 검토자는 (필요할 경우) 리뷰 의견을 작성하며, 공식 리뷰 완료 의견으로 리뷰를 종료한다.<br>
다음 중 당신이 진행해야 하는 리뷰에 대해 맞게 설명한 것은?
- a. 리뷰에 검토자를 초대하기 위해 충족해야 하는 조건이 명확하지 않음으로 항목 ii를 위반하고 있다.
- b. 테스터와 검증수행원 외에 유효성 검사자(validator)를 초대해야 함을 깨달았다. 하지만 이 항목은 체크리스트에 포함돼 있지 않아서 거기에 대한 의견은 작성하지 않는다.
- c. 리뷰 종료 조건이 명확하지 않기 때문에 체크리스트 항목 iii를 위반하고 있다.
- d. 리뷰에 참여하는 검토자의 자격 기준에 대한 체크리스트를 누가 제공하는지 명확하지 않음으로 항목 i를 위반하고 있다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-3.2.4 (K3) 작업 산출물에 리뷰 기법을 적용해 결함을 식별할 수 있다.
- a. 오답- 소프트웨어 아키텍트가 시스템 사양서를 완료하고 나서 초대한다는 것을 명시하고 있다.
- b. 오답- '체크리스트 기반'의 마지막 문장을 보면 체크리스트로 식별할 수 없는 결함도 찾아야 함이 언급돼 있다.
- c. 오답- 작성돼 있다. 모든 검토자는 리뷰 완료 의견을 작성해야 한다.
- d. 정답- 체크리스트가 제공된다는 것이 설명되어 있지만, 누가 제공하는지에 대한 설명은 없다.

</div>
</details>

---

B - Q14. 다음 중 정적 테스팅의 가치를 가장 잘 설명한 것은?
- A. 리뷰를 도입함으로써, 명세의 품질이 좋아지고 개발 및 테스팅에 필요한 시간이 증가했다.
- B. 정적 테스팅을 사용한다는 것은 수명주기 후반에 결함을 찾아내기가 쉽기 때문에 더 나은 제어와 경제적인 결함 관리를 할 수 있다는 것을 의미한다.
- C. 정적 분석을 사용해 누락된 요구사항을 줄이고 테스터와 개발자 간 의사소통이 향상되었다.
- D. 정적 분석을 사용한 이후로 동적 테스팅만 수행했을 때는 발견하지 못했던 코딩 결함을 찾을 수 있었다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-3.1.2 (K2) 정적 테스팅의 가치를 예제를 통해 설명할 수 있다.
- A. 오답- 리뷰로 명세의 품질은 좋아지지만 개발과 테스팅에 필요한 시간은 줄어든다.
- B. 오답- 결함 찾아내기는 일반적으로 수명주기 초기에 더 쉽게 할 수 있다.
- C. 오답- 누락된 요구사항을 줄이고 테스터와 개발자 간 의사소통을 향상시키는 것은 리뷰를 통해 가능하며 정적 분석으로 하기는 어렵다.
- D. 정답- 정적 분석의 이점이다.

</div>
</details>

---

B - Q15. 공식 리뷰에서 체크리스트 사용에 대한 다음 설명 중 올바른 것은?
- A. 리뷰 계획에서 리뷰어는 해당 리뷰에 필요한 체크리스트를 만든다.
- B. 논의 및 분석에서 리뷰어는 제공된 체크리스트에 검토 의견을 작성한다.
- C. 리뷰 회의에서 리뷰어는 제공된 체크리스트를 기반으로 결함 보고서를 작성한다.
- D. 시작 미팅에서 리뷰어는 리뷰에 필요한 체크리스트를 제공받는다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-3.2.1 (K2) 작업 산출물 리뷰 프로세스 활동을 요약할 수 있다.
- A. 오답- 계획에서 체크리스트의 사용 여부가 결정된다. 체크리스트의 준비는 계획 중에 수행되는 활동이 아니다. 또한 리뷰어는 계획에 관여하지 않으며 체크리스트 작성에 대한 책임도 없다.
- B. 오답- 이슈 논의 및 분석 단계에서는 개별 리뷰에서 확인된 잠재적 결함이 전달된다. 리뷰어의 체크리스트 작성은 개별 리뷰 중에 이미 이루어진다.
- C. 오답- 리뷰 회의(이슈 논의 및 분석)에서 리뷰어는 개별 리뷰 중에 식별한 산출물의 잠재 결함을 전달한다. 결함 보고서는 수정 및 보고 활동에서만 작성된다.
- D. 정답- 리뷰 착수("시작 미팅")에서는 작업 산출물 및 체크리스트와 같은 기타 자료가 배포된다.

</div>
</details>

---

B - Q16. 다음 중 공식 리뷰의 역할과 책임을 바르게 연결한 것은?
- A. 관리자 - 리뷰 수행 여부를 결정한다.
- B. 리뷰 리더 - 리뷰 회의가 효과적으로 진행되도록 한다.
- C. 서기 - 리뷰 후 작업 산출물의 결함을 수정한다.
- D. 중재자 - 비용 효율성을 지속적으로 모니터링한다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-3.2.2 (K1) 공식 리뷰의 다양한 역할과 책임을 인식할 수 있다.
- A. 정답- 관리자(경영진)가 검토 수행을 결정한다.
- B. 오답- 리뷰 회의가 효과적으로 진행되도록 하는 사람은 리뷰 리더가 아니라 중재자이다.
- C. 오답- 리뷰 후 작업산출물의 수정은 작성자가 한다.
- D. 오답- 관리자가 비용 효율성을 지속적으로 모니터링한다.

</div>
</details>

---

B - Q17. 당신의 부서에서 다음과 같이 리뷰를 하고 있다:
- 서기 역할을 하는 사람이 있다.
- 리뷰 목적은 잠재적 결함을 찾는 것이다.
- 리뷰 미팅은 저자가 주도한다.
- 리뷰어들은 개별 리뷰를 통해 잠재 결함을 발견한다.
- 리뷰 보고서를 작성한다.

위의 내용으로 볼 때 다음 중 어떤 유형의 리뷰를 수행한 것인가?
- A. 비공식 리뷰
- B. 워크쓰루
- C. 기술리뷰
- D. 인스펙션

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-3.2.3 (K2) 서로 다른 리뷰 유형(비공식 리뷰, 워크쓰루, 기술 리뷰, 인스펙션)의 차이를 설명할 수 있다.<br>
리뷰 내용과 실러버스 3.2.3 에 따르면:
- 서기 역할을 하는 사람이 있다 - 워크쓰루, 기술 리뷰, 인스펙션에 해당하는 내용이므로 비공식 리뷰는 아니다.
- 리뷰 목적은 잠재적 결함을 찾는 것이다 - 잠재적 결함을 찾는 것은 모든 리뷰 유형의 목적이다.
- 리뷰 미팅은 저자가 주도한다 - 인스펙션에서는 저자가 주도하지 않으며 테크니컬 리뷰에서도 보통 저자가 주도하지는 않는다. 하지만 워크쓰루나 비공식 리뷰에서는 가능하다.
- 리뷰어들은 개별 리뷰를 통해 잠재 결함을 발견한다 - 모든 리뷰 유형에 개별 리뷰가 포함되어 있다(비공식 리뷰도 마찬가지다).
- 리뷰 보고서를 작성한다 - 모든 유형의 리뷰에서 리뷰 보고서를 작성할 수 있다. 비공식 리뷰에서는 거의 보고서를 작성하지 않는다.

따라서, B 가 정답이다

</div>
</details>

---

B - Q18. 당신은 도서관 시스템 요구사항 문서에서 발췌한 다음 내용에 대해 체크리스트 기반 리뷰에 참여하기로 했다:

도서관 사서가 할 수 있는 일:
- 1, 신규 대여회원 등록
- 2, 대여회원이 반납한 책 처리
- 3, 대여회원의 연체료 수령
- 4, ISBN, 저자, 책 제목으로 시스템에 신규 도서 추가
- 5, 시스템에서 도서 삭제
- 6, 시스템은 5초 이내로 응답해야 함

대여회원이 할 수 있는 일:
- 7, 1회에 3권까지 도서 대여
- 8, 대여/반납한 도서 이력 보기
- 9, 3주 이내로 반납하지 못한 도서에 대해 연체료 납부
- 10, 시스템은 3 초 이내로 응답해야 함
- 11, 최대 4주까지 무료로 도서 대여
- 12, (도서가 대여 중인 경우) 도서 예약

모든 사용자(사서 및 대여회원)가 할 수 있는 일:
- 13, ISBN, 저자, 책 제목으로 도서 검색
- 14, 시스템 카탈로그 둘러 보기
- 15, 시스템은 사용자 요청에 3초 이내로 응답해야 함
- 16, 사용자 인터페이스는 사용이 쉬어야 함

당신은 개별 요구사항 간 일관성에 문제가 없는지(예: 요구사항 간 충돌) 체크리스트에 기반해 요구사항을 리뷰하기로 했다.<br>
다음 중 요구사항 간 일관성이 떨어지는 항목끼리 맞게 묶은 것은?
- A. 6-10, 6-15, 7-12
- B. 6-15, 9-11
- C. 6-10, 6-15, 9-11
- D. 6-15, 7-12

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-3.2.4 (K3) 작업 산출물에 리뷰 기법을 적용해 결함을 식별할 수 있다.<br>
각각의 쌍을 일관성의 측면에서 살펴보자:
- 6-10 - 사서는 5초 이내로 시스템 응답을 받아야 하고, 대여회원은 3초 이내로 응답 받아야 한다는 사실의 일관성에는 문제가 없다.
- 6-15 - 사서는 5초 이내로 시스템 응답을 받아야하는 반면에, 모든 사용자는 3초 이내로 응답을 받아야 한다는 것은 일관성이 없다.
- 7-12 - 대여회원은 1회에 최대 3권까지 대여 가능하다는 것과 대여 중인 도서를 예약할 수 있는 것 사이에는 일관성에 문제가 없다.
- 9-11 - 대여회원이 3주 내로 도서를 반납하지 않으면 벌금을 내는 것과 4주까지 무료로 대출 가능하다는 요구사항은 일관성이 없다(유효 대여 기간에 차이가 있다).

따라서, 6번과 15번, 9번과 11번 요구사항은 서로 모순인 요구사항이므로 정답은 B이다.

</div>
</details>

---

C - Q14. 공식적 리뷰에서 인스펙션 회의를 운영하는 참가자는 누구인가?
- a. 촉진자 (Facilitator)
- b. 프로그래머 (Programmer)
- c. 작성자 (Author)
- d. 프로젝트 관리자 (Project manager)

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-3.2.2, K1
- a. 정답- 촉진자 또는 중재자가 리뷰 회의를 운영한다.
- b. 오답- 프로그래머는 공식 리뷰 참가자의 역할명이 아니다.
- c. 오답- 촉진자 또는 중재자가 리뷰 회의를 운영한다.
- d. 오답- 촉진자 또는 중재자가 리뷰 회의를 운영한다.

</div>
</details>

---

C - Q15. 당신은 제품 담당자 및 개발자와의 회의를 준비하기 위해 제품 백로그에 있는 사용자 스토리를 읽으면서 잠재적인 결함을 표시하고 있다.<br>
다음 중 이 활동을 맞게 설명하는 것은?
- a. 정적 테스트는 테스트 대상을 실행해야 하므로 이 활동은 정적 테스트가 아니다.
- b. 정적 테스트는 항상 도구로 수행하기 때문에 이 활동은 정적 테스트가 아니다.
- c. 동적 테스팅에서 결함을 더 저렴하게 식별할 수 있기 때문에 이 활동은 정적 테스트이다.
- d. 정적 테스트는 테스트 대상을 실행하지 않기 때문에 이 활동은 정적 테스트이다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-3.1.3, K2
- a. 오답- 정적 테스팅은 테스트 대상을 실행하지 않는다.
- b. 오답- 몇몇의 정적 테스팅에 도구를 사용하는 경우가 있는데 특히 정적 분석같은 경우가 그렇다. 그러나 리뷰(여기에 서술된 활동)는 도구 사용을 필요로 하지 않는다.
- c. 오답- 이 문제에 설명된 리뷰는 정적 테스트의 일부이지만, 정적 테스트에서 결함을 식별하는 비용은 일반적으로 동적 테스팅에서 결함을 식별하는 비용보다 저렴하다.
- d. 정답- 정적 테스팅은 테스트 대상을 실행하지 않는다.

</div>
</details>

---

C - Q16. 집중 초과근무 기간 동안, 애초 계획에 없던 기술 리뷰를 일주일 후에 수행한다고 발표하고 시스템 구조 문서를 여러 프로젝트 참가자에게 전송했다.<br>
이러한 정보만을 고려했을 때, 성공적인 리뷰를 위해 빠뜨린 요소는 무엇인가?
- a. 적합한 리뷰 유형
- b. 준비에 충분한 시간 할당
- c. 작성자를 평가하기 위한 충분한 메트릭
- d. 잘 관리된 리뷰 회의

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-3.2.5, K2
- a. 오답- 기술 리뷰는 시스템 아키텍처 같은 기술 문서에 적합하다.
- b. 정답- 준비를 위한 적절한 시간이 중요하지만, 많은 사람들이 초과 근무를 하고 있으며 일련의 새로운 작업을 할 수 있도록 조정이 이뤄지지 않고 있다.
- c. 오답- 참가자를 평가하기 위해 리뷰 메트릭을 수집하는 것은 신뢰를 무너뜨리기 때문에 성공이 아닌 실패 요인이다.
- d. 오답- 잘 관리된 리뷰 회의가 중요하지만 주어진 정보만으로는 리뷰회의가 잘 관리되지 않았다는 근거를 찾을 수 없다.

</div>
</details>

---

C - Q17. 애자일팀에서 테스터로 일하는 당신은 제품 담당자 및 개발자와 함께 각 반복주기를 시작하면서 24개의 사용자 스토리 개선 세션에 참가하고 있다. 사용자 스토리 결함을 찾는 데 점점 더 효과적인 리뷰가 진행되고, 제품 담당자가 결함을 수정하는 데 능숙해지면서 당신과 팀은 번다운 차트에 나타난 것처럼 팀의 일 진행 속도가 빨라지기 시작했다는 것을 알게 되었다.<br>
다음 중 팀의 향상된 일 진행속도에 가장 직접적으로 영향을 주는 정적 테스팅의 이점인 것은?
- a. 전체 품질 비용의 증가
- b. 테스팅 비용 감소
- c. 개발 생산성 증가
- d. 전체 품질 비용의 감소

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-3.1.2, K2
- a. 오답- 리뷰는 전체 품질 비용을 높이는 게 아니라 낮춰준다.
- b. 오답- 이를 정적 테스팅의 이점으로 설명하지만 속도(velocity) 증가는 테스팅뿐 아니라 전반적인 개발 생산성이 향상됐다는 신호이므로 이는 부분적으로만 적용된다.
- c. 정답- 속도는 애자일 개발에서 생산성을 측정하는 하나의 방법이다.
- d. 오답- 여기서 언급한 이점은 개발팀의 전반적인 생산성 향상과 관련이 있다.

</div>
</details>

---

C - Q18. 애자일 방법론을 사용하는 비디오 게임 개발 프로젝트에 참여하고 있다. 이 게임은 그리스 신화와 역사를 배경으로 하며, 플레이어는 그리스와 트로이 간 전투 등과 같은 시나리오에서 중요한 역할을 할 수 있다. 다음은 사용자 스토리와 관련된 인수 조건이다:<br>
플레이어는,
- 마이다스의 막대(새로운 마법 도구)를 획득하려고 한다.
- 이 도구로 물건이나 다른 플레이어를 금으로 바꿀 수 있다.
- AC1: 막대는 이것을 잡고 있는 플레이어가 사이즈에 상관없이 터치 가능한 모든 대상 또는 플레이어를 건드렸을 때 작동해야 한다.
- AC2: 막대를 잡고 있는 플레이어는 금으로 변하지 않는다.
- AC3: 막대에 닿은 물건이나 플레이어는 1밀리초 내로 금으로 변한다.
- AC4: 막대는 O.W.RoM 프로토타입에 표시된 것처럼 나타난다.
- AC5: 변환은 막대와의 접촉점에서 시작하여 1밀리초 당 1미터의 속도로 움직인다.

당신은 이 사용자 스토리의 체크리스트 기반 리뷰에 참가하고 있다.<br>
이 사용자 스토리와 연관된 인수 기준은 이러한 산출물 유형의 정적 테스트로 식별할 수 있는 일반적인 결함 중 무엇을 포함하고 있는가?
- a. 표준과의 편차 (Deviation from standards)
- b. 모순 (Contradiction)
- c. 보안 취약성 (Security vulnerability)
- d. 커버리지 차이 (Coverage gaps)

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-3.2.4, K3
- a. 오답- 표준과 차이가 나는 것은 일반적으로 결함이지만 사용자 스토리 작성 시에 적용 필수인 표준은 없다.
- b. 정답- 모순은 일반적인 요구사항 결함의 하나이다. AC3과 AC5는 막대로 만진 지점에서 반경 1m 내의 물체를 만지면 충돌한다. AC1은 접촉할 물체의 크기를 제한하지 않기 때문이다.
- c. 오답- 보안 취약성을 일반적인 결함이지만 이 사용자 스토리에는 보안과 관련된 내용이 없다.
- d. 오답- 인수 조건에 테스트를 누락하는 것을 포함하여 테스트 커버리지 차이는 일반적인 결함이지만, 어떤 테스트를 수행했고 어떤 테스트를 수행하지 않았는지에 대한 정보는 주어지지 않았다.

</div>
</details>

# ● 자료참고
{: .notice--info .text-center}

[실러버스 본문](http://www.kstqb.org/board_skin/board_view.asp?idx=426&page=1&bbs_code=4&key=0&word=&etc=ISTQB){: .btn .btn--info}
[실러버스 용어](http://www.kstqb.org/board_skin/board_view.asp?idx=342&page=2&bbs_code=4&key=0&word=&etc=ISTQB){: .btn .btn--info}
[샘플문제](http://www.kstqb.org/board_skin/board_view.asp?idx=433&page=2&bbs_code=5&key=0&word=&etc=){: .btn .btn--info}