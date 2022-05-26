---
layout: post
title: (Javascript) 함수
categories: Javascript
tags: [Javascript, 기본문법]
---

## :bulb: Javascript 함수
* <font color='red'><strong>함수(function)란 어떤 목적을 가진 작업들을 수행하는 코드들이 모인 블록을 의미</strong></font>
* 일반적으로 "입력"" – > "함수" – > "return" – > "출력" 형태
* ex) function name() {//수행 내용}
* 자바스크립트의 함수는 <font color='red'>일급 객체</font> 라고 하며, 변수나 배열에 저장할 수 있음

<br>

>  용어 정리
>> **1. 일급시민 (First-Class Citizen)** <br>
   = 변수(variable)에 담을 수 있다. <br>
   =  함수의 인자(parameter)로 전달할 수 있다. <br>
   = 함수의 반환값(return value)으로 전달할 수 있다. <br>
>> <br>
>> **2. 일급객체(First-Class-Object)** <br>
   =  일급시민의 조건을 충족하는 객체 <br>
>> <br>
>>**3. 일급함수(First-Class-Function)** <br>
  = 일급시민의 조건을 충족하는 함수 <br>
  <br>
  <br>
>> 참고링크 : https://goddaehee.tistory.com/228
<br>

<br>

#### 함수 구성
* **함수명**
  - 함수명은 함수 내부 코드에서 자신을 재귀적으로 호출하거나 자바스크립트 디버거가 해당 함수를 구분하는 식별자로 사용  
  - 다만 함수명은 선택사항. 이때 함수명이 없는 함수를 익명 함수라 부름
* **매개변수 (parameter)**
  - 함수의 정의에서 전달받은 인수를 함수 내부로 전달하기 위해 사용하는 변수
  - C, Java 언어와 다르게, 변수 타입을 기술하지는 않음
* **실행문**
  - 어떤 목적을 가진 작업들을 수행하는 코드들이 모임
* **반환문(Option)**
  - 반환문은 함수의 실행을 중단하고, return 키워드 다음에 명시된 표현식의 값을 호출자에게 반환
  - 반환시 리턴 타입 제한은 없음
<br>

#### 함수 생성방법
##### 1. 함수 선언문(Function Declarations)
* 'function' 키워드로 시작
* 선언된 함수는 나중 사용을 위해 저장 및, 함수를 실행하려면 함수 이름을 호출(call)
* 함수명 정의는 필수

~~~javascript
//EX1 : 세금계산
function calcTax(sales) {
    let vat = 0.1;
    return sales * vat;
}
console.log('tax : ', calcTax(10)); // 1 출력 : 10 * 0.1

//EX2 : 계산기
function calculator(x, y, operator) {
    switch (operator) {
        case "+" :
            return x + y;
        case "-" :
            return x - y;
        case "*" :
            return x * y;
        case "/" :
            return x / y;
        default :
            return "No Such Operator"
    }
}
console.log("calculator : ", calculator(9, 3, "+")); // 12 출력 : 9 + 3
~~~
<br>

##### 2. 함수 표현식 방식(Function Expressions)
* 정의한 function을 별도의 변수에 할당
* 함수명 정의는 필수가 아님

~~~javascript
let sayHi = function() {  // 변수명 sayHi가 곧 함수명이다.
  console.log("Hello");
};

sayHi(); // "Hello" 출력
~~~
<br>

#### :exclamation: **호이스팅(Hoisting)이란?**
  * 호이스팅은 <font color='red'><strong>코드가 실행하기 전 변수선언/함수선언이 해당 스코프의 최상단으로 끌어 올려진 것 같은 현상</strong></font>
  > 호이스팅 과정
  >> 1. 자바스크립트 엔진이 코드를 실행하기 전 실행 가능한 코드를 형상화하고 구분
  >> 2. 자바스크립트 엔진은 코드를 실행하기 전 실행 컨텍스트를 위한과정에서 모든 선언(var, let, const, function)을 스코프에 등록
  >> 3. 코드 실행 전 이미 변수선언/함수선언이 저장되어 있기 때문에 선언문보다 참조/호출이 먼저 나와도 오류 없이 동작 (이는 선언부분이 파일의 맨 위로 끌어올려진 것 처럼 보임)
  >> 실행 컨텍스트 : 실행 가능한 코드가 실행되기 위해 필요한 환경을 의미
  * 자바스크립트의 모든 선언에는 호이스팅이 일어나지만, 'let', 'const', 'class'를 이용한 선언문은 호이스팅이 발생하지 않은 것처럼 동작하여 참조에러 발생 <font color='red'><strong>('var' 키워드는 선언과 함께 undefined로 초기화되어 메모리에 저장되는데 'let'과 'const'는 초기화되지 않은 상태로 선언만 메모리에 저장되기 때문)</strong></font>
  * 오류없이 동작하는 호이스팅 대상 : <font color='red'><strong>'var' 변수 선언, </strong></font> <font color='red'><strong>함수선언문</strong></font>

  ~~~javascript
  // var 변수
  console.log(text1); // undefined 출력
  var text1 = 'Hello';
  console.log(text1); // 'Hello' 출력

  // var 이외의 변수
  console.log(text2); // Uncaught ReferenceError: Cannot access 'text2' before initialization
  let text2 = 'World';

  // 함수선언문
  test(); // 'Hello' 출력

  function test() {
    console.log('Hello');
  }

  // 함수표현식
  test2(); // Uncaught TypeError: test2 is not a function 발생

  var test2 = function() {
      console.log('World');
  }
  ~~~

<br>
<br>

> 참고링크 1 : https://gmlwjd9405.github.io/2019/04/22/javascript-hoisting.html
> 참고링크 2 : https://hanamon.kr/javascript-%ED%98%B8%EC%9D%B4%EC%8A%A4%ED%8C%85%EC%9D%B4%EB%9E%80-hoisting/
