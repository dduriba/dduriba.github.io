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

셀 선택 → 셀 서식(Ctrl + 1) → 맞춤 → 텍스트 조정 →
1. 자동 줄 바꿈
2. 셀에 맞춤

<img src="/img/MS_Office/2023-07-12-excel-basic/TextAutoAdjust.png"/>

</div>
</details>

<details>
<summary>Mac</summary>
<div markdown="1">

홈 리본 메뉴 → 
1. 자동 줄 바꿈
2. 텍스트에 맞게 축소(셀에 맞춤)

<img src="/img/MS_Office/2023-07-12-excel-basic/TextAutoAdjustMac.png"/>

</div>
</details>

# 빠른 채우기
{: .notice--warning .text-center}

기준이 될 셀과 채울 셀을 선택 후 홈 리본 메뉴 → 채우기 → 빠른 채우기<br>
(참조할 셀이 좌측에 위치해야 함)

<img src="/img/MS_Office/2023-07-12-excel-basic/AutoFill.png"/>

# 내용 지우기와 삭제
{: .notice--warning .text-center}

내용 지우기는 삭제와 달리 서식이 남는다.

<img src="/img/MS_Office/2023-07-12-excel-basic/Erase&Delete.png"/>

# 함수
{: .notice--warning .text-center}

## =COUNTA(셀 범위)
{: .notice--success}

해당 셀 범위의 비어있지 않은 셀의 개수를 반환

<img src="/img/MS_Office/2023-07-12-excel-basic/COUNTA.png"/>

## =COUNTIF(셀 범위, 조건)
{: .notice--success}

해당 셀 범위 내 조건에 해당하는 셀의 개수를 반환

<img src="/img/MS_Office/2023-07-12-excel-basic/COUNTIF.png"/>

## =SUM(셀 범위)
{: .notice--success}

해당 셀 범위 내 값들의 합 연산 값을 반환

<img src="/img/MS_Office/2023-07-12-excel-basic/SUM.png"/>

## =SUMIF(셀 범위, 조건, 셀 범위)
{: .notice--success}

첫 번째 파라미터: 셀 범위 중<br>
두 번째 파라미터: 조건에 해당하는<br>
세 번째 파라미터: 이 셀 범위 내 값들의 합 연산 값을 반환

<img src="/img/MS_Office/2023-07-12-excel-basic/SUMIF.png"/>

## =AVERAGE(셀 범위)
{: .notice--success}

해당 셀 범위 내 값들의 평균 값을 반환

<img src="/img/MS_Office/2023-07-12-excel-basic/AVERAGE.png"/>

## =AVERAGEIF(셀 범위, 조건, 셀 범위)
{: .notice--success}

첫 번째 파라미터: 셀 범위 중<br>
두 번째 파라미터: 조건에 해당하는<br>
세 번째 파라미터: 이 셀 범위 내 값들의 평균 값을 반환

<img src="/img/MS_Office/2023-07-12-excel-basic/AVERAGEIF.png"/>

## =MIN(셀 범위)
{: .notice--success}

해당 셀 범위 내 값들 중 최솟값을 반환

<img src="/img/MS_Office/2023-07-12-excel-basic/MIN.png"/>

## =MAX(셀 범위)
{: .notice--success}

해당 셀 범위 내 값들 중 최댓값을 반환

<img src="/img/MS_Office/2023-07-12-excel-basic/MAX.png"/>

## =RANK(랭크 매길 값, 절대 셀 범위, 1|0)
{: .notice--success}

첫 번째 파라미터: 순위를 매길 셀<br>
두 번째 파라미터: 비교할 셀 범위(절대 셀 주소로 변경:F4)<br>
세 번째 파라미터: 0(내림차순), 1(오름차순)

<img src="/img/MS_Office/2023-07-12-excel-basic/RANK.png"/>

## =IF(조건식, if실행문, else실행문)
{: .notice--success}

첫 번째 파라미터: 조건식<br>
두 번째 파라미터: 조건식이 True일 경우 반환받을 값<br>
세 번째 파라미터: 조건식이 False일 경우 반환받을 값

<img src="/img/MS_Office/2023-07-12-excel-basic/IF.png"/>

## =VLOOKUP(찾을 값, 절대 셀 범위, 열 인덱스, TRUE|FALSE)
{: .notice--success}

첫 번째 파라미터: 찾을 값<br>
두 번째 파라미터: 찾을 셀 범위(절대 셀 주소로 변경:F4)<br>
세 번째 파라미터: 찾을 셀 범위 기준 반환 받으려는 셀이 있는 열의 인덱스<br>
네 번째 파라미터: FALSE(정확히 일치), TRUE(유사 일치)

주의할 점: 찾을 셀 범위의 첫 번째 열에 찾을 값이 있어야 해 반환받고 싶은 열이 보다 좌측에 위치할 경우 사용 불가, INDEX 함수와 MATCH 함수를 사용해 이를 보완할 수 있다.

<img src="/img/MS_Office/2023-07-12-excel-basic/VLOOKUP.png"/>

## =INDEX(절대 셀 범위, 행, 열)
{: .notice--success}

첫 번째 파라미터: 셀 범위<br>
두 번째 파라미터: 해당 셀 범위 기준 반환받을 셀의 행(row)<br>
세 번째 파라미터: 해당 셀 범위 기준 반환받을 셀의 열(column)

<img src="/img/MS_Office/2023-07-12-excel-basic/INDEX.png"/>

## =MATCH(찾을 값, 절대 셀 범위, -1|0|1)
{: .notice--success}

첫 번째 파라미터: 찾을 값<br>
두 번째 파라미터: 찾을 셀 범위(절대 셀 주소로 변경:F4)<br>
세 번째 파라미터: -1(보다 작음), 0(정확히 일치), 1(보다 큼)

셀 범위를 기준으로 값을 찾아 인덱스를 반환해 준다.

<img src="/img/MS_Office/2023-07-12-excel-basic/MATCH.png"/>

## =INDEX(절대 셀 범위, MATCH()|행 직접 입력, MATCH()|열 직접 입력)
{: .notice--success}

<img src="/img/MS_Office/2023-07-12-excel-basic/INDEX+MATCH.png"/>

# 빠른 실행 도구 모음
{: .notice--warning .text-center}

# 숏컷
{: .notice--warning .text-center}

- 셀 서식:
    + Windows: Ctrl + 1
    + Mac: Command + 1