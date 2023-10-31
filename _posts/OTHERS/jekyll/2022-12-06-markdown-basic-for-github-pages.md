---
title:  "Github Pages운용을 위한 문법들"
excerpt: "markdown, html등의 문법들을 알아봅시다."
categories: Jekyll
tag: [Jekyll, Github Pages, Markdown, HTML]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# 1.Header
{: .notice--warning .text-center}

```md
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

# 2.Link
{: .notice--warning .text-center}

```md
[Google](https://google.com)
```

[Google](https://google.com)

# 3.BlockQuote (인용 블록)
{: .notice--warning .text-center}

```md
> BlockQuote
  >> BlockQuote
```

> BlockQuote
  >> BlockQuote

# 4.Ordered List
{: .notice--warning .text-center}

```md
1. first
    1. first_1
    2. first_2
        - unordered
        - unordered
2. second
3. third
```

1. first
    1. first_1
    2. first_2
        - unordered
        - unordered
2. second
3. third

# 5.Unordered List
{: .notice--warning .text-center}

```md
- unordered
    * unordered
        + unordered
- unordered
```

- unordered
    * unordered
        + unordered
- unordered

# 6.Code Block
{: .notice--warning .text-center}

## 6-1 Code Block
{: .notice--success}

```html
<pre>상단부
<code>코드를 입력하는 곳</code>
하단부</pre>
```

<pre>상단부
<code>코드를 입력하는 곳</code>
하단부</pre>

## 6-2 Code Block
{: .notice--success}

~~~
```
코드를 입력하는 곳
```
~~~

```
코드를 입력하는 곳
```

## 6-3 Code Block
{: .notice--success}

```
~~~
코드를 입력하는 곳
~~~
```

~~~
코드를 입력하는 곳
~~~

## 6-4 Code Block
{: .notice--success}

~~~md
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

# 7.Strikethrough (취소선)
{: .notice--warning .text-center}

```
~~Strikethrough~~
```

~~Strikethrough~~

# 8.Bold, Italic
{: .notice--warning .text-center}

```md
*Italic*
**Bold**
***Italic & Bold***
```

*Italic*<br>
**Bold**<br>
***Italic & Bold***

# 9.Image
{: .notice--warning .text-center}

```html
<img src="/path/filename.png" style="zoom:50%;"/>

<img src="/path/filename.png" style="zoom:100%;"/>

<img src="/path/filename.png"/>

<center><img src="/path/filename.png" width="300" height="300"></center>

<center><img src="/path/filename.png" width="50%" height="50%"></center>

<img src="/path/filename.png" width="100%" height="100%">
```

<img src="/img/retriever/retrieverCheer.png" style="zoom:50%;"/>

<img src="/img/retriever/retrieverCheer.png" style="zoom:100%;"/>

<img src="/img/retriever/retrieverCheer.png"/>

<center><img src="/img/retriever/retrieverCheer.png" width="300" height="300"></center>

<center><img src="/img/retriever/retrieverCheer.png" width="50%" height="50%"></center>

<img src="/img/retriever/retrieverCheer.png" width="100%" height="100%">

# 10.line-break (줄바꿈)
{: .notice--warning .text-center}

```html
abcd<br>efg
```

abcd<br>efg

# 11.line-split
{: .notice--warning .text-center}

```
한 줄의 공백을 두어

작성을 하면 된다.
```

한 줄의 공백을 두어

작성을 하면 된다.

# 12.Underline (밑줄)
{: .notice--warning .text-center}

```html
<u>밑줄</u>
```

<u>밑줄</u>

# 13.text color
{: .notice--warning .text-center}

```html
<span style="color:red">코드</span>
```

<span style="color:red">코드</span>

# 14.Check box
{: .notice--warning .text-center}

```md
- [ ] 체크 안됨
- [X] 체크 됨
```

- [ ] 체크 안됨
- [X] 체크 됨

# 15.dividing line (구분선)
{: .notice--warning .text-center}

## 15-1 dividing line
{: .notice--success}

```
***
```

***

## 15-2 dividing line
{: .notice--success}

```
---
```

---

# 16.Table
{: .notice--warning .text-center}

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

# 17.Toggle List
{: .notice--warning .text-center}

```html
<details>
<summary>타이틀</summary>
<div markdown="1">

콘텐트

</div>
</details>
```

<details>
<summary>타이틀</summary>
<div markdown="1">

콘텐트

</div>
</details>

# 18.Button
{: .notice--warning .text-center}

```md
[Google](https://google.com){: .btn}
[FROM THE TOP](#){: .btn .btn--primary}
[FROM THE TOP](#){: .btn .btn--success}
[FROM THE TOP](#){: .btn .btn--warning}
[FROM THE TOP](#){: .btn .btn--danger}
[FROM THE TOP](#){: .btn .btn--info}
[FROM THE TOP](#){: .btn .btn--inverse}
[FROM THE TOP](#){: .btn .btn--light-outline}
```

[Google](https://google.com){: .btn}
[FROM THE TOP](#){: .btn .btn--primary}
[FROM THE TOP](#){: .btn .btn--success}
[FROM THE TOP](#){: .btn .btn--warning}
[FROM THE TOP](#){: .btn .btn--danger}
[FROM THE TOP](#){: .btn .btn--info}
[FROM THE TOP](#){: .btn .btn--inverse}
[FROM THE TOP](#){: .btn .btn--light-outline}

# 19.Youtube
{: .notice--warning .text-center}

`https://www.youtube.com/watch?v=QKXXF3uxzvI`<br>
`https://youtu.be/QKXXF3uxzvI`<br>
유튜브 링크 주소의 id="QKXXF3uxzvI" 를 사용

```liquid
{% raw %}{% include video id="QKXXF3uxzvI" provider="youtube" %}{% endraw %}
```

{% include video id="QKXXF3uxzvI" provider="youtube" %}

# 20.Notice
{: .notice--warning .text-center}

```
공지
{: .notice}
공지
{: .notice--primary}
공지
{: .notice--info}
공지
{: .notice--warning}
공지
{: .notice--success}
공지
{: .notice--danger}
```

공지
{: .notice}
공지
{: .notice--primary}
공지
{: .notice--info}
공지
{: .notice--warning}
공지
{: .notice--success}
공지
{: .notice--danger}

# 21.Inline
{: .notice--warning .text-center}

~~~md
이것은 `인라인` 사용법입니다.
~~~

이것은 `인라인` 사용법입니다.

# 22.Text alignment
{: .notice--warning .text-center}

```
Left aligned text
{: .text-left}
Center aligned text.
{: .text-center}
Right aligned text.
{: .text-right}
```

Left aligned text
{: .text-left}
Center aligned text.
{: .text-center}
Right aligned text.
{: .text-right}
