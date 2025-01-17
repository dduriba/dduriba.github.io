---
title:  "Github Pages운용을 위한 문법들"
categories: Note
excerpt: "Jekyll, Markdown, HTML"
---

# 1.Header
{: .notice--warning}

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
{: .notice--warning}

```md
[Google](https://google.com)
```

[Google](https://google.com)

# 3.BlockQuote (인용 블록)
{: .notice--warning}

```md
> BlockQuote
  >> BlockQuote
```

> BlockQuote
  >> BlockQuote

# 4.Ordered List
{: .notice--warning}

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
{: .notice--warning}

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
{: .notice--warning}

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
{: .notice--warning}

```
~~Strikethrough~~
```

~~Strikethrough~~

# 8.Bold, Italic
{: .notice--warning}

```md
*Italic*
**Bold**
***Italic & Bold***
```

*Italic*<br>
**Bold**<br>
***Italic & Bold***

# 9.Image
{: .notice--warning}

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
{: .notice--warning}

```html
abcd<br>efg
```

abcd<br>efg

# 11.line-split
{: .notice--warning}

```
한 줄의 공백을 두어

작성을 하면 된다.
```

한 줄의 공백을 두어

작성을 하면 된다.

# 12.Underline (밑줄)
{: .notice--warning}

```html
<u>밑줄</u>
```

<u>밑줄</u>

# 13.text color
{: .notice--warning}

```html
<span style="color:red">코드</span>
```

<span style="color:red">코드</span>

# 14.Check box
{: .notice--warning}

```md
- [ ] 체크 안됨
- [X] 체크 됨
```

- [ ] 체크 안됨
- [X] 체크 됨

# 15.dividing line (구분선)
{: .notice--warning}

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

# 17.Toggle List
{: .notice--warning}

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
{: .notice--warning}

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
{: .notice--warning}

`https://youtu.be/b3TOVBNSJDA?si=hyK0cokDO4uAdKnk`<br>
`https://youtu.be/b3TOVBNSJDA`<br>
유튜브 링크 주소의 id="b3TOVBNSJDA" 를 사용

```liquid
{% raw %}{% include video id="b3TOVBNSJDA" provider="youtube" %}{% endraw %}
```

{% include video id="b3TOVBNSJDA" provider="youtube" %}

# 20.Notice
{: .notice--warning}

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
{: .notice--warning}

~~~md
이것은 `인라인` 사용법입니다.
~~~

이것은 `인라인` 사용법입니다.

# 22.Text alignment
{: .notice--warning}

```
Left aligned text
{: .text-left}
Center aligned text.
{:}
Right aligned text.
{: .text-right}
```

Left aligned text
{: .text-left}
Center aligned text.
{:}
Right aligned text.
{: .text-right}
