---
title: "window 객체"
excerpt: "window object"
categories: JavaScript
tag: [JavaScript, window object]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# open
{: .notice--warning .text-center}

```html
<!-- 특정 URL을 오픈 -->
<button onclick="test1();">구글</button>
<button onclick="test2();">네이버</button>
<button onclick="test3();">close</button>

<script>
    console.log(window);
    function test1(){
        window.open('http://www.google.com', '구글'); // 새 탭으로 오픈 
    }
    function test2(){
        window.open('http://www.naver.com', '네이버', 'location=no', false); // 새 창으로 오픈
    }
    function test3(){
        window.close(); // 탭 클로즈
        alert('close 호출');
    }
</script>
```

# setTimeout
{: .notice--warning .text-center}

```html
<!-- 일정시간 이후에 예약된 함수를 한번 실행시키는 구조 -->
<button onclick="test4();">실행1</button>
<button onclick="test5();">실행2</button>
<div id="div1"></div>
<script>
    function test4(){
        var myWindow = window.open();
        myWindow.alert('3초 뒤에 페이지가 종료됩니다.');
        window.setTimeout(function(){
            myWindow.close();
        }, 3000);
    }   
    function test5(){
        document.getElementById('div1').innerHTML = '0초에 업데이트 된 문장<br>';
        window.setTimeout(function(){
            document.getElementById('div1').innerHTML = '3초 뒤에 업데이트 된 문장<br>'
        }, 3000);
    }
</script>  
```

# setInterval()
{: .notice--warning .text-center}

```html
<!-- 일정시간마다 지정한 함수를 반복하는 방법 -->
<button onclick="test6();">실행1</button>
<div id="div2"></div>
<script>
    function test6(){
        window.setInterval(function(){
            var date = new Date();
            document.getElementById('div2').innerText = date.toLocaleString();
        }, 1000); // ms 단위
    }
</script>
```

# clearInterval()
{: .notice--warning .text-center}

```html
<!-- Interval 종료시키는 함수 -->
<button onclick="test7();">실행1</button>
<button onclick="test8();">제거</button>
<div id="div3"></div>
<script>
    var intervalObj;

    function test7(){
        intervalObj = setInterval(function(){
            var date = new Date();
            document.getElementById('div3').innerText = date.toLocaleString() + '.' + date.getMilliseconds();
        }, 10); // ms 단위
    };

    function test8(){
        clearInterval(intervalObj); // window 이름 생략된 형태
    }
</script>
```
