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

# 1.Header
# H1
## H2
### H3
#### H4
##### H5
###### H6

# 2.Link
[Google](https://google.com)

# 3.BlockQuote
> BlockQuote
  >> BlockQuote

# 4.Ordered List
1. ordered-first
    1. first-one
    2. first-two
        - A
        - B
2. ordered-second
3. ordered-third

# 5.Unordered List
- unordered
    * unordered
        + unordered
- unordered

# 6.Code Block
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

# 7.Strikethrough
~~Strikethrough~~

# 8. Bold, Italic
*Italic*<br>
**Bold**<br>
***Italic & Bold***

# 9. Image
<img src="/img/retrieverCheer.png" style="zoom:50%;" />

<center><img src="/img/retrieverGimozzi.png" width="300" height="300"></center>

<center><img src="/img/retrieverStudy.png" width="70%" height="70%"></center>

# 10. 줄바꿈
abcdefg
hijklmnop
<br>qrstuvwxyz

# 11.문단 나누기
한 줄의 공백을 두어

작성을 하면 된다.

# 12.밑줄
<u>밑줄</u>

# 13.글씨 색
<span style="color:yellow">노랑색</span>

# 14.체크 박스
- []
- [X]

# 15.구분선
***
---

# 16.테이블
|왼쪽정렬|가운데정렬|오른쪽정렬|
|:---|:---:|---:|
|하나|둘|셋|
|에이|비|씨|

# 17.토글리스트
<details>
<summary>토글리스트</summary>
<div markdown="1">

숨겨진 내용

</div>
</details>

# 18.버튼
[맨위로이동](#){: .btn .btn--primary }

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

**hello world**
hello world

[button](https://google.com){: .btn .btn--danger}

{% include video id="svOWfkwaZOE" provider="youtube" %}

```python
class <ClassName>:

    <class_attribute_name> = <value>

    def __init__(self,<param1>, <param2>, ...):
        self.<attr1> = <param1>
        self.<attr2> = <param2>
        .
        .
        .
        # As many attributes as needed
    
   def <method_name>(self, <param1>, ...):
       <code>
       
   # As many methods as needed
```

## 이미지 목차
### 이미지 세부 목차1
image here
### 이미지 세부 목차2
image here
### 이미지 세부 목차3
image here



# second table
this begins second table
