---
title:  "배경 스타일"
excerpt: "background style"
categories: CSS
tag: [CSS, background, style]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# border, padding, margin과 background-clip
{: .notice--warning .text-center}

```html
<!-- border, padding, margin -->
<style>
    body{
        background-color:#202028;
        color: aliceblue;
    }
    .background1{
        background:cadetblue;
        height:100px;
        width: 100px;
        /* border : width(두께) style(테두리 스타일) color -> 요소의 테두리를 설정하는 속성 */
        border: 10px dashed white;
        /* padding : 요소의 내용과 테두리 사이에 여백을 설정하는 속성 */
        padding: 60px;
        /* margin : 요소의 바깥 부분에 여백을 설정하는 속성 */
        margin: 100px;
    }
</style>

<div class="background1">테스트 영역</div>

<!-- background-clip -->
<!-- 요소의 배경이 어디까지 적용될지를 지정하는 데 사용 -->
<style>
    .clip1{
        /* border-box : 테두리 상자까지 적용, 기본값 */
        background-clip: border-box;
    }
    .clip2{
        /* padding-box : 패딩 상자까지만 적용, 테두리 영역의 배경 제외 */
        background-clip: padding-box;
    }
    .clip3{
        /* content-box : 콘텐츠 상자(텍스트 등이 포함된 영역)까지만 적용, 테두리와 패딩 영역의 배경 제외 */
        background-clip: content-box;
    }
</style>

<!-- class 2개를 중첩시킨 형태 -->
<div class="background1 clip1">background-clip: border-box</div>
<div class="background1 clip2">background-clip: padding-box</div>
<div class="background1 clip3">background-clip: content-box</div>
```

# background-image
{: .notice--warning .text-center}

```html
<style>
    .background_image1 {
        height: 800px;
        border: black solid 1px;

        background-image: url(resources/image/bgsample.PNG);

        /* 이미지 반복 방법 지정 */
        /* 가로 세로 모두 반복(기본값) */
        /* background-repeat: repeat; */
        /* 가로만 반복 */
        /* background-repeat: repeat-x; */
        /* 세로만 반복 */
        /* background-repeat: repeat-y; */
        /* 반복 안함 */
        background-repeat: no-repeat;

        /* 이미지 크기 지정 */
        /* 원래 크기(기본값) */
        /* background-size: auto; */
        /* 요소 크기에 맞게 이미지 확대/축소(비율유지) */
        /* background-size: contain; */
        /* 요소 크기에 맞게 이미지 확대/축소(비율유지하지 않음) */
        /* background-size: cover; */
        /* 가로세로 크기 직접 지정(고정 크기) */
        /* background-size: 150px 100px; */
        /* 가로세로 크기 직접 지정(가변 크기) */
        /* background-size: 80% 50%; */

        /* 이미지 위치 지정 */
        /* background-position: left top; */
        /* background-position: right top; */
        background-position: center top;
        /* background-position: center bottom; */
        /* background-position: center center; */
        /* background-position: 10px 50px; */
        /* background-position: 50% 20%; */
        
        /* 이미지 스크롤 여부 지정 */
        background-attachment: scroll;
        /* background-attachment: fixed; */
    }
</style>

<div class="background_image1">
    텍스트 테스트
</div>
```