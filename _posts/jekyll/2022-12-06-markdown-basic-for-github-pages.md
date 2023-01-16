---
layout: single
title:  "Github Pages운용을 위한 문법들"
categories: jekyll
tag: [github pages, markdown, jekyll, html]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
author_profile: true
sidebar_main: true
sidebar:
    nav: "docs"
search: true
---

---

# 1.Header
{: .notice--warning}

<div class="notice--success">
<pre><span style="color:green">코드</span>
<code># H1
## H2
### H3
#### H4
##### H5
###### H6</code>
</pre>
</div>

# H1
## H2
### H3
#### H4
##### H5
###### H6

---

# 2.Link
{: .notice--warning}

<div class="notice--success">
<pre><span style="color:green">코드</span>
<code>[Google](https://google.com)</code>
</pre>
</div>

[Google](https://google.com)

---

# 3.BlockQuote
{: .notice--warning}

<div class="notice--success">
<pre><span style="color:green">코드</span>
<code>> BlockQuote
  >> BlockQuote</code>
</pre>
</div>

> BlockQuote
  >> BlockQuote

---

# 4.Ordered List
{: .notice--warning}

<div class="notice--success">
<pre><span style="color:green">코드</span>
<code>1. ordered-first
    1. first-one
    2. first-two
        - A
        - B
2. ordered-second
3. ordered-third</code>
</pre>
</div>

1. ordered-first
    1. first-one
    2. first-two
        - A
        - B
2. ordered-second
3. ordered-third

---

# 5.Unordered List
{: .notice--warning}

<div class="notice--success">
<pre><span style="color:green">코드</span>
<code>- unordered
    * unordered
        + unordered
- unordered</code>
</pre>
</div>

- unordered
    * unordered
        + unordered
- unordered

---

# 6.Code Block
{: .notice--warning}

```
<div class="notice--success">
<pre><span style="color:green">코드\</span>
<code>type your codes on here\</code>
</pre>
</div>
```

<div class="notice--success">
<pre><span style="color:green">코드</span>
<code>type your codes on here</code>
</pre>
</div>

<div class="notice--success">
<pre><span style="color:green">코드</span><br>```c#
<code>using System;

namespace HelloWorld
{
  class Program
  {
    static void Main(string[] args)
    {
      Console.WriteLine("Hello World!");    
    }
  }
}
</code>```
</pre>
</div>

```c#
using System;

namespace HelloWorld
{
  class Program
  {
    static void Main(string[] args)
    {
      Console.WriteLine("Hello World!");    
    }
  }
}
```

---

# 7.Strikethrough
{: .notice--warning}

<div class="notice--success">
<pre><span style="color:green">코드</span>
<code>~~Strikethrough~~</code>
</pre>
</div>

~~Strikethrough~~

---

# 8.Bold, Italic
{: .notice--warning}

<div class="notice--success">
<pre><span style="color:green">코드</span>
<code>*Italic*
**Bold**
***Italic & Bold***</code>
</pre>
</div>

*Italic*<br>
**Bold**<br>
***Italic & Bold***

---

# 9.Image
{: .notice--warning}

```
<img src="/img/retrieverCheer.png" style="zoom:50%;" />

<center><img src="/img/retrieverGimozzi.png" width="300" height="300"></center>

<center><img src="/img/retrieverStudy.png" width="70%" height="70%"></center>
```

<img src="/img/retrieverCheer.png" style="zoom:50%;" />

<center><img src="/img/retrieverGimozzi.png" width="300" height="300"></center>

<center><img src="/img/retrieverStudy.png" width="70%" height="70%"></center>

---

# 10.줄바꿈
{: .notice--warning}

```
abcd
<br>efg
```

abcd
<br>efg

---

# 11.문단 나누기
{: .notice--warning}

<div class="notice--success">
<pre><span style="color:green">코드</span>
<code>한 줄의 공백을 두어

작성을 하면 된다.</code>
</pre>
</div>

한 줄의 공백을 두어

작성을 하면 된다.

---

# 12.밑줄
{: .notice--warning}

```
<u>밑줄</u>
```

<u>밑줄</u>

---

# 13.글씨 색
{: .notice--warning}

```
<span style="color:red">빨강</span>
```

<span style="color:red">빨강</span>

---

# 14.체크 박스
{: .notice--warning}

<div class="notice--success">
<pre><span style="color:green">코드</span>
<code>- [ ] 체크 안됨
- [X] 체크 됨</code>
</pre>
</div>

- [ ] 체크 안됨
- [X] 체크 됨

---

# 15.구분선
{: .notice--warning}

<div class="notice--success">
<pre><span style="color:green">코드</span>
<code>***
---</code>
</pre>
</div>

***
---

---

# 16.테이블
{: .notice--warning}

<div class="notice--success">
<pre><span style="color:green">코드</span>
<code>|첫번째 셸|두번째 셸|세번째 셸|
|:---|---:|:---:|
|왼쪽정렬|오른쪽정렬|중앙정렬|
|왼쪽정렬|오른쪽정렬|중앙정렬|
|왼쪽정렬|오른쪽정렬|중앙정렬|</code>
</pre>
</div>

|첫번째 셸|두번째 셸|세번째 셸|
|:---|---:|:---:|
|왼쪽정렬|오른쪽정렬|중앙정렬|
|왼쪽정렬|오른쪽정렬|중앙정렬|
|왼쪽정렬|오른쪽정렬|중앙정렬|

---

# 17.토글리스트
{: .notice--warning}

```
<details>
<summary>토글리스트</summary>
<div markdown="1">

숨겨진 내용

</div>
</details>
```

<details>
<summary>토글리스트</summary>
<div markdown="1">

숨겨진 내용

</div>
</details>

---

# 18.버튼
{: .notice--warning}

<div class="notice--success">
<pre><span style="color:green">코드</span>
<code>[맨위로이동](#){: .btn .btn--primary }</code>
</pre>
</div>

[맨위로이동](#){: .btn .btn--primary }

---

# 19.유튜브
{: .notice--warning}

```html
{% include video id="" provider="youtube" %}
```

{% include video id="svOWfkwaZOE" provider="youtube" %}

---

# [KST(한국표준시)는 UTC(협정세계시)기준으로 +09:00의 시차가 있습니다](https://time.is/ko/UTC)
{: .notice--danger}

<div class="notice--success">
<h4>hello div class</h4>
<ul>
    <li>test num 1</li>
    <li>test num 2</li>
    <li>test num 3</li>
</ul>
</div>

[button](https://google.com){: .btn .btn--danger}
