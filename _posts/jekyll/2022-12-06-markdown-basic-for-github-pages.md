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

```markdown
# H1
## H2
### H3
#### H4
##### H5
###### H6
```

# H1
## H2
### H3
#### H4
##### H5
###### H6

---

# 2.Link
{: .notice--warning}

```markdown
[Google](https://google.com)
```

[Google](https://google.com)

---

# 3.BlockQuote
{: .notice--warning}

```markdown
> BlockQuote
  >> BlockQuote
```

> BlockQuote
  >> BlockQuote

---

# 4.Ordered List
{: .notice--warning}

```markdown
1. ordered-first
    1. first-one
    2. first-two
        - A
        - B
2. ordered-second
3. ordered-third
```

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

```markdown
- unordered
    * unordered
        + unordered
- unordered
```

- unordered
    * unordered
        + unordered
- unordered

---

# 6.Code Block
{: .notice--warning}

```html
<div class="notice--success">
<pre><span style="color:green">상단부\</span>
<code>코드를 입력하는 곳\</code>
</pre>하단부
</div>
```

<div class="notice--success">
<pre><span style="color:green">상단부</span>
<code>코드를 입력하는 곳</code>
</pre>하단부
</div>

~~~
```
코드를 입력하는 곳
```
~~~

```
코드를 입력하는 곳
```

```
~~~
코드를 입력하는 곳
~~~
```

~~~
코드를 입력하는 곳
~~~

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

~~~markdown
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
~~~

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

```
~~Strikethrough~~
```

~~Strikethrough~~

---

# 8.Bold, Italic
{: .notice--warning}

```markdown
*Italic*
**Bold**
***Italic & Bold***
```

*Italic*<br>
**Bold**<br>
***Italic & Bold***

---

# 9.Image
{: .notice--warning}

```html
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

```html
abcd
<br>efg
```

abcd
<br>efg

---

# 11.문단 나누기
{: .notice--warning}

```
한 줄의 공백을 두어

작성을 하면 된다.
```

한 줄의 공백을 두어

작성을 하면 된다.

---

# 12.밑줄
{: .notice--warning}

```html
<u>밑줄</u>
```

<u>밑줄</u>

---

# 13.글씨 색
{: .notice--warning}

```html
<span style="color:red">빨강</span>
```

<span style="color:red">빨강</span>

---

# 14.체크 박스
{: .notice--warning}

```markdown
- [ ] 체크 안됨
- [X] 체크 됨
```

- [ ] 체크 안됨
- [X] 체크 됨

---

# 15.구분선
{: .notice--warning}

```
***
---
```

***
---

---

# 16.테이블
{: .notice--warning}

```
|첫번째 셸|두번째 셸|세번째 셸|
|:---|---:|:---:|
|왼쪽정렬|오른쪽정렬|중앙정렬|
|왼쪽정렬|오른쪽정렬|중앙정렬|
|왼쪽정렬|오른쪽정렬|중앙정렬|
```

|첫번째 셸|두번째 셸|세번째 셸|
|:---|---:|:---:|
|왼쪽정렬|오른쪽정렬|중앙정렬|
|왼쪽정렬|오른쪽정렬|중앙정렬|
|왼쪽정렬|오른쪽정렬|중앙정렬|

---

# 17.토글리스트
{: .notice--warning}

```html
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

```markdown
[맨위로이동](#){: .btn .btn--primary }
```

[맨위로이동](#){: .btn .btn--primary }

---

# 19.유튜브
{: .notice--warning}

To embed the following YouTube video at url `https://www.youtube.com/watch?v=QKXXF3uxzvI` (long version) or `https://youtu.be/QKXXF3uxzvI` (short version) into a post or page's main content you'd use:

```liquid
{% raw %}{% include video id="QKXXF3uxzvI" provider="youtube" %}{% endraw %}
```

{% include video id="QKXXF3uxzvI" provider="youtube" %}

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
