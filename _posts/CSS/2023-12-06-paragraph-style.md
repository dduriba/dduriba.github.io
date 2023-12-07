---
title:  "문단 스타일"
excerpt: "paragraph style"
categories: CSS
tag: [CSS, paragraph, style]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# text-align
{: .notice--warning .text-center}

```html
<style>
    .align1{
        text-align: left;
    }
    .align2{
        text-align: right;
    }
    .align3{
        text-align: center;
    }
    .align4{
        text-align: justify;
    }
</style>

<div class="align1"> 정렬 기준 : left</div>
<div class="align2"> 정렬 기준 : right</div>
<div class="align3"> 정렬 기준 : center</div>
<div class="align4"> 정렬 기준 : justify (양쪽 맞춤 정렬 : 왼쪽과 오른쪽 여백에 균등하게 분산)</div>
```

# text-indent
{: .notice--warning .text-center}

```html
<style>
    .text_indent {
        text-indent: 50pt;
    }
</style>

<div class="text_indent">들여쓰기</div>
```

# line-height
{: .notice--warning .text-center}

```html
<style>
    .line_height1 {
        /* 기본 줄 간격 */
        line-height: normal;
    }
    .line_height2 {
        line-height: 50px;
    }
    .line_height3 {
        line-height: 2em;
    }
</style>

<p class="line_height1">별 헤는 밤 윤동주 계절이 지나가는 하늘에는가을로 가득 차 있습니다. 나는 아무 걱정도 없이 가을 속의 별들을 다 헬듯합니다. 가슴 속에 하나 둘 새겨지는 별을 이제 다 못 헤는 것은 쉬이아침이 오는 까닭이요, 내일 밤이 남은 까닭이요, 아직 나의 청춘이다하지 않은 까닭입니다.
</p>
<hr>
<p class="line_height2">별 헤는 밤 윤동주 계절이 지나가는 하늘에는가을로 가득 차 있습니다. 나는 아무 걱정도 없이 가을 속의 별들을 다 헬듯합니다. 가슴 속에 하나 둘 새겨지는 별을 이제 다 못 헤는 것은 쉬이아침이 오는 까닭이요, 내일 밤이 남은 까닭이요, 아직 나의 청춘이다하지 않은 까닭입니다.
</p>
<hr>
<p class="line_height3">별 헤는 밤 윤동주 계절이 지나가는 하늘에는가을로 가득 차 있습니다. 나는 아무 걱정도 없이 가을 속의 별들을 다 헬듯합니다. 가슴 속에 하나 둘 새겨지는 별을 이제 다 못 헤는 것은 쉬이아침이 오는 까닭이요, 내일 밤이 남은 까닭이요, 아직 나의 청춘이다하지 않은 까닭입니다.
</p>
```

# text-overflow
{: .notice--warning .text-center}

```html
<style>
    .bg{
        width:200px;
        border:1px solid black;
        /* white-space: nowrap -> 공백 문자와 줄 바꿈 문자를 무시하고 모든 텍스트를 한 줄에 나열 */
        white-space: nowrap;
        /* overflow: hidden; -> 요소의 내용이 요소의 크기를 벗어날 경우, 넘치는 부분을 숨김 */
        overflow: hidden;
        /* text-overflow: clip -> 텍스트가 요소의 영역을 벗어날 때, 초과된 부분을 잘라내어 보여줌 */
        /* text-overflow: clip; */
        /* text-overflow: ellipsis -> 텍스트가 요소의 영역을 벗어날 때, 초과된 부분을 "…" (ellipsis)으로 대체하여 보여줌 */
        text-overflow: ellipsis;
    }
</style>

<div class="bg">
    별 헤는 밤 윤동주, 계절이 지나가는 하늘에는 가을로 가득 차 있습니다.
</div>
```