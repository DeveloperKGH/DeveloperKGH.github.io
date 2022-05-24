---
layout: post
title: Javascript 연산자
categories: Javascript
tags: [Javascript, 기본문법]
---

## :eyes: Javascript 연산자
* 주어진 식을 계산하여 결과를 얻어내는 과정을 **'연산'**
* '연산자'란 프로그래밍에서 쓰이는 기호
* ex) 산술 연산자, 문자열 연산자, 증감 연산자, 지수 연산자, 대입 연산자, 비교 연산자, 삼항 연산자, 논리 연산자 등
<br>

#### 연산자 종류
* 산술 연산자
  * 덧셈(+), 뺄셈(-), 곱셈(*), 나눗셈(/), 나머지(%)로 구성
  ~~~javascript
  let a = 4 + 2; // 6
  let b = 3 - 2; // 1
  let c = 5 * 2; // 10
  let d = 6 / 2; // 3
  let e = 8 % 3; // 2
  ~~~
<br>

* 문자열 연산자
  *  '+' 연산자는 문자열이 아닌 데이터는 문자열로 바꿔서 연산  
  ~~~javascript
  let str1 = 'Beau ' + 'Kim'; // Beau Kim
  str1 += ' Male'; // Beau Kim Male
  let str2 = 'Beau ' + 2; // Beau 2
  let str3 = '1' + 7; // 17 (문자열)
  let str4 = 3 + 4 + ' Beau'; // 7 Beau (문자열)
  ~~~
<br>

* 증감 연산자
  * 변수에 1을 더하거나 뺌
  * 앞에 붙으면 전위 증감 연산자, 뒤에 붙으면 후위 증감 연산자
  ~~~javascript
  let x = 0;
  console.log(x++); // 후위 증감 연산에 따라 먼저 콘솔에 출력하고, x에 +1 : 0 출력
  console.log(++x); // 전위 증감 연산자에 따라 x에 +1 을 먼저하고, 콘솔에 출력 : 2 출력
  ~~~
<br>

* 지수 연산자
  * 거듭제곱을 올린 결과를 반환
  ~~~javascript
  let x = 2 ** 3; // 8
  ~~~
<br>

* 대입 연산자
  * '=' 로 변수에 값을 대입하는 연산자
  * 복합대입연산자 : '+=', '-=', '*=', '/='
  ~~~javascript
  let x = 10;
  x += 3; // x = x + 3; -> 13
  x -= 5; // x = x - 5; -> 8
  x *= 2; // x = x * 2; -> 16
  x /= 4; // x = x / 4; -> 4
  ~~~
<br>

* 비교 연산자
  * 두 값을 비교('==', '===', '!=', '!==', '>', '>=', '<', '<=')
  ~~~javascript
  console.log(1 == 1); // true
  console.log(1 != 3); // true
  console.log(3 > 2); // true
  console.log(3 < 2); // false
  ~~~
<br>

* 삼항 연산자
  * 조건 ? 참 : 거짓
  ~~~javascript
  let x = 4 > 3 ? 1 : 0; // (4 > 3) 조건이 true 이므로 1 출력
  ~~~
<br>

* 논리 연산자
  * '&&', '||', '!'으로 구성 된 논리식을 판단
  ~~~javascript
  console.log(3 > 2 && 1 > 2); // false (조건이 모두 만족해야 true 반환)
  console.log(3 > 2 || 1 > 2); // true (조건중 하나만 만족하더라도 true 반환)
  console.log(!(3 > 2)); // false (논리식의 결과가 true 이므로 반대인 false 반환)
  console.log(!(3 < 2)); // true (논리식의 결과가 false 이므로 반대인 true 반환)
  ~~~
<br>

#### :exclamation: **'==' 와 '===' 의 차이**
  * 자바스크립트는 **엄격한 비교**와 **유형변환 비교**를 모두 지원
  * '==' : 자동으로 자료형을 바꿔 값만 비교 (**유형변환 비교**)
  * '===' : 값 뿐만 아니라 자료형까지 모두 비교 (**엄격한 비교**)

![==, === 1](https://dhananjay25.files.wordpress.com/2014/03/image8.png)

  ~~~javascript
  // '==' (유형변환 비교)
  0 == '' // true
  0 == false // true
  0 == [] // true
  1 == '1' // true
  null == undefined // true

  // '===' (엄격한 비교)
  0 === '' // false
  0 === false // false
  0 === [] // false
  1 === '1' // false
  null === undefined // false
  ~~~
<br>

  ![==, === 2](https://velog.velcdn.com/post-images%2Ffiloscoder%2F8d6f8a80-fa17-11e9-b483-31f82d28ec79%2FabY0g3L700bwp.webp)
