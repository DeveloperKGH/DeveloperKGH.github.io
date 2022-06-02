---
layout: post
title: (Javascript) 내장함수 - String
categories: Javascript
tags: [Javascript, 기본문법]
---

## :bulb: Javascript String 내장함수
* 문자열을 다양하게 다룰 수 있도록 다양한 method 제공
* ex) length, indexOf, lastIndexOf, search, slice, substring, substr, replace, replaceAll, uppercase, lowercase, concat, trim, padStart, padEnd, charAt, split

<br>


##### String 내장함수 종류
* length
  - 문자열 길이를 알려주는 함수

~~~javascript
let alphabet = "ABCDEFGHIJKLMN";
console.log(alphabet.length); // 문자열 길이 출력 : 14
~~~
<br>

* indexOf / lastIndexOf
  - 찾을 문자열과 일치하는 문자열의 최초 문자 Index를 반환하는 함수
  - 일치하는 문자가 없는 경우 <font color='red'><strong>-1</strong></font> 반환
  - indexOf : 문자열을 <font color='red'><strong>왼쪽</strong></font>부터 찾음
  - lastIndexOf : 문자열을 <font color='red'><strong>오른쪽</strong></font>부터 찾음

~~~javascript
let txt = "My first name is Beau. My last name is Kim. My full name is Beau Kim.";

//indexOf
console.log(txt.indexOf('Beau')); // 'Beau' 라는 문자열을 왼쪽에서 부터 찾아 해당 인덱스 번호 출력 : 17
console.log(txt.indexOf('John')); // 'John' 에 해당하는 문자열이 없음 : -1

//lastIndexOf
console.log(txt.lastIndexOf('Beau')); // 'Beau' 라는 문자열을 오른쪽에 부터 찾아 해당 인덱스 번호 출력 : 60
console.log(txt.lastIndexOf('John')); // 'John' 에 해당하는 문자열이 없음 : -1
~~~
<br>

* search
  -  찾을 문자열이 포함되어있는지 확인하고, 포함되어 있다면 해당 첫 문자의 Index를 반환하는 함수 (indexOf 와 동일)
  - 일치하는 문자가 없는 경우 <font color='red'><strong>-1</strong></font> 반환

~~~javascript
let txt = "Hello World !!"
console.log(txt.search('World')); // 'World' 라는 문자열을 왼쪽에서 부터 찾아 해당 인덱스 번호 출력 : 6
console.log(txt.search('Bye')); // 'Bye' 에 해당하는 문자열이 없음 : -1
~~~
<br>

* slice
  -  문자열의 특정 부분을 잘라내서 가져오는 함수
  - '-' 가 오는 경우 뒤에서부터 계산
  - slice(start, end)
    - start : 추출을 시작할 인덱스
    - end : 추출을 종료할 인덱스 (end 를 제외하고 그 전까지의 요소만 추출)

~~~javascript
let fruits = "Apple, Banana, Kiwi";
console.log(fruits.slice(7, 13)); // 시작점 : 7번째 index, 끝점 : 13번째 index 이전까지 추출 : Banana
console.log(fruits.slice(7)); // 끝점을 지정안해주면 시작점부터 끝까지 모두 가져옴 : Banana, Kiwi
console.log(fruits.slice(-12, -6)); // '-'는 뒤에서부터 계산 : Banana
~~~
<br>

* substring
  -  문자열의 특정 부분을 잘라내서 가져오는 함수
  - '-' 가 오는 경우 0으로 치환
  - substring(start, end)
    - start : 추출을 시작할 인덱스
    - end : 추출을 종료할 인덱스 (end 를 제외하고 그 전까지의 요소만 추출)

~~~javascript
let alphabet = "ABCDEFG";
console.log(alphabet.substring(0, 2)); // 시작점 : 0번째 index, 끝점 : 2번째 index 이전까지 추출 : AB
console.log(alphabet.substring(-3, 3)); // 시작점 : '-3' 이 '0' 으로 치환 index, 끝점 : 3번째 index 이전까지 추출 : ABC
~~~
<br>

* substr
  - 특정 index 부터, 특정 length 길이만큼 문자열을 가져오는 함수
  - substr(start, length)
    - start : 추출을 시작할 인덱스
    - length : 추출할 문자열 길이

~~~javascript
let birth = '940111';
console.log(birth.substr(0, 2)); //0번째 index 부터 2글자 -> year : 94 
console.log(birth.substr(2, 2)); //2번째 index 부터 2글자 -> month : 01
console.log(birth.substr(4, 2)); //4번째 index 부터 2글자 -> day : 11
~~~
<br>

* replace
  - 특정 문자열을 다른 문자열로 교체하는 함수

~~~javascript
let str = "Please visit here!";
console.log(str.replace("here", "there")); // 'here' 문자열을 'there' 로 변환 : Please visit there!

let str2 = "Please visit here here here!";
console.log(str2.replace("here", "there")); // 제일 앞 'here' 문자열만 교체 : Please visit there here here!
~~~
<br>

* replaceAll
  - 특정 문자열에 해당하는 모든 문자열을 다른 문자열로 일괄적으로 교체하는 함수

~~~javascript
let str3 = "Please visit here here here!";
console.log(str3.replaceAll("here", "there")); // 모든 'here' 문자열 교체 :  Please visit there there there!
~~~
<br>

* toUpperCase / toUpperCase
  - 문자열을 모두 대문자 또는 소문자로 교체하는 함수

~~~javascript
//uppercase
let lowerCase = 'beaukim';
console.log(lowerCase.toUpperCase()); // 대문자로 변경하여 출력 : BEAUKIM

//lowercase
let upperCase = 'BEAUKIM';
console.log(upperCase.toLowerCase()); // 소문자로 변경하여 출력 : beaukim
~~~
<br>

* concat
  - 인자로 넘긴 문자열을 기존 문자열 뒤에 합치는 함수

~~~javascript
let c1 = 'Hello';
let c2 = 'World';
let c3 = '!!!';
console.log(c1.concat(' ', c2, ' ', c3)); // 인자로 넣어준 문자열을 모두 붙여줌 : Hello World !!!
~~~
<br>

* trim
  - 문자열 양쪽 끝 공백을 제거해주는 함수

~~~javascript
let t = "       Hello World!            ";
console.log(t);
console.log(t.trim()); //양쪽 끝 공백 모두 제거 : Hello World!
~~~
<br>

* charAt
  - 인자로 넘긴 index에 해당하는 문자형 데이터를 반환하는 함수

~~~javascript
let c = 'Hello World';
console.log(c.charAt(0)); // 문자열에서 0번째 인덱스인 첫번째 글자를 가져옴 : 'H'
~~~
<br>

* padStart / padEnd
  - pad는 좌우에 특정한 문자열로 채우는 함수
  - pad...(maxLength, fillString);
    - maxLength : 문자열 길이
    - fillString : 채울 문자열

~~~javascript
//padStart
let p1 = '5';
console.log(p1.padStart(4, '0')); // 4글자로 만들어주고 앞자리는 0으로 채움 : 0005

//padEnd
let p2 = '15';
console.log(p2.padEnd(4, '0')); // 4글자로 만들어주고 뒷자리는 0으로 채움 : 1500
~~~
<br>

* split
  - 문자열을 특정 문자를 기준으로 분리하여 각각 배열로 반환하는 함수

~~~javascript
let tags = '키보드,기계식,블루투스';
console.log(tags.split(',')); // ',' 기준으로 문자열을 분리하여 배열로 만듬 : ['키보드', '기계식', '블루투스']
~~~
<br>
