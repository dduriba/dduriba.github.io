---
title:  "목록 스타일"
excerpt: "list style"
categories: CSS
tag: [CSS, list, style]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# unordered list style
{: .notice--warning .text-center}

```html
<!-- 채운 원 모양 불렛(기본값) -->
<ul style="list-style-type: disc;">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ul>

<!-- 빈 원 모양 불렛 -->
<ul style="list-style-type: circle;">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ul>

<!-- 채운 사각형 모양 불렛 -->
<ul style="list-style-type: square;">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ul>

<!-- 불렛 없애기 -->
<ul style="list-style-type: none;">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ul>
```

# ordered list style
{: .notice--warning .text-center}

```html
<!-- 1로 시작하는 10진수(기본값) -->
<!-- <ol type="1"> -->
<ol style="list-style-type: decimal;">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ol>

<!-- 앞에 0이 붙는 10진수 -->
<ol style="list-style-type: decimal-leading-zero;">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ol>

<!-- 소문자 로마 숫자 -->
<!-- <ol type="i"> -->
<ol style="list-style-type: lower-roman;">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ol>

<!-- 대문자 로마 숫자 -->
<!-- <ol type="I"> -->
<ol style="list-style-type: upper-roman;">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ol>

<!-- 알파벳 소문자 -->
<!-- <ol type="a"> -->
<ol style="list-style-type: lower-alpha;">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ol>

<!-- 알파벳 대문자 -->
<!-- <ol type="A"> -->
<ol style="list-style-type: upper-alpha;">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ol>
```

# image list style
{: .notice--warning .text-center}

```html
<!-- 기호 대신 이미지 삽입 -->
<ul style="list-style-image: url(resources/image/iconsample.PNG);">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ul>
```