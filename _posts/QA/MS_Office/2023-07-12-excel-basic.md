---
title: "엑셀 기본"
excerpt: "실무에서 필요한 엑셀 기본기"
categories: MS_Office
tag: [MS_Office, Excel]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# 채우기
{: .notice--warning .text-center}

기준이 되는 셀을 선택하고 해당 셀 우측 하단 모서리에 커서를 올려 +폼으로 바꾼 뒤 드래그

<img src="/img/MS_Office/2023-07-12-excel-basic/Fill.png"/>

# 메모
{: .notice--warning .text-center}

- 메모 삽입: 셀 우클릭 → 메모 삽입(숏컷: Shift + F2)
- 메모 삭제: 메모 셀 우클릭 → 메모 삭제
- 메모 표시/숨기기: 메모 셀 우클릭 → 메모 표시/숨기기
- 메모 서식: 메모 선택 후 사이즈 UI에 커서를 올려 우클릭 → 메모 서식
- 전체 메모 삭제: Ctrl + Shift + O → 메모 셀 우클릭 → 메모 삭제

# 세로 쓰기
{: .notice--warning .text-center}

홈 리본 메뉴 → 맞춤 → 방향 → 세로 쓰기

<img src="/img/MS_Office/2023-07-12-excel-basic/VerticalText.png"/>

# 텍스트 조정
{: .notice--warning .text-center}

<details>
<summary>Windows</summary>
<div markdown="1">

temp.자동 줄 바꿈
temp.셀에 맞춤

</div>
</details>

<details>
<summary>Mac</summary>
<div markdown="1">

<img src="/img/MS_Office/2023-07-12-excel-basic/TextAutoAdjustMac.png"/>

</div>
</details>

# 수식 입력 및 채우기
{: .notice--warning .text-center}

# 빠른 채우기
{: .notice--warning .text-center}

<details>
<summary>Mac</summary>
<div markdown="1">

기준이 될 셀과 채울 셀을 선택 후 홈 리본 메뉴 → 채우기 → 빠른 채우기
(참조할 셀이 좌측에 위치해야 함)

<img src="/img/MS_Office/2023-07-12-excel-basic/AutoFillMac.png"/>

</div>
</details>

# 내용 지우기와 삭제
{: .notice--warning .text-center}

<details>
<summary>Mac</summary>
<div markdown="1">

내용 지우기는 삭제와 달리 서식이 남는다.

<img src="/img/MS_Office/2023-07-12-excel-basic/Erase&Delete.png"/>

</div>
</details>

# 빠른 실행 도구 모음
{: .notice--warning .text-center}

# 함수
{: .notice--warning .text-center}

## =COUNTA(셀 주소:셀 주소)
{: .notice--success}

해당 셀 범위의 셀의 갯수를 반환

## =COUNTIF(셀 주소:셀 주소,"조건 텍스트")
{: .notice--success}

해당 셀 범위 내 조건에 해당하는 셀의 갯수를 반환

## =SUM(셀 주소:셀 주소)
{: .notice--success}

해당 셀 범위 내 값들의 합 연산 값을 반환

## =SUMIF(셀 주소:셀 주소,"조건 텍스트",셀 주소:셀 주소)
{: .notice--success}

첫 번째 파라미터 값의 셀 범위 내 조건에 해당하는 세 번째 파라미터 값의 셀 범위 내 값들의 합 연산 값을 반환

## =AVERAGE(셀 주소:셀 주소)
{: .notice--success}

해당 셀 범위 내 값들의 평균 값을 반환

## =AVERAGEIF(셀 주소:셀 주소,"조건 텍스트",셀 주소:셀 주소)
{: .notice--success}

첫 번째 파라미터 값의 셀 범위 내 조건에 해당하는 세 번째 파라미터 값의 셀 범위 내 값들의 평균 값을 반환

## =MIN(셀 주소:셀 주소)
{: .notice--success}

해당 셀 범위 내 값들 중 최솟값을 반환

## =MAX(셀 주소:셀 주소)
{: .notice--success}

해당 셀 범위 내 값들 중 최댓값을 반환

## =RANK(셀 주소,절대 셀 주소:절대 셀 주소,1|0)
{: .notice--success}

첫 번째 파라미터 값엔 반환받을 순위값의 셀 주소<br>
두 번째 파라미터 값엔 기준이 될 셀 범위를 지정해 절대값 셀 주소로 변경(F4)<br>
세 번째 파라미터 값엔 오름차순:1, 내림차순:0을 선택

## =IF(조건식,if실행문,else실행문)
{: .notice--success}

첫 번째 파라미터 값엔 조건식<br>
두 번째 파라미터 값엔 조건식이 트루일 경우 해당 셀에 반환받을 값<br>
세 번째 파라미터 값엔 조건식이 펄스일 경우 해당 셀에 반환받을 값

## =VLOOKUP(셀 주소,절대 셀 주소:절대 셀 주소,열 넘버,TRUE|FALSE)
{: .notice--success}

첫 번째 파라미터 값엔 찾을 값<br>
두 번째 파라미터 값엔 찾을 값의 범위<br>
세 번째 파라미터 값엔 두 번째 파라미터 값 기준 첫 번째 파라미터 값이 있는 행의 반환받을 열의 넘버<br>
네 번째 파라미터 값엔 TRUE=유사 일치, FALSE=정확히 일치
