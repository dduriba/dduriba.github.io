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
<style>
    /* 채운 원 모양 불렛(기본값) */
    #default-bullet {
        list-style-type: disc;
    }

    /* 빈 원 모양 불렛 */
    #circle-bullet {
        list-style-type: circle;
    }

    /* 채운 사각형 모양 불렛 */
    #square-bullet {
        list-style-type: square;
    }
    
    /* 불렛 없애기 */
    #none-bullet {
        list-style-type: none;
    }
</style>

<h4>채운 원 모양 불렛(기본값)</h4>
<ul id="default-bullet">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ul>

<h4>빈 원 모양 불렛</h4>
<ul id="circle-bullet">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ul>

<h4>채운 사각형 모양 불렛</h4>
<ul id="square-bullet">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ul>

<h4>불렛 없애기</h4>
<ul id="none-bullet">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ul>
```

# ordered list style
{: .notice--warning .text-center}

```html
<style>
    /* 1로 시작하는 10진수(기본값) */
    #default-number {
        list-style-type: decimal;
    }

    /* 앞에 0이 붙는 10진수 */
    #zero-number {
        list-style-type: decimal-leading-zero;
    }

    /* 소문자 로마 숫자 */
    #lower-rome-number {
        list-style-type: lower-roman;
    }

    /* 대문자 로마 숫자 */
    #upper-rome-number {
        list-style-type: upper-roman;
    }

    /* 알파벳 소문자 */
    #lower-alpha {
        list-style-type: lower-alpha;
    }

    /* 알파벳 대문자 */
    #upper-alpha {
        list-style-type: upper-alpha;
    }
</style>

<h4>1로 시작하는 10진수(기본값)</h4>
<ol id="default-number">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ol>

<h4>앞에 0이 붙는 10진수</h4>
<ol id="zero-number">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ol>

<h4>소문자 로마 숫자</h4>
<ol id="lower-rome-number">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ol>

<h4>대문자 로마 숫자</h4>
<ol id="upper-rome-number">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ol>

<h4>알파벳 소문자</h4>
<ol id="lower-alpha">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ol>

<h4>알파벳 대문자</h4>
<ol id="upper-alpha">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ol>
```

# image list style
{: .notice--warning .text-center}

```html
<style>
    /* 기호 대신 이미지 삽입 */
    #image-bullet {
        list-style-image: url("resources/image/iconsample.PNG");
    }
</style>

<h3>기호 대신 이미지 삽입</h3>
<ul id="image-bullet">
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>JQuery</li>
</ul>
```