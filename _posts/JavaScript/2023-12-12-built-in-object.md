---
title: "내장 객체"
categories: JavaScript
---

# String 내장 객체
{: .notice--warning}

```html
<script>
    var str = 'Hello Javascript World!';
    var str2 = 'test';
        
    document.write(str+'<br>'); 
    document.write('length : ' + str.length + '<br>'); // 길이
    document.write('toUpperCase : ' + str.toUpperCase() + '<br>'); // 대문자
    document.write('toLowerCase : ' + str.toLowerCase() + '<br>'); // 소문자
    document.write('indexOf1 : ' + str.indexOf('J') + '<br>'); // 문자열 찾기 
    document.write('indexOf2 : ' + str.indexOf('Java') + '<br>'); // 문자열 찾기 
    document.write('indexOf3 : ' + str.indexOf('python') + '<br>'); // 문자열 찾기, 없으면 -1
    document.write('lastIndexOf : ' + str.lastIndexOf('l') + '<br>'); // 문자열 찾기 뒤부터
    document.write('charAt : ' + str.charAt(1) + '<br>'); // 위치에 있는 문자 가져오기 
    document.write('substr : ' + str.substr(1, 4) + '<br>'); // 문자열 자르기
    document.write('slice : ' + str.slice(5) + '<br>'); // 문자열 자르기2
    document.write('padStart : ' + str2.padStart(str2.length+5, '*') + '<br>'); // 문자열 채우기
    document.write('padEnd: ' + str2.padEnd(str2.length+5, '*') + '<br>'); // 문자열 채우기
    document.write('replace : ' + str.replace('Javascript','Java') + '<br>'); // 문자열 바꾸기
    document.write('split : ' + str.split('') + '<br>'); // 문자열 분리 -> 공백인 경우 모든 문자열 잘라짐
    document.write('split : ' + str.split(' ') + '<br>'); // 문자열 분리
    document.write('concat : ' + str.concat('Hello JS World!').concat('<br>')); // 문자열 합치기
    document.write('startsWith : ' + str.startsWith('Hello')); // Hello로 시작하는지
    document.write('startsWith : ' + str.startsWith('Hi')); // Hi로 시작하는지
    document.write('endsWith : ' + str.endsWith('World!')); // World로 끝나는지
    document.write('endsWith : ' + str.endsWith('world')); // world로 끝나는지
</script>
```

# String 객체의 HTML 관련 메서드
{: .notice--warning}

```html
<!-- HTML 속성으로 조정하는 방법임으로 CSS 에서 사용X -->
<!-- HTML4 사용시 활용했던 메서드로, 현재 HTML5에서는 권장되지 않음 -->
<div id="div1"></div>
<script>
    var div1 = document.getElementById("div1");
    var str1 = "Hello JavaScript World!!";
    var str2 = new String("Hello JavaScript World!!");
    div1.innerHTML += str1 + "<br>";
    div1.innerHTML += str2 + "<br><br>";
    div1.innerHTML += " anchor() : " + str1.anchor() + "<br>";
    div1.innerHTML += " big() : " + str1.big() + "<br>";
    div1.innerHTML += " bold() : " + str1.bold() + "<br>";
    div1.innerHTML += " fontcolor('red') : " + str1.fontcolor('red') + "<br>";
    div1.innerHTML += " fontsize(15) : " + str1.fontsize(15) + "<br>";
    div1.innerHTML += " italics() : " + str1.italics() + "<br>";
    div1.innerHTML += " link() : " + str1.link("http://www.naver.com") + "<br>";
    div1.innerHTML += " small() : " + str1.small() + "<br>";
    div1.innerHTML += " strike() : " + str1.strike() + "<br>";
    div1.innerHTML += " sub() : " + str1.sub() + "<br>";
    div1.innerHTML += " sup() : " + str1.sup() + "<br>";
</script>
```

# Number 관련 메서드
{: .notice--warning}

```html
<div id="div2"></div>
<script>
    var num1 = 123;
    var num2 = 123.4567893333333333333333333;
    var num3 = new Number(1234);

    var str = '';
    str += 'num1 원본 : ' +  num1 + '<br>';
    str += 'num2 원본 : ' +  num2 + '<br>';
    str += 'num3 원본 : ' +  num3 + '<br>';

    // 지수 형태로 출력
    str += '지수 형태 <br>'
    str += 'num1 : ' +  num1.toExponential() + '<br>';
    str += 'num2 : ' +  num2.toExponential() + '<br';
    
    // 고정소수점 출력, 반올림
    str += '고정 소수점 <br>'
    str += 'num1 : ' +  num1.toFixed() + '<br>';
    str += 'num2 : ' +  num2.toFixed() + '<br>';
    str += 'num1 : ' +  num1.toFixed(2) + '<br>';
    str += 'num2 : ' +  num2.toFixed(2) + '<br>';
        
    // 자동으로 지수 또는 고정소수점으로 표현하는 방법
    str += '숫자가 크면 자동으로 지수표현 <br>';
    str += 'num1 : ' +  num1.toPrecision() + '<br>';
    str += 'num2 : ' +  num2.toPrecision() + '<br>';
    str += 'num3 : ' +  new Number(219321873092180938210938210938120).toPrecision() + '<br>';

    // Number의 주요 속성값
    str += 'Number.MAX_VALUE : ' +  Number.MAX_VALUE +'<br>' 
    str += 'Number.MIN_VALUE : ' + Number.MIN_VALUE +'<br>' 
    str += 'Number.NaN : ' + Number.NaN +'<br>' 
    str += 'Number.POSITIVE_INFINITY : ' + Number.POSITIVE_INFINITY +'<br>' 
    str += 'Number.NEGATIVE_INFINITY : ' + Number.NEGATIVE_INFINITY +'<br>' 

    document.getElementById('div2').innerHTML = str;
</script>
```

# Math 관련 메서드
{: .notice--warning}

```html
<div id="div4"></div>
<script>
    var str = ''
    // 난수 발생
    var number = Math.random(); // 0 ~ 1까지의 난수 범위
    str += '난수 : ' + number + '<br>';
    str += '난수(1~100) : ' +number*100 + 1 + '<br>';
    str += '난수(1~100) : ' + Math.floor(number*100 + 1) + '<br>';
    
    // 반올림, 소수점 기준 일의 자리만 반올림
    str += '반올림 : ' + Math.round(3.6) + '<br>'; // 4
    str += '반올림 : ' + Math.round(3.126) + '<br>'; // 3

    // max, min값 구하기
    numberArray = [1,2,10,3,4,8,5,6,7,];
    // ... : 열거형 데이터형에서 배열로 값을 넣을때 사용하는 문법
    str += '가장 큰수(max) : ' + Math.max(... numberArray) + '<br>';
    str += '가장 작은수(min) : ' + Math.min(... numberArray) + '<br>';
    // eval
    str += '가장 큰수(max) : ' + eval('Math.max('+numberArray+')') + '<br>';
    str += '가장 작은수(min) : ' + eval('Math.min('+numberArray+')')  + '<br>';

    document.getElementById('div4').innerHTML = str;
</script>
```

# Date 내장 객체
{: .notice--warning}

```html
<div id="div3"></div>
<script>
    var str = '';
    // date 표현법, 웬만한 표기는 자동으로 파싱하여 date로 생성해줌
    // var date1 = Date();
    var date1 = new Date(); // 현재시간
    var date2 = new Date('2023-12-14'); 
    var date3 = new Date('2023.12.14'); 
    var date4 = new Date('2023-12-14 13:05:47'); 
    var date5 = new Date('2023-12-14T13:05:47'); // iso 표준 표기 
    var date6 = new Date('2023/12/14 13:05:47'); 
    var date7 = new Date('Dec. 14, 2023 13:05:47'); 
    var date8 = new Date('December 14, 2023'); 
    var date9 = new Date('December 14, 2023 13:05:47'); 
    var date10 = new Date('Thu Dec 14 2023 13:05:47 GMT+0900'); 

    // eval을 이용해 문자열 변수명으로 조회
    for(var i = 1; i <= 10; i++){
        var name = 'date' + i;
        var date = eval(name);
        str += name + ' : ' + date + '<br>';  
    }
    str += '<br>';

    // 현지시간 포멧으로 출력하는 방법, 브라우저나 시스템에 따라 달라짐 
    str += 'toLocaleDateString : ' + date1.toLocaleDateString() + '<br>';
    str += 'toLocaleTimeString : ' + date1.toLocaleTimeString() + '<br>'; 
    str += 'toLocaleString : ' + date1.toLocaleString() + '<br>';

    // 데이터 가져오는 법
    str += 'getFullYear() : ' + date1.getFullYear() + '<br>';
    str += 'getMonth() : ' + date1.getMonth() + '<br>'; // 월은 0부터
    str += 'getDate() : ' + date1.getDate() + '<br>';
    str += 'getDay() : 요일 : ' + date1.getDay() + '<br>';
    str += 'getHours() : ' + date1.getHours() + '<br>';
    str += 'getMinutes() : ' + date1.getMinutes() + '<br>';
    str += 'getSeconds() : ' + date1.getSeconds() + '<br>';
    str += 'getMilliseconds() : ' + date1.getMilliseconds() + '<br>';
    str += 'getTime() : ' + date1.getTime() + '<br>';

    // 날짜 변경하는 방법 = setter 사용
    date1 = new Date();
    date1.setFullYear(2020); // 연도변경, setter로 연월일시 변경이 가능
    date1.setMonth(10); // 월
    date1.setDate(1); // 날짜
    date1.setHours(10); // 시
    date1.setMinutes(30); // 분
    date1.setSeconds(50); // 초

    // 응용 예제
    str += '변경된 날짜/시간 : ' + date1.toLocaleString() + '<br>';
    str += '날짜 간격 구하는 방법1 : ' + (new Date() - date1) + '<br>'; // ms단위 시간 gap 구하기 
    str += '날짜 간격 구하는 방법2 : ' + new Date(new Date() - date1).toLocaleString() + '<br>';
    var gap = new Date() - date1; // ms gap 
    var gapDate = Math.floor(gap / (1000*60*60*24)); // ms, 초, 분, 시간
    str += '날짜 간격 일수로 표기 : ' + gapDate + '일<br>';

    document.getElementById('div3').innerHTML = str;
</script>
```