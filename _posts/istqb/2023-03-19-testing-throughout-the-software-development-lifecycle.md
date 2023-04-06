---
title: "[Foundation Level] 제 2장. 소프트웨어 개발 수명주기와 테스팅"
excerpt: "Foundation Level Chapter.2 Testing Throughout the Software Development Lifecycle"
categories: istqb
tag: [ISTQB, Foundation Level]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# 2.1 소프트웨어 개발 수명주기 모델 Software Development Lifecycle Models
{: .notice--warning .text-center}

소프트웨어 개발 수명주기 모델은 소프트웨어 개발 프로젝트의 각 단계에서 이루어지는 활동 유형과 이런 활동이 서로 어떻게 논리적 또 순차적으로 연결되는지 보여준다. 여러 가지 소프트웨어 개발 수명주기 모델이 있으며, 각각 다른 테스팅 접근법을 요구한다.

## 2.1.1 소프트웨어 개발과 소프트웨어 테스팅 (Software Development and Software Testing)
{: .notice--success}

<span style="color:green">(K2) 소프트웨어 개발 수명주기에서의 소프트웨어 개발 활동과 테스트 활동의 관계를 설명할 수 있다.</span>

필요한 테스트 활동을 수행할 수 있도록 일반적으로 많이 사용되는 소프트웨어 개발 수명주기 모델을 잘 이해하는 것은 테스터의 중요한 역할 중 하나이다.<br>
<span style="background-color:rgb(207,228,207);">모든 소프트웨어 개발 수명주기 모델에 적용하기 좋은 테스팅의 특성</span>을 들면 다음과 같다:
- <span style="background-color:rgb(237,220,195);">모든 개발 활동은 그에 상응하는 테스트 활동이 있다.</span>
- <span style="background-color:rgb(237,220,195);">각 테스트 레벨은 그 레벨에 맞는 구체적인 목적을 가진다.</span>
- <span style="background-color:rgb(237,220,195);">주어진 테스트 레벨에 맞는 테스트 분석과 설계는 상응하는 개발 활동이 이루어지고 있는 동안 시작해야 한다.</span>
- <span style="background-color:rgb(237,220,195);">테스터가 요구사항과 설계의 정의와 개선을 위한 대화에 참여하고, 작업 산출물(예: 요구사항, 설계, 사용자 스토리 등)의 초안이 나오는 즉시 리뷰에 참여한다.</span>

<span style="background-color:rgb(237,220,195);">어떤 소프트웨어 개발 수명주기 모델을 선택하더라도 테스팅을 초기에 시작하면 시간과 비용을 절약할 수 있다는 테스트 원리에 따라, 테스트 활동은 수명주기 초반에 시작해야 한다.</span><br>
이 실러버스에서는 대표적인 소프트웨어 <span style="background-color:rgb(207,228,207);">개발 수명주기 모델</span>을 아래와 같이 분류하고 있다:
- <span style="background-color:rgb(237,220,195);">순차적(sequential) 개발 모델</span>
- <span style="background-color:rgb(237,220,195);">반복적 점진적(iterative and incremental) 개발 모델</span>

<span style="background-color:rgb(207,228,207);">순차적 개발 모델</span>에서는 소프트웨어 <span style="background-color:rgb(237,220,195);">개발 프로세스를 1 차원적 선형(linear)의 순차적 활동으로 설명</span>한다. 즉, <span style="background-color:rgb(237,220,195);">개발 프로세스의 모든 단계는 이전 단계가 완료될 때 시작</span>돼야 한다. 이론적으로는 각 단계가 서로 중첩하지 않지만, 실제로는 다음 단계에서 빨리 피드백을 받는 것이 유익하다.<br>
<span style="background-color:rgb(207,228,207);">폭포수 모델(Waterfall model)</span>에서는, <span style="background-color:rgb(237,220,195);">개발 활동(예: 요구사항 분석, 설계, 코딩, 테스팅)이 순차적</span>으로 이루어진다. 이 모델에서의 <span style="background-color:rgb(237,220,195);">테스트 활동은 모든 개발 활동을 완료한 후</span>에 이루어진다.<br>
폭포수 모델과는 다르게, <span style="background-color:rgb(207,228,207);">V-모델</span>은 <span style="background-color:rgb(237,220,195);">테스팅을 초기에 시작하면 좋다는 원리를 토대로 테스트 프로세스를 전반적인 개발 프로세스에 통합</span>한다. 또한, V-모델은 대응하는 <span style="background-color:rgb(237,220,195);">각 개발 단계에 테스트 레벨를 부여함으로써 조기 테스팅을 좀 더 적극적으로 구현</span>하고 있다 (테스트 레벨에 관한 설명은 2.2절 참조). 이 모델에서는 <span style="background-color:rgb(237,220,195);">각 테스트 레벨의 테스트 실행이 순차적으로 이루어지도록 하고 있지만 경우에 따라서는 중첩</span>되기도 한다.<br>
<span style="background-color:rgb(207,228,207);">순차적 개발 모델</span>에서는 <span style="background-color:rgb(237,220,195);">완성된 기능 세트를 포함한 소프트웨어를 배포할 수 있지만, 일반적으로 이해관계자와 사용자에게 배포하기까지 몇 개월 또는 몇 년이 걸린다.</span><br>

<span style="background-color:rgb(207,228,207);">점진적 개발</span>에서는 <span style="background-color:rgb(237,220,195);">요구사항 정의, 시스템의 설계, 구축, 테스팅을 조각으로 나눠서 진행</span>한다. 따라서, 소프트웨어 기능은 점진적으로 늘어나게 된다. 이런 <span style="background-color:rgb(237,220,195);">기능 증분(feature increments)의 크기는 다양하게 설정</span>할 수 있다. 일부 방법론에서는 증분을 크게 설정하며 다른 방법론에서는 작게 설정하기도 한다. 기능 증분은 사용자 인터페이스 화면이나 신규 문의 옵션에 생기는 변경 하나만큼 작을 수도 있다.

<span style="background-color:rgb(207,228,207);">반복적 개발</span>은 <span style="background-color:rgb(237,220,195);">기능 집합을 종종 고정된 기간의 일련의 주기 안에서 같이 명시, 설계, 구축, 테스트할 때 발생</span>한다. <span style="background-color:rgb(237,220,195);">반복주기에는 전체 프로젝트 범위에 대한 변경이나 기존 반복주기 동안 개발한 기능에 대한 수정이 포함될 수 있다.</span> <span style="background-color:rgb(237,220,195);">각 반복주기에서는 전체 기능 세트 중 일부의 기능을 하는 소프트웨어를 만들어내고 소프트웨어의 기능은 반복주기 횟수가 늘어남에 따라 점차 늘어나게 되고, 완성된 소프트웨어가 배포되거나 개발이 중단될 때까지 진행</span>된다.<br>
대표적인 예로는:
- **<span style="background-color:rgb(237,220,195);">래셔널 통합 프로세스(Rational Unified Process)</span>**: <span style="background-color:rgb(242,213,214);">각 반복주기가 상당히 긴</span> 경우가 많으며(예: 2, 3 개월), 따라서 <span style="background-color:rgb(242,213,214);">기능 증분도 상당히 큼</span> (예: 2, 3 개의 연관된 기능 그룹)
- **<span style="background-color:rgb(237,220,195);">스크럼(Scrum)</span>**: <span style="background-color:rgb(242,213,214);">각 반복주기가 짧은</span> 성향을 가지며(예: 몇 시간, 며칠, 또는 몇 주) 따라서 <span style="background-color:rgb(242,213,214);">기능 증분도 작음</span> (예: 몇 가지 개선 사항 혹은 2, 3 개의 신규 기능)
- **<span style="background-color:rgb(237,220,195);">칸반(Kanban)</span>**: <span style="background-color:rgb(242,213,214);">반복주기 기간이 고정된 경우와 고정되지 않은 경우가 있으며, 각 반복주기는 완료 후 하나의 개선 사항이나 기능을 전달하거나 몇 개의 기능을 묶어 한번에 전달할 수도 있음</span>
- **<span style="background-color:rgb(237,220,195);">나선형(Spiral)</span>**: <span style="background-color:rgb(242,213,214);">실험적인 증분을 생성, 일부는 차후 개발 과정에서 상당 부분 수정되거나 심한 경우 폐기되기도 함</span>

이런 모델을 활용해 컴포넌트나 시스템을 개발하면 전반적인 개발 과정에서 테스트 레벨을 중첩하거나 반복적으로 적용하는 경우가 많아진다. 이상적으로는 각 기능의 배포 시점이 가까워짐에 따라 여러 테스트 레벨에서 테스트되는 것이다. 지속적인 전달 혹은 배포를 활용하는 팀도 있는데, 두 가지 모두 릴리스 파이프라인에 속한 여러 테스트 레벨에 대해 상당한 자동화 구현을 요구한다. 이런 방법을 활용하는 개발 방법론 중 다수는 자기 조직적인 팀(self-organizing teams)의 개념도 수용하고 있는데, 이 개념으로 인해 테스팅 작업을 편성하는 방법과 테스터와 개발자 간의 관계에도 변화가 일어날 수 있다.<br>
이런 방법을 사용하면 점진적으로 커지는 시스템을 만들 수 있으며, 해당 시스템은 최종 사용자에게 기능별, 반복주기별, 아니면 좀 더 전통적인 주요 릴리스 단위로 릴리스할 수 있다. 소프트웨어 증분이 최종 사용자를 위한 릴리스인지의 여부와 상관없이 시스템이 커짐에 따라 리그레션 테스팅의 중요성은 증가하게 된다.<br>
순차적 모델과는 다르게 <span style="background-color:rgb(207,228,207);">반복적 점진적 모델</span>은 <span style="background-color:rgb(237,220,195);">사용 가능한 소프트웨어를 몇 주, 또는 며칠 만에 전달할 수 있다. 다만, 전체 요구사항을 충족하는 제품은 몇 개월 또는 몇 년에 걸쳐 전달하게 된다.</span><br>
애자일 개발에서의 소프트웨어 테스팅에 대한 추가 정보는 (ISTQB-CTFL-AT, Black 2017, Crispin 2008, Gregory 2015) 참조.

## 2.1.2 정황에 따른 소프트웨어 개발 수명주기 모델 (Software Development Lifecycle Models in Context)
{: .notice--success}

<span style="color:green">(K1) 소프트웨어 개발 수명주기 모델을 프로젝트 정황과 제품 특성에 따라 수정해야 하는 이유를 식별할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">소프트웨어 개발 수명주기 모델은 프로젝트 정황과 제품 특성에 따라 선택하고 적용</span>해야 한다. <span style="background-color:rgb(237,220,195);">프로젝트의 목표, 개발 대상 제품 유형, 비즈니스 특성 (예: 출시 시기), 식별된 제품 및 프로젝트 리스크 등을 기반으로 적합한 소프트웨어 개발 모델을 선택할 필요</span>가 있다. 예를 들어, <span style="background-color:rgb(242,213,214);">내부에서만 사용하는 소규모 관리 시스템의 개발과 테스팅은 자동차 브레이크 제어 시스템과 같은 안전 최우선 시스템의 개발, 테스팅과는 달라야 한다. 또 다른 예로, 조직적 문화적 차이가 팀원 간의 의사소통에 걸림돌이 되고, 결국 개발 자체를 지연시키는 경우</span>가 있을 수도 있다.<br>
<span style="background-color:rgb(207,228,207);">프로젝트의 정황</span>에 따라 <span style="background-color:rgb(237,220,195);">테스트 레벨과 테스트 활동을 조합하거나 조정</span>해야 할 경우가 있다. 예를 들어, <span style="background-color:rgb(242,213,214);">상용 소프트웨어(COTS, commercial off-the-shelf)를 큰 시스템에 통합하는 경우, 구매자가 상호운용성 테스팅을 시스템 통합 테스트 레벨(예: 인프라와 기타 시스템과의 통합)의 끝과 인수 테스트 레벨(사용자 인수 테스팅과 운영 인수 테스팅 또 기능과 비기능 테스팅)에서 실행할 수 있다.</span> 테스트 레벨에 관해서는 2.2 절을 참조하고, 테스트 유형에 관해서는 2.3 절을 참조하라.<br>
또한, <span style="background-color:rgb(237,220,195);">소프트웨어 개발 수명주기 모델 자체도 조합</span>할 수 있다. 예를 들어, <span style="background-color:rgb(242,213,214);">백엔드 시스템과 그것의 통합에 대한 개발과 테스팅에는 V-모델을 사용하고, 프런트엔드 사용자 인터페이스(UI) 기능의 개발과 테스트에는 애자일 개발 모델을 사용할 수 있다. 프로젝트 초반에는 프로토타이핑(prototyping)을 사용하다 실험적인 단계가 끝나면 점진적 개발 모델을 적용하는 경우도 있다.</span><br>
<span style="background-color:rgb(242,213,214);">다수의 다양한 오브젝트(object)로 구성된 사물 인터넷(IoT) 시스템에서는 보통 오브젝트 별로 다른 소프트웨어 개발 수명주기 모델을 적용한다. 각 개별 기기, 제품, 서비스가 각각 하나의 오브젝트가 될 수 있다. 그렇기 때문에 사물 인터넷 시스템용 제품 개발은 특히 어려울 수 있다. 또한, 이런 오브젝트에 적용하는 소프트웨어 개발 수명주기는 해당 오브젝트를 운영에 사용하기 위해 배포된 후, 즉 소프트웨어 개발 수명주기의 후반부(예: 운영, 업데이트, 해체 단계)를 더 강조하고 있다.</span><br>
<span style="background-color:rgb(207,228,207);">소프트웨어 개발 모델이 프로젝트 및 제품 특성의 맥락에 맞게 조정되어야 하는 이유</span>는 다음과 같다:
- <span style="background-color:rgb(237,220,195);">시스템의 제품 리스크의 차이</span> (복잡하거나 간단한 프로젝트)
- <span style="background-color:rgb(237,220,195);">많은 사업부가 프로젝트나 프로그램의 일부일 수 있다</span> (순차적 및 애자일 개발의 조합)
- <span style="background-color:rgb(237,220,195);">제품의 짧은 출시 기간</span> (테스트 레벨에서 테스트 유형의 통합 및 테스트 레벨 병합)

# 2.2 테스트 레벨 (Test Levels)
{: .notice--warning .text-center}

<span style="color:green">(K2) 목적, 테스트 베이시스, 테스트 대상, 대표적 결함과 장애, 접근법과 책임의 관점에서 다양한 테스트 레벨을 비교할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">테스트 레벨</span>이란 <span style="background-color:rgb(237,220,195);">함께 분류되고 관리되는 테스트 활동의 집합을 지칭</span>한다. 각 테스트 레벨은 1.4 절에서 설명하고 있는 활동으로 구성되며, 개별 단위(unit)나 컴포넌트에서부터 완성된 시스템이나 경우에 따라서는 시스템의 시스템까지 해당 개발 레벨의 소프트웨어와 관련해 실행되는 전체 테스트 프로세스의 하나의 사례이다. 테스트 레벨은 소프트웨어 개발 수명주기의 기타 활동과도 연관되어 있다.<br>
이 실러버스에서 다루고 있는 테스트 레벨은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">컴포넌트 테스팅</span>
- <span style="background-color:rgb(237,220,195);">통합 테스팅</span>
- <span style="background-color:rgb(237,220,195);">시스템 테스팅</span>
- <span style="background-color:rgb(237,220,195);">인수 테스팅</span>

테스트 레벨은 다음과 같은 <span style="background-color:rgb(237,220,195);">특성을 기준으로 분류</span>된다:
- <span style="background-color:rgb(242,213,214);">구체적인 목적</span>
- <span style="background-color:rgb(242,213,214);">테스트 케이스를 도출하기 위해 참고하는 테스트 베이시스</span>
- <span style="background-color:rgb(242,213,214);">테스트 대상(즉, 테스트 되고 있는 것)</span>
- <span style="background-color:rgb(242,213,214);">일반적인 결함과 장애</span>
- <span style="background-color:rgb(242,213,214);">구체적인 접근법과 역할</span>

모든 테스트 레벨에는 <span style="background-color:rgb(237,220,195);">적절한 테스트 환경이 필요</span>하다. 예를 들어, <span style="background-color:rgb(242,213,214);">인수 테스팅에는 실제 사용 환경과 유사한 환경이 가장 이상적이지만, 컴포넌트 테스팅에서는 개발자가 자신의 개발 환경을 사용하는 경우가 대부분</span>이다.

## 2.2.1 컴포넌트 테스팅 (Component Testing)
{: .notice--success}

**컴포넌트 테스팅의 목적 (Objectives of component testing)**<br>
<span style="color:blue">컴포넌트 테스팅(단위 혹은 모듈 테스팅이라고 부르기도 함)은 개별적으로 테스트할 수 있는 컴포넌트에 초점을 맞춘다.</span><br>
<span style="background-color:rgb(207,228,207);">컴포넌트 테스팅의 목적</span>에는 다음과 같은 것들이 있다:
- <span style="background-color:rgb(237,220,195);">리스크 완화</span>
- <span style="background-color:rgb(237,220,195);">컴포넌트의 기능과 비기능 동작이 설계 및 명세와 일치하는지 여부 판단</span>
- <span style="background-color:rgb(237,220,195);">컴포넌트 품질 수준에 대한 자신감 획득</span>
- <span style="background-color:rgb(237,220,195);">컴포넌트에 존재하는 결함 발견</span>
- <span style="background-color:rgb(237,220,195);">다음 단계로의 결함 전이 방지</span>

경우에 따라, 특히 <u>코드 변경이 지속해서 이루어지는 점진적 반복적 개발 모델(예: 애자일)에서는 수정으로 인해 기존 컴포넌트가 손상되지 않았다는 확신을 얻는 데 자동 컴포넌트 리그레션 테스트가 중요한 역할</u>을 한다.<br>
<span style="background-color:rgb(207,228,207);">컴포넌트 테스팅</span>은 <span style="background-color:rgb(237,220,195);">소프트웨어 개발 수명주기 모델과 시스템에 따라 개별적으로 이루어지는 경우가 많으며, 그럴 경우 목 오브젝트(mock object), 서비스 가상화(service virtualization), 하네스(harness), 스텁(stub), 드라이버(driver) 등이 필요할 수도 있다.</span> 컴포넌트 테스팅은 <span style="background-color:rgb(237,220,195);">기능(예: 연산의 정확성), 비기능 특성(예: 메모리 누수 탐지), 구조적 속성(예: 결정 테스팅) 등을 커버할 수 있다.</span>

**테스트 베이시스 (Test basis)**<br>
<span style="background-color:rgb(207,228,207);">컴포넌트 테스팅의 테스트 베이시스로 사용할 수 있는 대표적인 작업 산출물</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">상세 설계</span>
- <span style="background-color:rgb(237,220,195);">코드</span>
- <span style="background-color:rgb(237,220,195);">데이터 모델</span>
- <span style="background-color:rgb(237,220,195);">컴포넌트 명세</span>

**테스트 대상 (Test objects)**<br>
<span style="background-color:rgb(207,228,207);">컴포넌트 테스팅의 대표적인 테스트 대상</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">컴포넌트, 단위, 모듈</span>
- <span style="background-color:rgb(237,220,195);">코드 및 데이터 구조</span>
- <span style="background-color:rgb(237,220,195);">클래스</span>
- <span style="background-color:rgb(237,220,195);">데이터베이스 모듈</span>

**대표적인 결함과 장애 (Typical defects and failures)**<br>
<span style="background-color:rgb(207,228,207);">컴포넌트 테스팅의 대표적인 결함과 장애</span>는 다음과 같다:
- <span style="background-color:rgb(237,220,195);">잘못된 기능</span> (예: 설계 명세의 설명과 다름)
- <span style="background-color:rgb(237,220,195);">데이터 흐름 문제</span>
- <span style="background-color:rgb(237,220,195);">잘못된 코드 및 논리</span>

<u>결함은 발견하는 즉시 수정되며, 공식적인 결함 관리 프로세스 없이 이루어지는 경우가 많다. 하지만 개발자가 결함에 대해 보고하는 경우, 근본 원인 분석 및 프로세스 개선에 활용할 수 있는 중요한 정보를 제공</u>하게 된다.

**구체적인 접근법과 책임 (Specific approaches and responsibilities)**<br>
<span style="background-color:rgb(232,233,234);">일반적으로 컴포넌트 테스팅은 코드를 작성한 개발자가 수행하지만, 다른 사람이 수행하더라도 최소한 테스트 대상 코드에 접근할 수 있어야 한다. 개발자는 컴포넌트 개발과 결함 발견 및 수정을 번갈아 가며 진행할 수 있다. 개발자는 컴포넌트 코드를 작성한 후 테스트를 작성하고 실행하는 경우가 많다. 하지만, 특히 애자일 개발에서는, 애플리케이션 코드보다 자동화된 컴포넌트 테스트 케이스를 먼저 작성하는 경우도 있다.<br>
예를 들어, 테스트 주도 개발(TDD)을 생각해보자. 테스트 주도 개발은 자동 테스트 케이스를 개발한 후, 작은 코드 조각들을 빌드하고 통합해서 컴포넌트 테스트를 실행하고, 발생한 이슈를 수정하고 코드를 리팩토링(re- factoring)하는 것으로 구성된 주기를 기반으로 이루어지는 매우 반복적인 프로세스이다. 이 프로세스는 전체 컴포넌트가 완성되고 모든 컴포넌트 테스트가 통과할 때까지 계속된다. 테스트 주도 개발은 테스트 우선 접근법의 한가지 예이다. 테스트 주도 개발은 익스트림 프로그래밍(XP, eXtreme Programming)에서 처음 등장했지만, 현재는 다른 애자일 방법론뿐만 아니라 순차적 수명주기 모델에서도 활용하고 있다 (ISTQB-CTFL- AT) 참조.</span>

## 2.2.2 통합 테스팅 (Integration Testing)
{: .notice--success}

**통합 테스팅의 목적 (Objectives of integration testing)**<br>
<span style="color:blue">통합 테스팅은 컴포넌트나 시스템 간의 상호작용에 초점을 맞춰서 진행한다.</span><br>
<span style="background-color:rgb(207,228,207);">통합 테스팅의 목적</span>에는 다음과 같은 것들이 있다:
- <span style="background-color:rgb(237,220,195);">리스크 완화</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">인터페이스</span>의 기능과 비기능 동작이 설계 및 명세와 일치하는지 여부 판단</span>
- <span style="background-color:rgb(237,220,195);"><span style="color:red">인터페이스</span> 품질 수준에 대한 자신감 획득</span>
- <span style="background-color:rgb(237,220,195);">결함 발견</span> (<u>결함은 <span style="color:red">인터페이스</span> 자체 또는 컴포넌트나 시스템에 존재할 수 있다</u>)
- <span style="background-color:rgb(237,220,195);">다음 단계로의 결함 전이 방지</span>

<u>컴포넌트 테스팅과 마찬가지로, 자동 통합 리그레션 테스트를 수행하여 수정으로 인해 기존 <span style="color:red">인터페이스</span>, 컴포넌트, 시스템 등이 손상되지 않았다는 확신을 얻는 경우가 있다.</u><br>
이 실러버스에서는 다음과 같은 두 개의 다른 통합 테스팅 레벨을 다루고 있으며, 이런 통합 테스팅은 다양한 크기의 테스트 대상에 수행할 수 있다:
- <span style="background-color:rgb(207,228,207);">컴포넌트 통합 테스팅</span>은 <span style="background-color:rgb(237,220,195);">통합된 컴포넌트 간의 상호운용성과 인터페이스에 초점을 맞춘다. 컴포넌트 통합 테스팅은 컴포넌트 테스팅 후 수행하며 자동화하는 경우가 많다. 반복적 점진적 개발에서는 컴포넌트 통합 테스트를 지속적 통합 프로세스의 일부로 수행한다.</span>
- <span style="background-color:rgb(207,228,207);">시스템 통합 테스팅</span>은 <span style="background-color:rgb(237,220,195);">시스템, 패키지, 마이크로 서비스(microservice) 간의 상호운용성과 인터페이스에 초점을 맞춘다. 시스템 통합 테스팅은 또한 기존 컴포넌트(예: 웹 서비스)와의 상호운용 혹은 인터페이스를 커버하기도 한다. 이 경우 개발 조직이 외부 인터페이스를 제어하지 않으므로 테스팅에 여러 가지 어려움을 겪게 될 수 있다 (예: 테스트의 진행을 막고 있는 외부 조직의 코드에 존재하는 결함의 해결, 테스트 환경 구성, 등). 시스템 통합 테스팅은 (순차적 개발과 점진적 반복적 개발 모두에서) 시스템 테스팅 후 또는 진행 중인 시스템 테스팅 활동과 병행해서 수행할 수 있다.</span>

**테스트 베이시스 (Test basis)**<br>
<span style="background-color:rgb(207,228,207);">통합 테스팅의 테스트 베이시스로 사용할 수 있는 대표적인 작업 산출물</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">소프트웨어 및 시스템 설계</span>
- <span style="background-color:rgb(237,220,195);">시퀀스 다이어그램(sequence diagram)</span>
- <span style="background-color:rgb(237,220,195);">인터페이스 및 통신 프로토콜 명세</span>
- <span style="background-color:rgb(237,220,195);">유스케이스</span>
- <span style="background-color:rgb(237,220,195);">컴포넌트나 시스템 레벨의 아키텍처</span>
- <span style="background-color:rgb(237,220,195);">워크플로우(workflow)</span>
- <span style="background-color:rgb(237,220,195);">외부 인터페이스 정의서</span>

**테스트 대상 (Test objects)**<br>
<span style="background-color:rgb(207,228,207);">통합 테스팅의 대표적인 테스트 대상</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">서브시스템(subsystems)</span>
- <span style="background-color:rgb(237,220,195);">데이터베이스(database)</span>
- <span style="background-color:rgb(237,220,195);">인프라(infrastructure)</span>
- <span style="background-color:rgb(237,220,195);">인터페이스(interfaces)</span>
- <span style="background-color:rgb(237,220,195);">APIs</span>
- <span style="background-color:rgb(237,220,195);">마이크로서비스(microservices)</span>

**일반적인 결함과 장애 (Typical defects and failures)**<br>
<span style="background-color:rgb(207,228,207);">컴포넌트 통합 테스팅에서 발견되는 대표적인 결함과 장애</span>는 다음과 같다:
- <span style="background-color:rgb(237,220,195);">잘못된 데이터, 누락된 데이터, 잘못된 데이터 인코딩</span>
- <span style="background-color:rgb(237,220,195);">잘못된 인터페이스 콜 순서나 타이밍</span>
- <span style="background-color:rgb(237,220,195);">인터페이스 불일치</span>
- <span style="background-color:rgb(237,220,195);">컴포넌트 간의 통신 장애</span>
- <span style="background-color:rgb(237,220,195);">컴포넌트 간의 통신 실패 처리 누락 및 오류</span>
- <span style="background-color:rgb(237,220,195);">컴포넌트 간 주고 받는 데이터의 의미, 단위, 경계에 대한 잘못된 가정</span>

<span style="background-color:rgb(207,228,207);">시스템 통합 테스팅에서 발견되는 대표적인 결함과 장애</span>는 다음과 같다:
- <span style="background-color:rgb(237,220,195);">시스템 간의 일관적이지 않은 메시지 구조</span>
- <span style="background-color:rgb(237,220,195);">잘못된 데이터, 누락된 데이터, 잘못된 데이터 인코딩</span>
- <span style="background-color:rgb(237,220,195);">인터페이스 불일치</span>
- <span style="background-color:rgb(237,220,195);">시스템 간의 통신 장애</span>
- <span style="background-color:rgb(237,220,195);">시스템 간의 통신 실패 처리 누락 및 오류</span>
- <span style="background-color:rgb(237,220,195);">시스템 간 주고 받는 데이터의 의미, 단위, 경계에 대한 잘못된 가정</span>
- <span style="background-color:rgb(237,220,195);">필수 보안 규정 준수 실패</span>

**구체적인 접근법과 책임 (Specific approaches and responsibilities)**<br>
<span style="background-color:rgb(232,233,234);">컴포넌트 통합 테스트와 시스템 통합 테스트는 통합 자체에 집중해야 한다. 예를 들어, 모듈 A 와 모듈 B 를 통합하는 경우, 모듈 간의 커뮤니케이션에 테스트를 집중해야 하며 컴포넌트 테스팅에서 커버했어야 할 개별 모듈의 기능에 초점을 맞춰서는 안 된다. 시스템 X와 시스템 Y를 통합하는 경우, 시스템 간의 커뮤니케이션에 테스트를 집중해야 하며 시스템 테스팅에서 커버했어야 할 개별 시스템의 기능에 초점을 맞춰서는 안 된다. 기능, 비기능, 구조적 테스트 유형이 적용될 수 있다.<br>
컴포넌트 통합 테스팅은 개발자의 책임인 경우가 많다. 시스템 통합 테스팅은 일반적으로 테스터의 책임이다. 이상적인 상황에서는 시스템 통합 테스팅을 수행하는 테스터는 시스템 아키텍처를 이해하고 통합 계획에 참여했어야 한다.<br>
컴포넌트나 시스템을 빌드하기 전에 통합 테스트와 통합 테스트 전략을 세운 경우, 가장 효과적인 테스팅이 가능한 순서대로 컴포넌트나 시스템을 빌드할 수 있다. 시스템 통합 전략은 시스템 아키텍처(예: 상향식과 하향식), 기능 작업, 트랜잭션 처리 순서, 시스템 또는 컴포넌트의 기타 측면 등을 기반으로 수립할 수 있다. 결함 격리를 좀 더 수월하게 하고 결함을 일찍 발견하기 위해 통합은 한번에 모든 것을 통합하지 않고 가능한 점진적으로 진행해야 한다(즉, 한번에 몇 개의 컴포넌트나 시스템만 추가). 가장 복잡한 인터페이스에 대한 리스크 분석은 통합 테스팅의 노력을 집중시키는 데 도움이 된다.<br>
통합하는 범위가 넓으면 장애를 특정 컴포넌트나 시스템으로 격리하기 어려워지고, 이는 개발의 리스크와 문제 해결(Troubleshooting) 시간을 증가시킬 수 있다. 이것은 지속적인 통합이 관행으로 자리 잡은 배경 중 하나이다. 지속적인 통합에서 소프트웨어는 컴포넌트 단위로 통합(즉, 기능적 통합)된다. 이런 지속적인 통합은 이상적으로 여러 테스트 레벨에 자동 리그레션 테스팅을 적용하는 경우가 많다.</span>

## 2.2.3 시스템 테스팅 (System Testing)
{: .notice--success}

**시스템 테스팅의 목적 (Objectives of system testing)**<br>
<span style="color:blue">시스템 테스팅은 전체 시스템 또는 제품의 동작이나 능력에 관심을 가지며, 시스템이 수행할 엔드-투-엔드(end- to-end) 작업과 그런 작업을 수행할 때 나타나는 비기능 동작을 고려하는 경우가 많다.</span><br>
<span style="background-color:rgb(207,228,207);">시스템 테스팅의 대표적인 목적</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">리스크 완화</span>
- <span style="background-color:rgb(237,220,195);">시스템의 기능/비기능 동작이 설계 및 명시된 대로 이루어지는지 검증</span>
- <span style="background-color:rgb(237,220,195);">완성된 시스템이 기대한 대로 동작하는지 확인</span>
- <span style="background-color:rgb(237,220,195);">전체 시스템 품질에 대한 자신감 획득</span>
- <span style="background-color:rgb(237,220,195);">결함 발견</span>
- <span style="background-color:rgb(237,220,195);">결함이 상위 테스트 레벨이나 생산 단계로의 전이 방지</span>

<u>시스템에 따라서는 데이터 품질 검증 또한 목적</u>일 수도 있다. <u>컴포넌트 테스팅이나 통합 테스팅과 마찬가지로, 자동 시스템 리그레션 테스트를 통해 어떤 부분의 수정으로 기존 기능이나 엔드-투-엔드 기능에 문제가 생기지 않았다는 자신감을 얻을 수 있는 경우가 있다.</u> <span style="background-color:rgb(207,228,207);">시스템 테스팅</span>은 <span style="background-color:rgb(237,220,195);">이해관계자가 릴리스 결정시 사용하는 정보를 제공하는 경우가 많다.</span> 시스템 테스팅을 통해 <span style="background-color:rgb(237,220,195);">법적, 규정 요구사항이나 표준을 만족시킬 수도 있다.</span>
<u>테스트 환경은 최종 사용, 생산 환경과 부합하는 것이 가장 이상적</u>이다.

**테스트 베이시스 (Test basis)**<br>
<span style="background-color:rgb(207,228,207);">시스템 테스팅의 테스트 베이시스로 사용할 수 있는 대표적인 작업 산출물</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">시스템 및 소프트웨어 요구사항 명세 (기능/비기능)</span>
- <span style="background-color:rgb(237,220,195);">리스크 분석 보고서</span>
- <span style="background-color:rgb(237,220,195);">유스케이스</span>
- <span style="background-color:rgb(237,220,195);">에픽(epic)과 사용자 스토리</span>
- <span style="background-color:rgb(237,220,195);">시스템 동작 모델</span>
- <span style="background-color:rgb(237,220,195);">상태 다이어그램</span>
- <span style="background-color:rgb(237,220,195);">시스템 및 사용자 매뉴얼</span>

**테스트 대상 (Test objects)**<br>
<span style="background-color:rgb(207,228,207);">시스템 테스팅의 대표적인 테스트 대상</span>은 아래와 같다:
- <span style="background-color:rgb(237,220,195);">애플리케이션</span>
- <span style="background-color:rgb(237,220,195);">하드웨어/소프트웨어 시스템</span>
- <span style="background-color:rgb(237,220,195);">운영 시스템</span>
- <span style="background-color:rgb(237,220,195);">테스트 대상 시스템 (SUT, System Under Test)</span>
- <span style="background-color:rgb(237,220,195);">시스템 설정과 설정 데이터</span>

**일반적인 결함과 장애 (Typical defects and failures)**<br>
<span style="background-color:rgb(207,228,207);">시스템 테스팅에서 발견되는 결함과 장애</span>는 다음과 같다:
- <span style="background-color:rgb(237,220,195);">잘못된 연산</span>
- <span style="background-color:rgb(237,220,195);">시스템의 잘못되거나 예상치 못한 기능/비기능 동작</span>
- <span style="background-color:rgb(237,220,195);">시스템 내 잘못된 제어 및 데이터 흐름</span>
- <span style="background-color:rgb(237,220,195);">엔드-투-엔드 기능 작업 수행 실패</span>
- <span style="background-color:rgb(237,220,195);">시스템 환경에서 시스템의 정상 동작 실패</span>
- <span style="background-color:rgb(237,220,195);">시스템 및 사용자 매뉴얼대로의 시스템 동작 실패</span>

**구체적인 접근법과 역할 (Specific approaches and responsibilities)**<br>
<span style="background-color:rgb(232,233,234);">시스템 테스팅은 기능과 비기능 모두의 측면에서 전반적인 시스템의 엔드-투-엔드 동작에 관심을 가진다. 시스템 테스팅에서는 테스트 대상 시스템의 특성에 가장 잘 맞는 기법(4 장 참조)을 사용해야 한다. 예를 들어, 기능 동작이 비즈니스 규칙에서 설명하고 있는 것과 맞는지 검증하기 위해서는 결정 테이블을 생성할 수 있다.<br>
시스템 테스팅은 일반적으로 명세에 과도하게 의존하는 독립적인 테스터가 수행한다. 명세 결함(예: 누락된 사용자 스토리, 잘못 기술된 비즈니스 요구사항 등)은 기대하는 시스템 동작에 대한 이해 부족이나 의견 불일치를 가져올 수 있다. 이런 상황은 시간을 허비하게 만드는 거짓양성이나 결함 발견 효과를 감소시키는 거짓음성(false negatives)의 원인이 될 수 있다. 테스터가 사용자 스토리 개선이나 리뷰와 같은 정적 테스팅 활동에 좀 더 일찍 참여하면 이런 상황을 예방하는 데 도움이 된다.</span>

## 2.2.4 인수 테스팅 (Acceptance Testing)
{: .notice--success}

**인수 테스팅의 목적 (Objectives of acceptance testing)**<br>
<span style="color:blue">시스템 테스팅과 마찬가지로 인수 테스팅도 전체 시스템 또는 제품의 동작이나 능력에 초점을 두고 진행하는 경우가 많다.</span><br>
<span style="background-color:rgb(207,228,207);">인수 테스팅의 목적</span>에는 다음과 같은 것들이 있다:
- <span style="background-color:rgb(237,220,195);">전체 시스템의 품질에 대한 자신감 획득</span>
- <span style="background-color:rgb(237,220,195);">완성된 시스템이 기대한 대로 동작하는지 확인</span>
- <span style="background-color:rgb(237,220,195);">시스템의 기능/비기능 동작이 명세대로 동작하는지 검증</span>

<u>인수 테스팅의 결과로 시스템을 배포하거나 고객(최종 사용자)이 사용할 준비가 어느 정도 됐는지 평가할 수 있는 정보를 만들 수 있다.</u> 인수 테스팅 중 결함을 발견할 수 있지만, 결함 발견이 목적이 아닌 경우가 많으며, 인수 테스팅에서 상당수의 결함이 발견되면 심각한 프로젝트 리스크로 인식하는 경우도 있다. 인수 테스팅으로 법적, 규정 요구사항이나 표준을 만족할 수도 있다.<br>
<span style="background-color:rgb(207,228,207);">인수 테스팅의 대표적인 형태</span>는 다음과 같다:
- <span style="background-color:rgb(237,220,195);">사용자 인수 테스팅</span>
- <span style="background-color:rgb(237,220,195);">운영 인수 테스팅</span>
- <span style="background-color:rgb(237,220,195);">계약 및 규제 인수 테스팅</span>
- <span style="background-color:rgb(237,220,195);">알파(alpha) 및 베타(beta) 테스팅</span>

다음 4 개 절에서 각각을 설명하고 있다.

**사용자 인수 테스팅 (UAT, User Acceptance Testing)**<br>
시스템의 <span style="background-color:rgb(207,228,207);">사용자 인수 테스팅</span>은 일반적으로 <span style="background-color:rgb(237,220,195);">실제 또는 시뮬레이션된 운영 환경에서 예정된 사용자가 사용하기에 얼마나 적합한지 확인하는 데 관심</span>을 둔다. <span style="color:blue">가장 중요한 목적은 사용자가 그들의 필요에 따라 요구사항을 충족하면서 최소한의 어려움, 비용, 리스크 등으로 비즈니스 프로세스를 수행할 수 있다는 자신감을 획득하는 것</span>이다.

**운영 인수 테스팅 (OAT, Operational Acceptance Testing)**<br>
<span style="background-color:rgb(207,228,207);">운영자 또는 시스템 관리 직원에 의해 수행되는 시스템 인수 테스팅</span>은<span style="background-color:rgb(237,220,195);">(시뮬레이션 된) 생산 환경에서 이루어지는 경우가 많다.</span> <span style="background-color:rgb(237,220,195);">테스트는 운영 측면에 집중돼 있으며, 다음을 포함할 수 있다</span>:
- <span style="background-color:rgb(242,213,214);">백업 및 복원 테스팅</span>
- <span style="background-color:rgb(242,213,214);">설치, 삭제, 업그레이드</span>
- <span style="background-color:rgb(242,213,214);">긴급 복구 (disaster recovery)</span>
- <span style="background-color:rgb(242,213,214);">사용자 관리</span>
- <span style="background-color:rgb(242,213,214);">유지보수 작업</span>
- <span style="background-color:rgb(242,213,214);">데이터 로딩 및 이관(migration) 작업</span>
- <span style="background-color:rgb(242,213,214);">보안 취약점 확인</span>
- <span style="background-color:rgb(242,213,214);">성능 테스팅</span>

<span style="color:blue">운영 인수 테스팅의 가장 중요한 목적은 운영자 또는 시스템 관리자가 비록 예외적이고 어려운 조건에서라도 운영 환경에서 사용자를 위해 시스템을 정상적으로 유지할 수 있다는 자신감을 얻는 것</span>이다.

**계약 및 규제 인수 테스팅 (Contractual and regulatory acceptance testing)**<br>
<span style="background-color:rgb(207,228,207);">계약 인수 테스팅</span>은 <span style="background-color:rgb(237,220,195);">주문 개발 소프트웨어의 생산을 위한 계약서에 명시된 인수 조건을 가지고 수행한다. 인수 조건은 모든 계약 당사자가 계약에 동의할 때 정의해야 한다. 계약 인수 테스팅은 사용자나 독립적인 테스터가 수행하는 경우가 많다.</span><br>
<span style="background-color:rgb(207,228,207);">규제 인수 테스팅</span>은 <span style="background-color:rgb(237,220,195);">정부, 법적, 안전 규제 등과 같이 준수해야 하는 모든 규제를 가지고 수행한다. 규제 인수 테스팅은 사용자나 독립적인 테스터가 수행하는 경우가 많으며, 규제 기관이 결과에 대한 실사나 감사를 진행하기도 한다.</span><br>
<span style="color:blue">계약 및 규제 인수 테스팅의 가장 중요한 목적은 계약이나 규제 준수에 대한 자신감의 획득</span>이다.

**알파 및 베타 테스팅 (Alpha and beta testing)**<br>
<u>알파 및 베타 테스팅은 소프트웨어 제품을 시장에 출시하기 전에 기존 혹은 신규 사용자, 고객, 운영자 등으로부터 피드백을 받기 원하는 상용 소프트웨어 개발자가 사용하는 경우가 많다.</u> <span style="background-color:rgb(207,228,207);">알파 테스팅</span>은 <span style="background-color:rgb(237,220,195);">개발 조직의 현장에서 개발팀이 아닌 신규 혹은 기존 고객이나 운영자, 독립적 테스트팀이 수행</span>한다. <span style="background-color:rgb(207,228,207);">베타 테스팅</span>은 <span style="background-color:rgb(237,220,195);">신규 혹은 기존 고객 이나 운영자가 자신의 환경에서 수행한다. 베타 테스팅은 알파 테스팅 후에 진행하거나 사전 알파 테스팅 없이 수행할 수도 있다.</span><br>
<span style="color:blue">알파 및 베타 테스팅의 목적 중 하나는 신규 혹은 기존 고객이나 운영자가 시스템을 일반적인 조건과 운영 환경에서 사용해 자신의 목적을 최소한의 어려움, 비용, 리스크 등으로 완수할 수 있다는 자신감을 획득하는 것이다. 또 다른 목적은 시스템을 사용할 조건 및 환경과 관련된 결함의 발견일 수 있다. 특히, 이런 조건과 환경을 개발팀에서 동일하게 연출하기 어려운 경우 더 그러하다.</span>

**테스트 베이시스 (Test basis)**<br>
<span style="background-color:rgb(207,228,207);">모든 형태의 인수 테스팅의 테스트 베이시스로 활용할 수 있는 대표적인 작업 산출물</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">비즈니스 프로세스</span>
- <span style="background-color:rgb(237,220,195);">사용자 또는 비즈니스 요구사항</span>
- <span style="background-color:rgb(237,220,195);">규제, 법적 계약, 표준</span>
- <span style="background-color:rgb(237,220,195);">유스케이스 및 사용자 스토리</span>
- <span style="background-color:rgb(237,220,195);">시스템 요구사항</span>
- <span style="background-color:rgb(237,220,195);">시스템 또는 사용자 문서</span>
- <span style="background-color:rgb(237,220,195);">설치 절차</span>
- <span style="background-color:rgb(237,220,195);">리스크 분석 보고서</span>

추가로 <span style="background-color:rgb(207,228,207);">운영 인수 테스팅의 테스트 케이스를 도출하기 위한 테스트 베이시스로 다음과 같은 작업 산출물이 사용될 수 있다</span>:
- <span style="background-color:rgb(237,220,195);">백업 및 복원 절차</span>
- <span style="background-color:rgb(237,220,195);">긴급 복구 절차</span>
- <span style="background-color:rgb(237,220,195);">비기능 요구사항</span>
- <span style="background-color:rgb(237,220,195);">운영 문서</span>
- <span style="background-color:rgb(237,220,195);">배포 및 설치 지침</span>
- <span style="background-color:rgb(237,220,195);">성능 목표</span>
- <span style="background-color:rgb(237,220,195);">데이터베이스 패키지</span>
- <span style="background-color:rgb(237,220,195);">보안 표준 또는 규정</span>

**일반적인 테스트 대상 (Typical test objects)**<br>
<span style="background-color:rgb(207,228,207);">모든 유형의 인수 테스팅의 대표적인 테스트 대상</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">테스트 대상 시스템</span>
- <span style="background-color:rgb(237,220,195);">시스템 설정과 설정 데이터</span>
- <span style="background-color:rgb(237,220,195);">완전히 통합된 시스템의 비즈니스 프로세스</span>
- <span style="background-color:rgb(237,220,195);">복원 시스템이나 비즈니스 연속성 및 긴급 복구 테스팅을 위한 핫 사이트 (hot site)</span>
- <span style="background-color:rgb(237,220,195);">운영 및 유지보수 프로세스</span>
- <span style="background-color:rgb(237,220,195);">양식</span>
- <span style="background-color:rgb(237,220,195);">보고서</span>
- <span style="background-color:rgb(237,220,195);">기존 및 전환된 생산 데이터</span>

**일반적인 결함과 장애 (Typical defects and failures)**<br>
<span style="background-color:rgb(207,228,207);">모든 유형의 인수 테스팅의 대표적인 결함</span>은 다음과 같다:
- <span style="background-color:rgb(237,220,195);">비즈니스나 사용자 요구사항을 충족하지 못하는 시스템 워크플로우 (workflow)</span>
- <span style="background-color:rgb(237,220,195);">잘못 구현된 비즈니스 규칙</span>
- <span style="background-color:rgb(237,220,195);">계약 혹은 규제 요구사항을 충족하지 못하는 시스템</span>
- <span style="background-color:rgb(237,220,195);">보안 취약성, 많은 부하가 걸렸을 때 성능 효율성 저하, 지원 대상 플랫폼상에서의 잘못된 운영 등과 같은 비기능 장애</span>

**구체적인 접근법과 역할 (Specific approaches and responsibilities)**<br>
<span style="background-color:rgb(232,233,234);">인수 테스팅은 주로 고객, 비즈니스 사용자, 제품 소유자, 혹은 시스템 운영자가 담당하며, 기타 이해관계자가 참여하는 경우도 있다.<br>
인수 테스팅은 순차적 개발 수명주기의 마지막 테스트 레벨로 여겨지는 경우가 많지만, 다음과 같이 다른 시점에서 이루어지는 경우도 있다:</span>
- <span style="background-color:rgb(232,233,234);">상용 소프트웨어 제품에 대한 인수 테스팅은 그것이 설치되거나 통합될 때 이루어진다.</span>
- <span style="background-color:rgb(232,233,234);">신규 기능 개선 사항에 대한 인수 테스팅은 시스템 테스팅 전에 이루어질 수 있다.</span>

<span style="background-color:rgb(232,233,234);">반복적 개발에서는 프로젝트팀이 다양한 유형의 인수 테스팅을 각 반복주기 중간 혹은 끝에 편성할 수 있다. 대표적으로 인수 조건을 가지고 신규 기능을 검증하거나 신규 기능이 사용자의 요구를 만족하는지 확인하는 경우도 있다. 또한, 알파 테스트와 베타 테스트는 각 반복주기 끝에, 혹은 각 반복주기가 완료되고 나서, 또는 몇 개의 반복주기 후에 수행할 수도 있다. 사용자 인수 테스트, 운영 인수 테스트, 규제 인수 테스트, 계약 인수 테스트 등도 각 반복주기 끝에, 혹은 각 반복주기가 완료되고 나서, 또는 몇 개의 반복주기 후에 수행할 수 있다.</span>

# 2.3 테스트 유형 (Test Types)
{: .notice--warning .text-center}

<span style="color:green">(K2) 기능, 비기능, 화이트박스 테스팅을 비교할 수 있다.</span><br>
<span style="color:green">(K1) 기능, 비기능, 화이트박스 테스트가 모든 테스트 레벨에서 이루어질 수 있음을 인지할 수 있다.</span><br>
<span style="color:green">(K2) 확인 테스팅과 리그레션 테스팅의 목적을 비교할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">테스트 유형</span>이란 <span style="background-color:rgb(237,220,195);">특정 테스트 목적을 위해 소프트웨어 시스템이나 시스템의 일부 특정 속성을 테스트하는 활동의 집합</span>을 얘기한다. 대표적인 <span style="background-color:rgb(237,220,195);">목적</span>은 다음과 같다:
- <span style="background-color:rgb(242,213,214);">완전성, 정확성, 적합성 등과 같은 기능 품질 특성 평가</span>
- <span style="background-color:rgb(242,213,214);">신뢰성, 성능 효율성, 보안성, 호환성, 사용성 등과 같은 비기능 품질 특성 평가</span>
- <span style="background-color:rgb(242,213,214);">컴포넌트나 시스템의 아키텍처 및 구조가 정확하고 완전하며 명시된 것과 일치하는지 평가</span>
- <span style="background-color:rgb(242,213,214);">수정의 효과 평가. 예를 들어, 결함이 수정됐는지 확인(확인 테스팅)하고 소프트웨어나 환경의 변화로 인해 동작에 의도하지 않은 변화가 없는지(리그레션 테스팅) 평가</span>

## 2.3.1 기능 테스팅 (Functional Testing)
{: .notice--success}

기능 테스팅은 시스템이 수행해야 하는 기능을 평가하기 위한 테스트를 포함한다. 일반적으로 기능 요구사항은 비즈니스 요구사항 명세, 에픽(epic), 사용자 스토리, 유스케이스, 기능 명세 등과 같은 작업 산출물에 설명되어 있지만, 문서로 기록되지 않는 경우도 존재한다. 기능이란 시스템이 해야 하는 그 "무엇”을 얘기한다.<br>
기능 테스트는 모든 테스트 레벨에서 수행(예를 들어, 컴포넌트에 대한 테스트는 컴포넌트 명세를 기반으로 할 수 있다)해야 하지만, 각 레벨에서의 관심 사항은 다를 수 있다 (2.2절 참조).<br>
기능 테스팅은 소프트웨어 동작을 보기 때문에 컴포넌트나 시스템의 기능에 대한 테스트 컨디션과 테스트 케이스 도출을 위해 블랙박스 기법을 활용할 수 있다 (4.2 절 참조).<br>
기능 테스팅이 얼마나 철저하게 수행됐는지 기능 커버리지를 통해 측정할 수 있다. 기능 커버리지란 어떤 기능이 테스트에 의해 어느 정도 실행됐는지를 말하며, 커버되고 있는 요소 유형에 대한 백분율로 표기된다. 예를 들어, 테스트와 기능 요구사항 간의 추적성을 사용해 이런 요구사항 중 테스팅한 비율을 계산할 수 있고, 결국 커버리지 어디에 빈틈이 있는지 식별할 수 있다.<br>
기능 테스트 설계 및 실행에는 특수한 역량이나 지식이 필요할 수 있다. 소프트웨어가 해결하는 비즈니스 문제에 대한 지식(예: 정유 및 가스 업계를 위한 지질학 모델링(modeling) 소프트웨어) 등이 여기에 포함된다.

## 2.3.2 비기능 테스팅 (Non-functional Testing)
{: .notice--success}

시스템의 비기능 테스팅은 사용성, 성능 효율성 또는 보안성과 같은 시스템 특성을 평가한다. 소프트웨어 제품 품질 특성의 분류에 관해서는 ISO 표준(ISO/IEC 25010)을 참조. 비기능 테스팅이란 시스템이 "얼마나 잘" 동작하는지에 대한 테스팅을 말한다.<br>
일반적인 오해와는 다르게 비기능 테스팅은 모든 테스트 레벨에서 수행할 수 있고, 수행해야 한다. 또한, 가능한 초반에 수행하는 것이 좋다. 비기능 결함을 늦게 발견하게 되면 프로젝트의 성공에 큰 위협이 될 수 있다.<br>
블랙박스 기법(4.2 절 참조)은 비기능 테스팅을 위한 테스트 컨디션과 테스트 케이스를 도출하는 데 사용할 수 있다. 예를 들어, 성능 테스트를 위한 스트레스(stress) 조건을 정의하는 데 경계값 분석을 활용할 수 있다.<br>
비기능 테스팅을 얼마나 철저하게 수행했는지는 비기능 커버리지를 사용해서 측정할 수 있다. 비기능 커버리지란 특정 비기능 요소가 테스트로 어느 정도 실행됐는지를 말해주며 커버하고 있는 요소 유형에 대한 백분율로 표기한다. 예를 들어, 테스트와 지원 기기 간의 추적성을 사용해 이런 기기 중 호환성 테스팅으로 커버된 비율을 계산할 수 있고, 결국 커버리지 어디에 빈틈이 있는지 식별할 수 있다.<br>
비기능 테스트 설계 및 실행에는 특수한 역량이나 지식이 필요할 수 있다. 설계 또는 기술이 내재하고 있는 약점에 대한 지식(예: 특정 프로그래밍 언어와 관련된 보안 취약성), 또는 특정한 사용자 기반(예: 의료 시설 관리 시스템의 사용자가 가지는 특성) 등이 여기에 포함된다.<br>
비기능 품질 특성에 대한 테스팅에 관해서는 ISTQB-CTAL-TA, ISTQB-CTAL-TTA, ISTQB-CTAL-SEC, 기타 ISTQB specialist module 을 참조.

## 2.3.3 화이트박스 테스팅 (White-box Testing)
{: .notice--success}

화이트박스 테스팅은 시스템의 내부 구조나 구현을 기반으로 테스트를 도출한다. 내부 구조로는 코드, 아키텍처, 워크플로우(workflow), 시스템 내 데이터 플로우(data flow) 등이 있다 (4.3 절 참조).<br>
화이트박스 테스팅이 얼마나 철저하게 이루어졌는지는 구조 커버리지를 통해 측정할 수 있다. 구조 커버리지란 특정 구조 요소가 테스트에 의해 어느 정도 실행됐는지를 말하며, 커버되고 있는 요소 유형에 대한 백분율로 표기한다.<br>
컴포넌트 테스팅 레벨에서 얘기하는 코드 커버리지는 컴포넌트 코드 중 테스트된 비율을 얘기하며, 컴포넌트의 실행 가능한 구문 중 테스트된 비율이나 결정 결과값 중 테스트된 비율 등 코드의 여러 가지 측면(커버리지 항목)으로 측정될 수 있다. 이와 같은 유형의 커버리지를 합쳐서 코드 커버리지라고 한다. 컴포넌트 통합 테스팅 레벨에서는 컴포넌트 간의 인터페이스와 같은 시스템의 아키텍처를 기반으로 화이트박스 테스팅을 수행할 수 있으며, 구조 커버리지를 인터페이스 중 테스트된 비율의 측면에서 측정할 수 있다.<br>
화이트박스 테스트 설계와 구현에는 특수한 역량이나 지식이 필요할 수 있다. 대표적으로 코드가 구축된 방법, 데이터가 저장되는 방법(예를 들어, 가능한 데이터베이스 쿼리(queries)를 평가하기 위해), 코드 커버리지 도구를 사용하는 방법과 해당 결과를 제대로 분석하기 위한 지식 등이 있다.

## 2.3.4 변경 관련 테스팅 (Change-related Testing)
{: .notice--success}

결함을 수정하고자 했든 또는 기능을 추가하거나 개선하기 위해서 했든 시스템이 변경되면, 해당 변경이 결함을 제대로 수정했는지, 기능을 올바르게 구현했는지 또 예상하지 못한 부작용이 발생하지 않았는지 확인하기 위한 테스팅을 수행할 필요가 있다.
- 확인 테스팅(Confirmation testing): 결함이 수정된 후 이 결함으로 인해 불합격했던 모든 테스트 케이스를 새로운 소프트웨어 버전에서 재실행할 수 있다. 결함 수정에 필요한 변경을 커버하기 위해 소프트웨어를 대상으로 새로운 테스트를 수행할 수도 있다. 최소한 결함으로 발생했던 장애의 재현 절차를 새로운 소프트웨어 버전에서 실행해 볼 필요가 있다. 확인 테스팅의 목적은 원래 제대로 결함을 제대로 수정했는지 확인하는 것이다.
- 리그레션 테스팅(Regression testing): 코드의 특정 부분에 대한 변경이 무언가를 수정하기 위해서거나 또는 다른 목적이든 관계없이 이런 변경은 의도치 않게 코드의 다른 부분에 영향을 줄 수 있다. 여기서 다른 부분이란 같은 컴포넌트의 다른 부분, 같은 시스템의 다른 컴포넌트, 경우에 따라서는 다른 시스템일 수도 있다. 변경에는 운영 시스템이나 데이터베이스 관리 시스템의 신규 버전 등과 같은 환경에 대한 변경도 포함된다. 이런 의도하지 않은 부작용을 리그레션이라 부른다. 리그레션 테스팅은 이런 의도하지 않은 부작용을 발견하기 위한 테스트를 수행하는 것이다.

확인 테스팅과 리그레션 테스팅은 모든 테스트 레벨에서 수행 가능하다.<br>
특히 반복적 점진적 개발 수명주기(예: 애자일)에서는 신규 기능, 기존 기능에 대한 변경, 코드 리팩토링(code re-factoring) 때문에 코드에 잦은 변경이 가해지고 결국 변경 관련 테스팅이 필요하게 된다. 시스템이 진화하는 특성 때문에 확인 및 리그레션 테스팅은 매우 중요하다. 특히 개별 오브젝트(예: 기기)가 자주 업데이트되거나 교체되는 사물 인터넷(IoT) 시스템에서는 더욱 중요하다.<br>
리그레션 테스트 스위트는 여러번 반복 수행되며 대개는 서서히 변화하기 때문에 리그레션 테스팅은 자동화에 적합하다. 이런 테스트의 자동화는 프로젝트 초반에 시작해야 한다 (6 장 참조).

## 2.3.5 테스트 유형과 테스트 레벨 (Test Types and Test Levels)
{: .notice--success}

위에서 언급한 <span style="color:blue">모든 테스트 유형은 어느 테스트 레벨에서나 수행할 수 있다.</span> 인터넷 뱅킹 애플리케이션의 모든 테스트 레벨에 기능, 비기능, 화이트박스, 변경 관련 테스트가 어떻게 적용되는지 아래에서 예로 설명하고 있다.<br>
첫 째, <span style="background-color:rgb(207,228,207);">기능 테스트</span>는:
- <span style="background-color:rgb(237,220,195);">컴포넌트 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">컴포넌트가 복잡한 이자 계산을 어떻게 해야 하는지를 기반으로 테스트 설계</span>
- <span style="background-color:rgb(237,220,195);">컴포넌트 통합 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">사용자 인터페이스에서 포착하는 계정 정보가 어떻게 비즈니스 로직(logic)으로 전달되는지를 기반으로 테스트 설계</span>
- <span style="background-color:rgb(237,220,195);">시스템 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">계좌 소유주가 어떻게 자신의 예금 통장에 신용 한도를 부여할 수 있는지를 기반으로 테스트 설계</span>
- <span style="background-color:rgb(237,220,195);">시스템 통합 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">시스템이 외부 마이크로서비스를 사용해서 계좌 소유주의 신용 점수를 확인하는 방법을 기반으로 테스트 설계</span>
- <span style="background-color:rgb(237,220,195);">인수 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">은행이 신용 한도를 승인하거나 거절하는 방법을 기반으로 테스트 설계</span>

다음은 <span style="background-color:rgb(207,228,207);">비기능 테스트</span>의 예이다:
- <span style="background-color:rgb(237,220,195);">컴포넌트 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">복잡한 전체 이자 계산을 수행하기 필요한 CPU 사이클(cycle) 횟수를 평가하기 위해 성능 테스트 설계</span>
- <span style="background-color:rgb(237,220,195);">컴포넌트 통합 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">사용자 인터페이스에서 비즈니스 로직으로 전달되는 데이터로 인한 버퍼 오버플로우(buffer overflow) 취약성을 위한 보안 테스트 설계</span>
- <span style="background-color:rgb(237,220,195);">시스템 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">보이는 화면이 모든 지원 대상 브라우저와 모바일 기기에서 제대로 동작하는지 확인하기 위한 이식성 테스트 설계</span>
- <span style="background-color:rgb(237,220,195);">시스템 통합 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">신용 점수 마이크로서비스가 응답하지 않을 때 시스템의 강건성(robustness)을 평가하기 위한 신뢰성 테스트 설계</span>
- <span style="background-color:rgb(237,220,195);">인수 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">은행 신용 처리 인터페이스에 장애인의 접근성을 평가하는 사용성 테스트 설계</span>

다음은 <span style="background-color:rgb(207,228,207);">화이트박스 테스트</span>의 예이다:
- <span style="background-color:rgb(237,220,195);">컴포넌트 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">금융 계산을 수행하는 모든 컴포넌트에 대한 완벽한 구문 및 결정 커버리지(4.3 장 참조)를 달성하기 위한 테스트 설계</span>
- <span style="background-color:rgb(237,220,195);">컴포넌트 통합 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">브라우저 인터페이스의 각 화면이 다음 화면과 비즈니스 로직을 기반으로 데이터를 어떻게 전달하는지 확인하기 위한 테스트 설계</span>
- <span style="background-color:rgb(237,220,195);">시스템 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">신용 한도 신청 도중 순차적으로 거치게 되는 웹페이지를 커버하기 위한 테스트 설계</span>
- <span style="background-color:rgb(237,220,195);">시스템 통합 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">신용 점수 마이크로서비스로 보내는 모든 조회(inquiry) 유형을 실행하기 위한 테스트 설계</span>
- <span style="background-color:rgb(237,220,195);">인수 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">은행 간 이체에서 지원하는 모든 금융 데이터 파일 구조와 값 범위를 커버하기 위한 테스트 설계</span>

마지막으로, 다음은 <span style="background-color:rgb(207,228,207);">변경 관련 테스트</span>의 예이다:
- <span style="background-color:rgb(237,220,195);">컴포넌트 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">각 컴포넌트를 위한 자동 리그레션 테스트가 구축되고 지속적인 통합 프레임워크에 포함</span>
- <span style="background-color:rgb(237,220,195);">컴포넌트 통합 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">인터페이스 관련 결함 수정이 코드 저장소에 체크인(check-in)됐을 때 해당 수정을 확인하기 위한 테스트 설계</span>
- <span style="background-color:rgb(237,220,195);">시스템 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">특정 워크플로우에 속하는 화면 중 하나만 변경되더라도 해당 워크플로우에 대한 모든 테스트 실행</span>
- <span style="background-color:rgb(237,220,195);">시스템 통합 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">신용 점수 마이크로서비스에 대한 지속적인 개발의 일환으로 해당 마이크로서비스와 상호작용하는 애플리케이션에 대한 테스트를 매일 재실행</span>
- <span style="background-color:rgb(237,220,195);">인수 테스팅</span>에 적용, <span style="background-color:rgb(242,213,214);">인수 테스팅에서 발견된 결함이 수정되면 기존에 불합격했던 모든 테스트를 재실행</span>

위에서 모든 레벨에 모든 테스트 유형을 적용한 예제를 제공했지만, 모든 소프트웨어가 모든 레벨에 모든 테스트 유형을 적용해야 하는 것은 아니다. 그러나 각 레벨에서 가능한 테스트 유형을 수행하는 것이 중요하며 특히 해당 테스트 유형이 처음으로 발생하는 첫 레벨에서 수행하는 것이 중요하다.

# 2.4 유지보수 테스팅 (Maintenance Testing)
{: .notice--warning .text-center}

소프트웨어와 시스템이 생산 환경으로 배포되고 나면 유지보수가 필요하다. 배포된 소프트웨어와 시스템에 대한 다양한 변경은 거의 필연적으로 발생한다. 이런 변경으로는 운영 중 발견한 결함 수정, 신규 기능 추가, 기존 기능의 삭제나 개선 등이 있다. 유지보수는 컴포넌트나 시스템의 수명 동안 그것의 비기능 품질 특성을 보존 혹은 개선하기 위해서도 필요하다. 특히 성능 효율성(performance efficiency), 호환성(compatibility), 신뢰성(reliability), 보안성(security), 이식성(portability)에 대한 보존이나 개선이 필요하다.<br>
유지보수의 일환으로 변경이 이루어지게 되면, 변경의 성공 여부를 평가하고 시스템의 변경되지 않은 부분(많은 경우 시스템의 대부분)에서 부작용(예: 리그레션)의 발생 여부를 확인하기 위한 유지보수 테스팅을 수행해야 한다.<br>
유지보수는 계획된 릴리스나 계획되지 않은 릴리스(핫픽스)와 연관되어 발생할 수 있다.<br>
유지보수 릴리스는 그것의 범위에 따라 다양한 테스트 유형을 활용한 복수의 테스트 레벨에서의 유지보수 테스팅이 필요할 수 있다.<br>
유지보수 테스팅의 범위는 다음과 같은 요소의 영향을 받는다:
- 변경의 리스크 수준, 예를 들어, 변경된 소프트웨어 영역이 다른 컴포넌트나 시스템과 통신하는 정도
- 기존 시스템의 규모
- 변경의 규모

## 2.4.1 유지보수가 필요한 상황 (Triggers for Maintenance)
{: .notice--success}

<span style="color:green">(K2) 유지보수 테스팅이 필요한 상황을 요약할 수 있다.</span>

계획됐든 계획되지 않았든, 소프트웨어 유지보수, 즉 유지보수 테스팅이 이루어지게 되는 원인은 다양하다.<br>
유지보수의 계기는 다음과 같이 분류할 수 있다:
- 개선을 위한 변경(modification), 계획된 확장(예: 릴리스 기반), 수정 혹은 긴급 변경, 운영 환경 변경(예: 계획된 운영 시스템이나 데이터베이스 업그레이드), 상용 소프트웨어 업그레이드, 결함 및 취약성을 위한 패치 등
- 이관(migration)을 위한 변경, 하나의 플랫폼에서 다른 플랫폼으로 이관할 때, 변경된 소프트웨어뿐만 아니라 신규 환경에 대한 운영 테스트가 필요할 수 있거나 또는 유지보수하고 있는 시스템에 이관하는 다른 애플리케이션의 데이터를 위한 데이터 전환 테스트 등
  + 단종(retirement), 애플리케이션의 수명이 다할 때 등, 애플리케이션이나 시스템이 단종될 때 데이터 이관이나 장시간의 데이터 유지가 필요하면 보관처리에 대한 테스팅이 필요할 수 있다.
  + 장시간의 보관이 필요한 경우 차후 복원/회수 절차에 대한 테스팅이 필요할 수 있다.
  + 여전히 서비스하고 있는 기능이 있다면, 해당 기능이 정상 동작할거라는 확신을 얻기 위한 리그레션 테스팅이 필요할 수 있다.

사물 인터넷(IoT) 시스템에서는 유지보수 테스팅이 완전히 새롭거나 개선된 사물, 예를 들어 하드웨어 기기 및 소프트웨어 서비스를 전체 시스템에 추가하는 것을 계기로 발생할 수 있다. 이런 시스템에 대한 유지보수 테스팅은 다양한 레벨(예: 네트워크 레벨, 애플리케이션 레벨)에서의 통합 테스팅과 보안 측면, 특히 개인 정보와 관련된 측면에 집중하게 된다.

## 2.4.2 유지보수를 위한 영향도 분석 (Impact Analysis for Maintenance)
{: .notice--success}

<span style="color:green">(K2) 유지보수 테스팅에서 영향도 분석의 역할을 기술할 수 있다.</span>

<span style="background-color:rgb(207,228,207);">영향도 분석</span>은 <span style="background-color:rgb(237,220,195);">유지보수 릴리스에 포함된 변경을 평가해서, 의도한 결과뿐만 아니라 변경으로 인해 발생할 수 있는 예견된 부작용을 식별하고, 변경의 영향을 받는 시스템 영역을 식별하기 위해 실시</span>한다. 영향도 분석은 <span style="background-color:rgb(237,220,195);">변경이 기존 테스트에 미치는 영향을 식별하기 위해 사용</span>할 수 있다. 부작용과 영향 받은 시스템 영역에 대해서는, <u>필요한 경우 변경의 영향을 받는 기존 테스트를 업데이트해서 리그레션 테스트를 수행</u>할 필요가 있다.<br>
시스템의 다른 영역에 발생할 수 있는 영향을 기반으로 변경을 적용하기 전에 영향도 분석을 실시할 수 있으며, 이런 경우 변경을 적용할지 여부를 판단하는 데 도움을 준다.<br>
다음과 같은 상황에서는 영향도 분석이 어려울 수 있다:
- 명세(예: 비즈니스 요구사항, 사용자 스토리, 아키텍처)가 너무 오래 됐거나 없는 경우
- 테스트 케이스가 문서화되어 있지 않거나 너무 오래된 경우
- 테스트와 테스트 베이시스 간 양방향 추적성이 유지되지 않은 경우
- 도구 활용이 적거나 없는 경우
- 연관된 인원이 도메인이나 시스템 지식을 가지고 있지 않은 경우
- 소프트웨어의 개발 중 유지보수성에 충분히 신경을 쓰지 못한 경우

# ● 용어
{: .notice .text-center}

<details>
<summary>Keywords</summary>
<div markdown="1">

- 인수 테스팅(acceptance testing):<br>
참조 : ISO 24765<br>
연관 항목 : 사용자 인수 테스팅(user acceptance testing)<br>
시스템이 사용자의 필요 및 요구사항, 비즈니스 프로세스 측면에서 인수 조건을 만족하는지 확인하고 사용자, 고객, 기타 권한을 지닌 사람이 시스템의 인수 여부를 결정하기 위해 수행 하는 공식 테스팅

- 알파 테스팅(alpha testing): 개발 조직이 아닌 제3자가 개발자의 테스트 환경에서 수행하는 시뮬레이션 또는 실제 운영 테스팅

- 베타 테스팅(beta testing):<br>
유의어 : 필드 테스팅(field testing)<br>
개발 조직이 아닌 제3자가 외부 환경에서 수행하는 시뮬레이션 또는 실제 운영 테스팅

- 변경관련 테스팅(change-related testing)

- 상용 소프트웨어(COTS, Commercial Off-The-Shelf)

- 컴포넌트 통합 테스팅(component integration testing):<br>
유의어 : 링크 테스팅(link testing)<br>
통합된 컴포넌트 간의 인터페이스와 상호작용에서의 결함을 노출시키기 위한 테스팅

- 컴포넌트 테스팅(component testing):<br>
참조 : ISO 24765<br>
유의어 : 모듈 테스팅(module testing), 단위 테스팅(unit testing)<br>
개별 하드웨어나 소프트웨어 컴포넌트에 대한 테스팅

- 확인 테스팅(confirmation testing):<br>
유의어 : 재테스팅(re-testing)<br>
결함 수정 후 결함으로 인한 장애가 더 이상 발생하지 않는지 확인하는 동적 테스팅

- 계약 인수 테스팅(contractual acceptance testing): 시스템이 계약상의 요구사항을 충족시키는지 검증하는 인수 테스팅

- 기능 테스팅(functional testing):<br>
참조 : ISO 24765<br>
연관 항목 : 블랙박스 테스팅(black-box testing)<br>
컴포넌트나 시스템이 기능 요구사항(functional requirements)을 어느 정도 준수하고 있는지 평가하기 위해 실시하는 테스팅

- 영향도 분석(impact analysis):<br>
참조 : ISO 24765<br>
변경을 완료하는 데 필요한 자원의 예상 견적과 변경에 의해 영향받는 모든 작업 산출물의 식별

- 통합 테스팅(integration testing):<br>
연관 항목 : 컴포넌트 통합 테스팅(component integration testing), 시스템 통합 테스팅 (system integration testing)<br>
통합된 컴포넌트나 시스템 간의 인터페이스 및 상호작용에서 결함을 발견하기위해 수행하는 테스팅

- 유지보수(maintenance):<br>
참조 : ISO 14764<br>
결함을 수정하거나, 품질 속성을 개선하거나, 변경된 환경에 적응하고자 출시 후 컴포넌트나 시스템을 수정하는 프로세스

- 유지보수성(maintainability):<br>
참조 : ISO 25010<br>
유지보수자가 컴포넌트나 시스템을 의도대로 수정할 수 있는 정도

- 유지보수 테스팅(maintenance testing): 운영 중인 시스템에 대한 변화, 또는 운영 중인 시스템에 미치는 환경 변화의 영향에 대한 테스팅

- 비기능 테스팅(non-functional testing): 컴포넌트나 시스템이 비기능 요구사항을 준수하는지 확인하고자 수행하는 테스팅

- 운영 인수 테스팅(operational acceptance testing):<br>
연관 항목 : 운영 테스팅(operational testing)<br>
유의어 : 생산 인수 테스팅(production acceptance testing)<br>
인수 테스트 단계에서의 운영 테스팅. 일반적으로 운영 및 시스템 관리 직원에 의해 (시뮬레이션 된) 운영 환경에서 수행되며, 주로 복구성, 리소스-동작, 설치성, 기술 준수성 등 운영상의 측면에 중점을 두고 있음

- 리그레션 테스팅(regression testing): 개선을 위한 소프트웨어 수정 후 변경 결과로 소프트웨어의 변경되지 않은 영역에서 결함이 발견되거나 유입되지 않았는지 확인하기 위해 이전 테스트 구성 요소 또는 시스템에 대해 진행하는 테스팅

- 규정 인수 테스팅(regulatory acceptance testing): 시스템이 관련 법규나 정책, 규정을 준수하는지 확인하기 위해 수행하는 인수 테스팅

- 순차적 개발 모델(sequential development model): 전체 시스템이 서로 겹치지 않는 여러 개의 개별적, 연속적 단계를 통해 개발되는 개발 수명주기 모델의 한 유형

- 시스템 통합 테스팅(system integration testing): 시스템의 통합과 상호작용을 테스팅하는 것

- 시스템 테스팅(system testing):<br>
참조 : Hetzel<br>
통합 시스템이 제시된 요구사항을 충족하는지 확인하는 테스팅

- 테스트 환경(test environment):<br>
참조 : ISO 24765<br>
유의어 : 테스트 베드(test bed), 테스트 리그(test rig)<br>
테스트 수행에 필요한 하드웨어, 계측, 시뮬레이터, 소프트웨어 도구 그리고 기타 지원 요소를 포함하고 있는 환경

- 테스트 레벨(test level):<br>
참조 : ISO 29119<br>
유의어 : 테스트 단계(test stage) 테스트 프로세스 중의 특정 예시 단계

- 테스트 유형(test type):<br>
참조 : TMap<br>
컴포넌트나 시스템의 특성을 목표로 하는 구체적인 테스트 목적에 기반한 테스트 활동의 집합

- 사용자 인수 테스팅(user acceptance testing):<br>
연관 항목 : 인수 테스트(acceptance test)<br>
자신의 필요, 요구사항, 비즈니스 프로세스 등에 맞춰 예상된 사용자가 실제 또는 시뮬레이션된 운영 환경에서 수행하는 인수 테스팅

- 화이트박스 테스팅(white-box testing):<br>
유의어 : 투명 박스 테스팅(clear-box testing), 코드 기반 테스팅(code-based testing), 유리 박스 테스팅(glass-box testing), 논리 커버리지 테스팅(logic-coverage testing), 논리 주도 테스팅(logic-driven testing), 구조적 테스팅(structural testing), 구조 기반 테스팅(structure-based testing)<br>
컴포넌트나 시스템의 내부구조 분석에 기반한 테스팅

- 상호운용성(interoperability):<br>
참조 : ISO 25010<br>
둘 이상의 컴포넌트나 시스템이 서로 정보를 교환하고, 교환된 정보를 얼마나 잘 사용할 수 있는지의 정도

- 상호운용성 테스팅(interoperability testing):<br>
연관 항목 : 기능성 테스팅(functionality testing)<br>
유의어 : 호환성 테스팅(compatibility testing)<br>
소프트웨어 제품의 상호운용성을 확인하는 테스팅

- 유스케이스(use case): 액터(actor)와 컴포넌트 또는 시스템 사이에 실제 결과를 가진 일련의 상호작용. 여기서 액터는 사용자 또는 시스템과 정보 교환이 가능한 어떤 것이든 될 수 있음

- 시스템(system):<br>
참조 : ISO 24765<br>
특정한 기능이나 기능 집합을 달성하기 위해 조직된 상호작용 요소들의 집합

- 강건성(robustness):<br>
참조 : ISO 24765<br>
연관 항목 : 오류 허용성(error-tolerance), 결점 허용성(fault-tolerance)<br>
유효하지 않은 입력값 또는 스트레스 요소가 많은 환경 조건에서도 컴포넌트나 시스템이 올바르게 기능할 수 있는 정도



</div>
</details>

# ● 샘플문제
{: .notice--danger .text-center}

A - Q9. 사용자 인수 테스팅 중에 화이트박스 테스팅을 어떤 방식으로 적용할 수 있는가?
- a. 통합된 시스템 간에 많은 양의 데이터 전송이 가능한지 확인한다.
- b. 모든 코드 구문과 결정 경로가 실행됐는지 확인한다.
- c. 모든 업무 프로세스 흐름을 확인했는지 점검한다.
- d. 웹페이지의 모든 경로(navigations)를 확인한다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-2.3.2 (K1) 기능, 비기능, 화이트박스 테스트가 모든 테스트 레벨에서 이루어질 수 있음을 인지할 수 있다.
- a. 오답- 통합 테스팅과 관련이 있다.
- b. 오답- 컴포넌트 테스팅과 관련이 있다.
- c. 정답- 인수 테스팅에서 테스트는 기능적 요구사항 문서에 정의된 모든 워크플로우를 다루도록 설계된다.
- d. 오답- 시스템 테스팅과 관련이 있다.

</div>
</details>

---

A - Q10. 다음 컴포넌트 테스팅과 시스템 테스팅을 비교한 설명 중 맞는 것은?
- a. 컴포넌트 테스팅은 소프트웨어 모듈, 프로그램 객체, 테스트 가능 단위로 구분된 클래스의 기능을 확인하는 것이고, 시스템 테스팅은 컴포넌트 간 인터페이스와 시스템의 각 부분 간 상호작용을 확인하는 것이다.
- b. 컴포넌트 테스팅의 테스트 케이스는 일반적으로 컴포넌트 명세서, 설계 명세서 또는 데이터 모델에서 도출하지만, 시스템 테스팅의 테스트 케이스는 요구사항 명세서나 유스케이스로부터 도출한다.
- c. 컴포넌트 테스팅은 기능적 측면에만 초점을 맞추지만 시스템 테스팅은 기능과 비기능 측면 모두에 초점을 맞춘다.
- d. 컴포넌트 테스팅은 테스터의 임무지만 시스템 테스팅은 일반적으로 시스템 사용자들이 수행한다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-2.2.1 (K2) 목적, 테스트 베이시스, 대표적 결함과 장애, 접근법과 책임의 관점에서 다양한 테스트 레벨을 비교할 수 있다.
- a. 오답- 시스템 테스팅은 컴포넌트 간 인터페이스와 시스템의 각 부분 간 상호작용을 테스트하지 않는다. 이는 통합 테스트의 목표이다.
- b. 정답- 실러버스 2.2.1: 컴포넌트 테스팅에서 테스트 베이시스로 사용하는 산출물의 예로, 상세 설계, 코드, 데이터 모델, 컴포넌트 명세 등이 있다.<br> 
실러버스 2.2.3: 시스템 테스팅에서 테스트 베이시스로 사용하는 산출물의 예로, 시스템 및 소프트웨어 요구사항 명세서(기능 및 비기능), 유스케이스 등이 있다.
- c. 오답- 컴포넌트 테스팅은 기능적 측면에만 중점을 두지 않는다.
- d. 오답- 시스템 테스팅은 보통 (독립적인) 테스터가 수행하는 반면, 컴포넌트 테스트는 개발자가 수행하기도 한다.

</div>
</details>

---

A - Q11. 다음 중 리그레션 테스팅과 확인 테스팅에 대한 설명으로 맞는 것은?
- a. 리그레션 테스팅의 목적은 수정사항이 문제없이 구현됐는지 점검하는 것이고, 확인 테스팅의 목적은 수정사항에 따른 부작용이 없는지 확인하는 것이다.
- b. 리그레션 테스팅의 목적은 의도하지 않은 부작용을 찾는 것이고, 확인 테스팅의 목적은 시스템이 새로운 환경에서 잘 동작하는지 점검하는 것이다.
- c. 리그레션 테스팅의 목적은 의도하지 않은 부작용을 찾는 것이고, 확인 테스팅의 목적은 발견된 결함이 수정됐는지 점검하는 것이다.
- d. 리그레션 테스팅의 목적은 신규 기능이 동작하는지 점검하는 것이고, 확인 테스팅의 목적은 원래의(original) 결함이 수정됐는지 확인하는 것이다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-2.3.3 (K2) 확인 테스팅과 리그레션 테스팅의 목적을 비교할 수 있다.
- a. 오답- 리그레션 테스팅으로 구현이 잘 됐는지 점검하지 않으며, 확인 테스팅으로 부작용을 점검하지도 않는다.
- b. 오답- 확인 테스팅에 대한 설명 부분이 리그레션 테스팅을 설명하고 있다.
- c. 정답- 오답의 이유 참조.
- d. 오답- 신규 기능을 테스트하는 것은 리그레션 테스팅이 아니다.

</div>
</details>

---

A - Q12. 다음 중 점진적 개발 모델을 가장 잘 정의한 것은?
- a. 요구사항 정의, 소프트웨어 설계 및 테스팅은 각각의 단계에 시스템 조각이 추가되는 단계에서 수행한다.
- b. 개발 프로세스 단계는 이전 단계를 완료할 때 시작해야 한다.
- c. 테스팅은 개발을 완료한 후 수행하는 별도의 단계로 간주한다.
- d. 테스팅을 개발활동의 일환으로 추가한다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-2.1.1 (K2) 소프트웨어 개발 수명주기에서의 소프트웨어 개발 활동과 테스트 활동의 관계를 설명할 수 있다.
- a. 정답- 점증적 개발은 요구사항 수립, 설계, 빌드 및 시스템에 대한 테스팅을 분리된 작업으로 수행한다.
- b. 오답- 순차적 모델에 대한 설명이다.
- c. 오답- 폭포수 모델에 대한 설명이다.
- d. 오답- 점진적 개발에서 테스팅만 수행하는 반복주기는 없다.

</div>
</details>

---

A - Q13. 다음 중 유지보수 테스팅을 유발하는 요인이 아닌 것은?
- a. 소프트웨어의 유지보수성을 테스트하기로 했다.
- b. 새로운 운영 플랫폼으로 시스템을 마이그레이션한 후 테스트하기로 했다.
- c. 저장된 데이터가 검색 가능한지 테스트하기로 했다.
- d. “핫 픽스” 후 테스트하기로 했다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-2.4.1 (K2) 유지보수 테스팅이 필요한 상황을 요약할 수 있다.
- a. 정답- 유지보수(maintenance) 테스팅이 아니라 유지보수성(maintainability) 테스팅이다.
- b. 오답- 유지보수 테스팅을 유발하는 요인이다. 변경된 소프트웨어뿐 아니라 새로운 환경에 대한 운영 테스트
- c. 오답- 유지보수 테스팅을 유발하는 요인이다. 장기간 보관된 데이터의 복원/검색 절차 테스팅
- d. 오답- 유지보수 테스팅을 유발하는 요인이다. 실질적 장애를 일으키는 긴급 결함을 고치기 위해 전달된 소프트웨어 제품을 수정

</div>
</details>

---

B - Q9. 다음은 소프트웨어 개발 수명주기에서 소프트웨어 개발 활동과 테스트 활동의 관계를 설명한 것이다:
1. 각 개발 활동에 대응하는 테스팅 활동이 있어야 한다.
2. 문서의 최종 버전이 작성되면 리뷰를 시작해야 한다.
3. 테스트 설계와 구현은 대응하는 개발 단계에 시작해야 한다.
4. 테스팅 활동은 소프트웨어 개발 수명주기의 초기 단계에 시작해야 한다.

다음 중 참인 설명과 거짓인 설명을 올바르게 분류한 것은?
- A. 참 – 1,2; 거짓 – 3,4
- B. 참 – 2,3; 거짓 – 1,4
- C. 참 – 1,2,4; 거짓 – 3
- D. 참 – 1,4; 거짓 – 2,3

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-2.1.1 (K2) 소프트웨어 개발 수명주기에서의 소프트웨어 개발 활동과 테스트 활동의 관계를 설명할 수 있다.<br>
각 문장을 살펴보자:
1. 각 개발 활동에 대응하는 테스팅 활동이 있어야 한다. – 참
2. 문서의 최종 버전을 사용할 수 있게 되면 리뷰를 시작해야 한다. - 거짓 : 문서의 초기 버전이 작성되면 리뷰를 시작한다.
3. 테스트 설계와 구현은 대응하는 개발 단계에 시작해야 한다. - 거짓 : 테스트 구현이 아니라, 테스트 분석과 설계야말로 대응하는 개발 단계에서 시작해야 한다.
4. 테스팅 활동은 소프트웨어 개발 수명주기의 초기 단계에 시작해야 한다. – 참

따라서 D 가 정답이다.

</div>
</details>

---

B - Q10. 다음과 같은 내용으로 테스팅을 수행했다:
- 인터페이스 명세(interface specifications)를 기반으로 함
- 통신(communication) 장애를 찾는 데 초점을 맞춤
- 테스트 접근 방법으로 기능 및 구조적 테스트 유형을 사용함

위의 내용으로 볼 때, 다음 중 어느 테스트 레벨을 수행했다고 볼 수 있는가?
- A. 통합 테스팅
- B. 인수 테스팅
- C. 시스템 테스팅
- D. 컴포넌트 테스팅

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-2.2.1 (K2) 목적, 테스트 베이시스, 대표적 결함과 장애, 접근법과 책임의 관점에서 다양한 테스트 레벨을 비교할 수 있다.
- ‘인터페이스 명세를 기반으로 테스팅을 수행함’ - 통신 프로토콜 명세와 함께 인터페이스 명세는 컴포넌트 통합 테스팅의 테스트 베이시스에 포함되며, 이는 다른 테스트 레벨에는 포함되지 않는다.
- ‘통신 장애를 찾는데 초점을 맞춘 테스팅’ - 테스트한 컴포넌트 간 통신 장애는 컴포넌트 통합 테스팅에서 발견되는 일반적인 장애 유형이며, 이는 다른 테스트 레벨에는 포함되지 않는다.
- ‘테스트 접근 방법으로는 기능 및 구조적 테스트 유형을 사용함’ - 기능 및 구조적 테스트 유형은 모두 컴포넌트 통합 테스팅에서 사용 가능하며 다른 테스트 레벨에서도 사용한다. 다만 실러버스에서는 시스템 테스팅에서만 명시적으로 언급한다.

따라서, A 가 정답이다.

</div>
</details>

---

B - Q11. 다음 중 테스트 유형과 테스트 레벨에 대한 설명으로 옳은 것은?
- A. 기능 및 비기능 테스팅은 시스템과 인수 테스트 레벨에서 수행할 수 있고, 화이트-박스 테스팅은 컴포넌트와 통합 테스팅에서만 수행할 수 있다.
- B. 기능 테스팅은 모든 레벨에서 수행 가능하나, 화이트-박스 테스팅은 컴포넌트 테스팅에서만 수행한다.
- C. 모든 테스트 레벨에서 기능, 비기능 및 화이트-박스 테스팅을 수행할 수 있다.
- D. 기능 및 비기능 테스팅은 모든 레벨에서 수행 가능하나, 화이트-박스 테스팅은 컴포넌트와 통합 테스팅에서만 수행한다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-2.3.2 (K1) 기능, 비기능, 화이트박스 테스트가 모든 테스트 레벨에서 이루어질 수 있음을 인지할 수 있다.
- A. 오답- 어떤 테스트 유형(기능, 비기능, 화이트-박스)이든지 모든 테스트 레벨에서 수행할 수 있다. 따라서, 시스템과 인수 테스트 레벨에서 기능 및 비기능 테스팅을 수행한다는 것은 맞지만, 화이트-박스 테스팅을 컴포넌트와 통합 테스팅에서만 수행한다는 것은 틀린 설명이다.
- B. 오답- 어떤 테스트 유형(기능, 비기능, 화이트-박스)이든지 모든 테스트 레벨에서 수행할 수 있다. 따라서, 화이트-박스 테스팅을 컴포넌트 테스팅에서만 수행한다는 것은 틀린 설명이다.
- C. 정답- 어떤 테스트 유형(기능, 비기능, 화이트-박스)이든지 모든 테스트 레벨에서 수행할 수 있다.
- D. 오답- 어떤 테스트 유형(기능, 비기능, 화이트-박스)이든지 모든 테스트 레벨에서 수행할 수 있다. 따라서 화이트-박스 테스팅을 컴포넌트 테스팅과 통합 테스팅에서만 수행한다는 것은 틀린 설명이다.

</div>
</details>

---

B - Q12. 다음 설명 중 확인 테스팅과 리그레션 테스팅의 목적을 가장 잘 비교한 것은?
- A. 리그레션 테스팅의 목적은 이전에 수행한 모든 테스트가 여전히 문제없이 수행되는지 확인하는 것이며, 확인 테스팅의 목적은 시스템 한 부분의 수정사항이 다른 부분에 영향을 주지 않았는지 확인하는 것이다.
- B. 확인 테스팅의 목적은 전에 찾은 결함이 수정되었는지 확인하는 것이고, 리그레션 테스팅의 목적은 수정에 의해 시스템의 다른 부분에 영향이 없는지 확인하는 것이다.
- C. 리그레션 테스팅의 목적은 시스템 일부의 변경이 다른 부분에 문제를 일으키지 않는지 확인하는 것이고, 확인 테스팅의 목적은 이전에 수행했던 테스트가 같은 결과를 내는지 확인하는 것이다.
- D. 확인 테스팅의 목적은 시스템이 성공적으로 변경되었는지 확인하는 것이고, 리그레션 테스팅의 목적은 이전에 통과하지 못한 테스트가 이제는 잘 되는지 확인하기 위해 수행하는 것이다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-2.3.3 (K2) 확인 테스팅과 리그레션 테스팅의 목적을 비교할 수 있다.
- A. 오답- 리그레션 테스팅에 대한 설명은 대체로 맞지만 확인 테스팅(결함이 수정되었는지 확인)에 대한 설명은 틀렸다.
- B. 정답- 확인과 리그레션 테스팅에 대한 설명 모두 실러버스의 내용과 일치한다.
- C. 오답- 리그레션 테스팅에 대한 설명은 대체로 맞지만 확인 테스팅은 이전에 실패했던 케이스들이 이제는 잘 동작하는지 확인하는 것이므로 확인 테스팅(같은 결과를 얻기 위해 이전에 수행한 테스트를 모두 다시 수행)에 대한 설명은 틀렸다.
- D. 오답- 확인 테스팅에 대한 설명은 대체로 맞지만 리그레션 테스팅(이전에 실패한 테스트를 다시 수행)에 대한 설명은 틀렸다(확인 테스팅에 대한 좀 더 상세한 설명이다).

</div>
</details>

---

B - Q13. 다음 중 유지보수에서 영향도 분석(impact analysis)의 역할을 올바르게 설명한 것은?
- A. 영향도 분석은 유지보수 시스템의 변경이 그만한 가치가 있는지 결정할 때 사용한다.
- B. 영향도 분석은 데이터를 유지보수 시스템에 마이그레이션하는 방법을 파악할 때 사용한다.
- C. 영향도 분석은 어느 핫픽스가 사용자에게 가장 유용한지 결정할 때 사용한다.
- D. 영향도 분석은 새로운 유지보수 테스트 케이스의 효과성을 판단할 때 사용한다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-2.4.2 (K2) 유지보수 테스팅에서 영향도 분석의 역할을 기술할 수 있다.
- A. 정답- 영향도 분석은 수정에 영향을 받는 시스템 영역을 파악할 때 사용하며, 영향의 정도(예: 필요한 리그레션 테스팅)는 실러버스(2.4.2)에 따르면 변경이 그만한 가치가 있는지 결정할 때 사용할 수 있다.
- B. 오답- 데이터 마이그레이션 테스팅이 유지보수 테스팅(전환 테스팅 참조)의 일부이기는 하나, 영향도 분석으로 이를 어떻게 수행할지를 알 수는 없다.
- C. 오답- 영향도 분석은 시스템의 어느 부분이 변경의 영향을 받는지 보여주므로 시스템에 미치는 영향의 측면에서 다양한 핫픽스의 차이점을 보여줄 수 있지만, 사용자에게 변경 사항의 가치를 알려주지는 않는다.
- D. 오답- 영향도 분석은 시스템의 어느 부분이 변경의 영향을 받는지 보여주지만, 테스트 케이스의 효과성에 대한 지표를 제공할 수는 없다.

</div>
</details>

---

C - Q9. 당신은 시스템의 컴포넌트 간 인터페이스에 있을 수 있는 잠재적 네트워크 병목현상을 찾기 위해 성능 테스트를 수행하고 있다.<br>
다음 중 이 테스트를 설명하고 있는 것은?
- a. 통합 테스트 레벨에서의 기능 테스트
- b. 통합 테스트 레벨에서의 비기능 테스트
- c. 컴포넌트 테스트 레벨에서의 기능 테스트
- d. 컴포넌트 테스트 레벨에서의 비기능 테스트

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-2.3.2, K1
- a. 오답- 이 테스트는 통합 테스트 내용과 맞지만, 이는 비기능 테스트이다.
- b. 정답- 이 테스트는 통합 테스트 설명과 일치하며 비기능 테스트이다.
- c. 오답- 이 테스트는 컴포넌트 테스트 설명과 일치하지 않고 기능 테스트도 아니다.
- d. 오답- 이 테스트는 비기능 테스트이지만, 컴포넌트 테스트의 설명과 일치하지 않는다.

</div>
</details>

---

C - Q10. 다음 중 옳은 것은?
- a. 영향도 분석은 유지보수 테스팅에서 확인 테스팅에 유용하다.
- b. 확인 테스팅은 시스템 설계에서 리그레션 테스팅에 유용하다.
- c. 영향도 분석은 유지보수 테스팅에서 리그레션 테스팅에 유용하다.
- d. 확인 테스팅은 유지보수 테스팅에서 영향도 분석에 유용하다.

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-2.4.2, K2
- a. 오답- 유지보수 테스팅에서 영향도 분석이 중요하지만, 확인 테스팅을 위한 것은 아니다. 확인 테스팅은 결함 수정이나 다른 변경에 따른 의도된 영향에 대한 것이다.
- b. 오답- 확인과 리그레션 테스팅은 두 개의 분리된 활동으로 확인 테스팅은 시스템 설계의 일부가 아니다.
- c. 정답- 영향도 분석은 유지보수 테스팅에서 리그레션 테스트 선택을 위해 사용할 수 있다.
- d. 오답- 일반적으로 유지보수 테스팅 도중 확인 테스팅을 수행하지만, 확인 테스팅은 영향도 분석의 일부가 아니다.

</div>
</details>

---

C - Q11. 다음과 같이 테스트 레벨에 따라 집중할 수 있는 결함의 유형을 고려할 때:
1. 별도로 테스트할 수 있는 모듈이나 대상의 결함
2. 결함 발견에 중점을 두지 않음
3. 인터페이스와 상호작용에서의 결함
4. 전체 테스트 대상에서의 결함

다음 중 파운데이션 실러버스에 나오는 테스트 레벨과 위의 결함 유형을 가장 잘 연결한 것은?

- a. 1- 성능 테스트, 2- 컴포넌트 테스트, 3- 시스템 테스트, 4- 인수 테스트
- b. 1- 컴포넌트 테스트, 2- 인수 테스트, 3- 시스템 테스트, 4- 통합 테스트
- c. 1- 컴포넌트 테스트, 2- 인수 테스트, 3- 통합 테스트, 4- 시스템 테스트
- d. 1- 통합 테스트, 2- 시스템 테스트, 3- 컴포넌트 테스트, 4- 인수 테스트

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-2.2.1, K2
성능 테스팅은 테스트 레벨이 아닌 테스트 유형 중 하나이다. 컴포넌트 테스팅은 테스트 가능한 분리된 모듈이나 오브젝트의 결함에, 통합 테스팅은 인터페이스 및 상호작용에서의 결함에, 시스템 테스팅은 전체 테스트 대상의 결함에 집중하지만, 인수 테스팅은 일반적으로 결함을 찾는 것에 중점을 두지는 않는다.

따라서, 정답은 C이다.

</div>
</details>

---

C - Q12. 대량 판매 시장용 운영체제 소프트웨어 제품을 x86 시리즈 프로세서를 장착한 모든 PC 하드웨어에서 실행 가능하게 설계했다. 당신은 이러한 사양의 여러 PC를 지원하는 것과 관련된 결함을 찾고 주요 PC 브랜드 제품에서 정상적으로 동작하는지 확인하기 위해 테스트를 수행하고 있다.<br>
당신은 어떤 테스트를 수행하고 있는가?
- a. 성능 테스트 (Performance test)
- b. 프로세서 테스트 (Processor test)
- c. 기능 테스트 (Functional test)
- d. 이식성 테스트 (Portability test)

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-2.3.1, K2
- a. 오답- 기술된 테스트는 비기능 테스트이며 성능테스트가 아닌 이식성 테스트이다.
- b. 오답- 프로세서 테스트는 정의된 테스트 유형이 아니다.
- c. 오답- 이 테스트는 비기능 테스트 중 이식성 테스트이다.
- d. 정답- 지원하는 장비에 대한 테스팅은 비기능 테스트, 특히 이식성 테스트 이다.

</div>
</details>

---

C - Q13. 애자일 개발을 수행하는 도중, 제품 담당자는 특정 에픽(epic) 내 대부분의 사용자 스토리에 적용되지만 이전에는 알지 못했던 규제 관련 요구사항을 발견했다. 사용자 스토리는 소프트웨어 동작의 필수 변경을 위해 업데이트되었다. 팀 내 개발자들은 요구사항에 따라 코드를 수정했다.<br>
이 팀의 테스터로서 당신은 어떤 테스트를 수행해야 하는가?
- a. 확인 테스트 (Confirmation tests)
- b. 리그레션 테스트 (Regression tests)
- c. 기능 테스트 (Functional tests)
- d. 변경 관련 테스트 (Change-related tests)

<details>
<summary><span style="color:red">Answer</span></summary>
<div markdown="1">

FL-2.3.3, K2
동작(behavior)의 변경은 변경 관련 테스트 실행의 필요에 따라 기능적 또는 비기능적일 수 있으며, 그 중 일부는 확인 테스트, 나머지는 리그레션 테스트이다.<br>
따라서 정답은 d이다.

</div>
</details>

# ● 자료참고
{: .notice--info .text-center}

[실러버스 본문](http://www.kstqb.org/board_skin/board_view.asp?idx=426&page=1&bbs_code=4&key=0&word=&etc=ISTQB){: .btn .btn--info}
[실러버스 용어](http://www.kstqb.org/board_skin/board_view.asp?idx=342&page=2&bbs_code=4&key=0&word=&etc=ISTQB){: .btn .btn--info}
[샘플문제](http://www.kstqb.org/board_skin/board_view.asp?idx=433&page=2&bbs_code=5&key=0&word=&etc=){: .btn .btn--info}