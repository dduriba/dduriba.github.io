---
title:  "변형"
excerpt: "transform"
categories: CSS
tag: [CSS, transform]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# 2차원 변형
{: .notice--warning .text-center}

```html
<style>
    img{
        width:250px;
        border: 1px solid black;
    }
    .trans1:hover{
        /* html5 표준 스타일*/
        transform: translateX(100px);
        /* 크롬 계열 */
        /* -webkit-transform: translateX(100px); */
        /*ms 익스플로러 계열 */
        /* -ms-transform: translateX(100px); */
    }
    .trans2:hover{
        transform: translateY(100px);
    }
    .trans3:hover{
        transform: translate(100px, -100px);
    }
    .trans4:hover{
        transform: scaleX(2);
    }
    .trans5:hover{
        transform: scaleY(0.5);
    }
    .trans6:hover{
        transform: scale(3, 3);
    }
    .trans7:hover{
        transform: rotate(-45deg);
        transition: all 1s;
    }
    .trans7:active{
        transform: rotate(45deg);
        transition: all 1s;
    }
    .trans8:hover{
        transform: skewX(-45deg);
    }
    .trans9:hover{
        transform: skewY(-45deg);
    }
    .trans10:hover{
        transform: skew(30deg,30deg);
        transition: all 1s;
    }
</style>

<h3>1. translateX</h3>
<img class="trans1" src="resources/image/flower1.PNG">
<h3>2. translateY</h3>
<img class="trans2" src="resources/image/flower2.PNG">
<h3>3. translate</h3>
<img class="trans3" src="resources/image/flower3.PNG">
<h3>4. scaleX</h3>
<img class="trans4" src="resources/image/flower4.PNG">
<h3>5. scaleY</h3>
<img class="trans5" src="resources/image/flower5.PNG">
<h3>6. scale</h3>
<img class="trans6" src="resources/image/flower1.PNG">
<h3>7. rotate</h3>
<img class="trans7" src="resources/image/flower2.PNG">
<h3>8. skewX</h3>
<img class="trans8" src="resources/image/flower3.PNG">
<h3>9. skewY</h3>
<img class="trans9" src="resources/image/flower4.PNG">
<h3>10. skew</h3>
<img class="trans10" src="resources/image/flower5.PNG">
```

# 3차원 변형
{: .notice--warning .text-center}

```html
<style>
    img {
        width: 250px;
        border: solid black 1px;
    }
    .trans1:hover {
        transform: perspective(300px) translate3d(100px, 50px, 100px);
        transition: 2s all;
    }
    .trans2:hover {
        transform: perspective(300px) translateZ(30px);
        transition: 2s all;
    }
    .trans3:hover {
        transform: perspective(300px) rotateX(30deg);
    }
    .trans4:hover {
        transform: perspective(300px) rotateY(45deg);
    }
    .trans5:hover {
        transform: perspective(300px) rotateZ(-45deg);
    }
    .trans6:hover {
        transform: perspective(300px) rotate3d(2.5, 1.5, -1.5, 30deg);
        transition: 2s all;
    }
    .trans7:hover {
        transform: rotateZ(25deg);
        transform-origin: left top;
        transition: 2s all;
    }
</style>

<h3>1. translate3d</h3>
<img class="trans1" src="resources/image/flower1.PNG">
<h3>2. translateZ</h3>
<img class="trans2" src="resources/image/flower2.PNG">
<h3>3. rotateX</h3>
<img class="trans3" src="resources/image/flower3.PNG">
<h3>4. rotateY</h3>
<img class="trans4" src="resources/image/flower4.PNG">
<h3>5. rotateZ</h3>
<img class="trans5" src="resources/image/flower5.PNG">
<h3>6. rotate3d</h3>
<img class="trans6" src="resources/image/flower1.PNG">
<h3>7. rotateZ</h3>
<img class="trans7" src="resources/image/flower2.PNG">
```

# transition
{: .notice--warning .text-center}

```html
<!-- transition: property duration timing-function delay; -->
<!-- property: 애니메이션화할 CSS 속성을 지정(width, height, background-color 등) -->
<!-- duration: 애니메이션의 지속 시간을 초 또는 밀리초 단위로 설정(0.5s, 1000ms) -->
<!-- timing-function: 애니메이션의 진행 속도를 조절하는 함수를 지정 -->
<!--    주로 ease, linear, ease-in, ease-out, ease-in-out 등의 키워드를 사용 -->
<!--    또는 cubic-bezier 함수를 사용하여 사용자 정의 타이밍 함수를 지정할 수 있음 -->
<!-- delay: 애니메이션이 시작되기 전에 대기할 시간을 초 또는 밀리초 단위로 설정 -->
<style>
    img,
    div {
        width: 200px;
        height: 150px;
        background-color: crimson;
        border: 1px solid black;
    }
    .trans1:hover {
        transform: rotate(45deg);
        transition: all 2s;
    }
    .trans1:active {
        transform: rotate(-45deg);
        transition: all 2s;
    }
    .trans2:hover {
        width: 300px;
        height: 300px;
        transform: rotateZ(200deg);
        background-color: chartreuse;
        /* 각 property 마다 duration 지정 */
        transition-property: background-color, transform, height, width;
        transition-duration: 5s, 10s, 1s, 100ms;
    }
    .trans2:active {
        width: 100px;
        height: 100px;
        transform: rotateZ(-200deg);
        background-color: rgb(0, 255, 234);
        transition: all 2s;
    }
    .trans3:hover {
        transform: rotate(45deg);
        transition-duration: 2s;
        transition-delay: 1s;
    }
</style>

<h3>1. transition-duration</h3>
<img class="trans1" src="resources/image/flower3.PNG">
<h3>2. transition-property - rotateZ</h3>
<div class="trans2"></div>
<h3>3. transition-duration & delay</h3>
<img class="trans3" src="resources/image/flower2.PNG">
```

# animation
{: .notice--warning .text-center}

```html
<style>
    @keyframes menumove {
        from {
            transform: translateX(3px);
            color: lime;
            text-decoration: underline;
            font-size: 40px;
        }
        to {
            transform: translateX(-3px);
            color: lightgreen;
            text-decoration: underline;
            font-size: 40px;
        }
    }
    header>nav>ul>li {
        display: inline-block;
        font-size: 30px;
        font-weight: bold;
        margin-right: 50px;
        color: lightgreen;
        cursor: pointer;
    }
    header>nav li:hover {
        animation: menumove 0.5s infinite alternate;
    }
    @keyframes ani {
        from {
            background-color: black;
            font-size: 20px;
            transform: rotate(30deg);
        }
        to {
            background-color: coral;
            border: 3px aquamarine dotted;
            font-size: 10px;
            border-radius: 50px;
            transform: rotate(360deg);
        }
    }
    .anitest {
        width: 200px;
        animation-name: ani;
        animation-duration: 4s;
        animation-direction: alternate;
        animation-iteration-count: infinite;
    }
    @keyframes ani2 {
        0% {
            background-color: darkgreen;
            font-size: 15px;
            border-radius: 100px;
            transform: rotate(360deg);
        }
        20% {
            background-color: crimson;
            width: 300px;
            height: 300px;
        }
        40% {
            transform: translate(100px, 200px);
            background-color: lightsalmon;
        }
        60% {
            width: 10px;
            height: 10px;
            transform: scale(1.5);
        }
        100% {
            background-color: magenta;
            width: 200px;
            height: 200px;
            transform: skew(20deg, 20deg);
        }
    }
    .anitest2 {
        animation: ani2 5s infinite alternate;
    }
</style>

<header>
    <nav>
        <ul>
            <li>main</li>
            <li>board</li>
            <li>gallary</li>
            <li>warehouse</li>
        </ul>
    </nav>
</header>
<div class="anitest">anitest 애니메이션 적용</div>
<div class="anitest2">anitest2 애니메이션 적용</div>
```