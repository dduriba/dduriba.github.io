---
title:  "폰트 스타일"
excerpt: "font style"
categories: CSS
tag: [CSS, font, style]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# font-family
{: .notice--warning .text-center}

```html
<!-- font-family : 사용할 폰트를 지정 -->
<!-- PC에 있는 글꼴(기본 글꼴을 포함)을 사용하는 방법과 -->
<!-- 외부 혹은 서버에서 제공하는 방법이 존재 -->
<!-- 구글 폰트 사이트 : https://fonts.google.com/ -->

<head>
    <!-- html에서 link해 가져오는 방법, font2에 사용할 폰트 -->
    <!-- 구글 폰트 사이트에서 가져옴 -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Nanum+Pen+Script&display=swap" rel="stylesheet">
</head>

<style>
    /* css에서 import해 가져오는 방법, font3에 사용할 폰트 */
    /* 구글 폰트 사이트에서 가져옴 */
    @import url('https://fonts.googleapis.com/css2?family=Gugi&display=swap');

    .font1 {
        font-family: '궁서체';
    }

    .font2 {
        font-family: 'Nanum Pen Script', cursive;
        font-size: 20pt;
    }

    .font3 {
        font-family: 'Gugi', sans-serif;
        font-size: 20pt;
    }
</style>

<div class="font1">1. PC에 있는 궁서체 가져오기(없을 경우 일반 폰트로 변경됨)</div>
<div class="font2">2. 나눔펜 폰트 적용 </div>
<div class="font3">3. Gugi 폰트 적용 </div>
```

# font-size
{: .notice--warning .text-center}

```html
<style>
    .font_size1 {
        font-size:12pt;
    }
    /* em은 부모 요소의 폰트 크기에 상대적 */
    /* 부모 요소의 폰트 크기가 16px이라면, 1em은 16px, 2em은 32px이 됨 */
    /* 중첩된 요소에서 상속되는 폰트 크기에 영향을 받음 */
    .font_size2 {
        font-size:2em;
    }
    /* rem은 최상위(root) 요소(html 또는 body)의 폰트 크기에 상대적 */
    /* 중첩된 요소에 영향을 받지 않음 */
    .font_size3 {
        font-size:2rem;
    }
    /* %는 부모 요소의 크기를 기준으로 함 */
    .font_size4 {
        font-size:200%;
    }
    .font_size5 {
        font-size:larger;
    }
</style>

<div class="font_size1">font_size1 12pt</div>
<div class="font_size2">font_size2 2em</div>
<div class="font_size3">font_size3 2rem</div>
<div class="font_size4">font_size4 200%</div>
<div class="font_size5">font_size5 larger</div>
```

# font-weight
{: .notice--warning .text-center}

```html
<style>
    .font_weight1{
        font-weight: bold;
    }
    .font_weight2{
        font-weight: 900;
    }
    .font_weight3{
        font-weight: lighter;
    }
</style>

<div class="font_weight1">1. bold</div>
<div class="font_weight2">2. 900</div>
<div class="font_weight3">3. lighter</div>
```

# font-variant, font-style
{: .notice--warning .text-center}

```html
<style>
    /* 소문자를 작은 대문자로 서체 변형 */
    .font_variant {
        font-variant: small-caps;
    }
    .font_style {
        font-style: italic;
    }
</style>

<div class="font_variant">I Am A Student<div>
<div class="font_style"> 이탤릭체</div>
```

# font
{: .notice--warning .text-center}

```css
.font1 {
    font-family :'Gugi';
    font-weight : bold;
    font-size: 32pt;
    /* 위 전체 속성을 font 속성으로 압축 가능 */
    /* font-style, font-variant, font-weight, font-stretch, font-size, line-height, font-family 순서로 사용 */
    font : bold 32pt 'Gugi';
}
```