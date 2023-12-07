---
title:  "텍스트 스타일"
excerpt: "text style"
categories: CSS
tag: [CSS, text, style]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# direction
{: .notice--warning .text-center}

```html
<style>
    .direction1 {
        direction: rtl;
    }
</style>

<div class="direction1">일타스랍아 는가 로으쪽왼 서에쪽른오</div>
```

# color
{: .notice--warning .text-center}

```html
<style>
    .colorBack{
        /* 6바이트 16진수 RGB 표현 */
        background:#000000;
    }
    .color1{
        /* 8바이트 16진수 RGBA 표현 */
        color: #f900a6c4;
    }
    .color2{
        /* 3바이트 10진수 rgb 표현 */
        color: rgb(48, 200, 10);
    }
    .color3{
        /* 표준화된 컬러 사용 */
        color:blue;
    }
    .color4{
        /* 4바이트 10진수 rgba 표현 */
        color:rgba(207, 79, 79, 0.675);
    }
</style>

<div class="colorBack">
    <div class="color1">color1</div>
    <div class="color2">color2</div>
    <div class="color3">color3</div>
    <div class="color4">color4</div>
</div>
```

# text-decoration
{: .notice--warning .text-center}

```html
<style>
    .text_deco1{
        text-decoration: none;
    }
    .text_deco2 {
        text-decoration: underline;
    }
    .text_deco3 {
        text-decoration: line-through;
    }
    .text_deco4 {
        text-decoration: overline;
    }
</style>

<a href="https://google.com" class="text_deco1">a 태그에서 밑줄을 없앤 형태</a><br>
<div class="text_deco2">밑줄(강조선)</div>
<div class="text_deco3">관통줄(취소선)</div>
<div class="text_deco4">윗줄(강조선)</div>
```

# text-transform
{: .notice--warning .text-center}

```html
<style>
    .text_trans1 {
        text-transform: none;
    }
    .text_trans2 {
        /* 각 첫 글자만 대문자로 변경 */
        text-transform: capitalize;
    }
    .text_trans3 {
        /* 전체 대문자로 변경 */
        text-transform: uppercase;
    }
    .text_trans4 {
        /* 전체 소문자로 변경 */
        text-transform: lowercase;
    }
</style>

<div class="text_trans1">I am a student. none.</div>
<div class="text_trans2">I am a student. capitalize.</div>
<div class="text_trans3">I am a student. uppercase.</div>
<div class="text_trans4">I am a student. LOWERCASE.</div>
```

# text-shadow
{: .notice--warning .text-center}

```html
<style>
    .bg {
        background-color: black;
        margin: 30px;
        padding: 50px;
        width: 100%;
        height: 500px;
    }
    /* text-shadow: offset-x offset-y blur-radius color; */
    /* offset-x: 그림자의 수평 위치를 나타냅니다. */
    /* offset-y: 그림자의 수직 위치를 나타냅니다. */
    /* blur-radius: 그림자의 흐림 정도를 나타냅니다. 값이 클수록 흐린 그림자가 생성됩니다. */
    /* color: 그림자의 색상을 지정합니다. */
    .text_shadow1 {
        color: orangered;
        text-shadow: 5px 5px orange;
        font: 30pt bold;
    }
    .text_shadow2 {
        color: rgb(255, 178, 178);
        text-shadow: 0px 1px 20px #fff;
        line-height: 30pt;
        font: 30pt bold;
    }
    .text_shadow3 {
        color: white;
        text-shadow: 5px 5px 20px turquoise;
        line-height: 30pt;
        font: 30pt bold;
    }
    .text_shadow4 {
        color: rgb(44, 33, 33);
        line-height: 30pt;
        font: 30pt bold;
        text-shadow: 0px 0px 4px #ccc, 0px -5px 4px #ff3, 2px -10px 6px #fd3, -2px -15px 11px #f80, 2px -19px 18px #f20;
    }
</style>

<div class="bg">
    <p class="text_shadow1">그림자 있는 글꼴 5px 5px orange</p>
    <p class="text_shadow2">그림자 있는 글꼴 0px 1px 20px white</p>
    <p class="text_shadow3">그림자 있는 글꼴 5px 5px 20px turquoise</p>
    <p class="text_shadow4">그림자 있는 글꼴 중첩 형태</p>
</div>
```