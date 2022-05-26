---
layout: post
title: (Javascript) 조건문
categories: Javascript
tags: [Javascript, 기본문법]
---

## :bulb: Javascript 조건문
* <font color='red'><strong>조건문이란 특정한 조건 아래서만 코드가 실행되게 하는 구문</strong></font>
* ex) if, else if, else, switch
<br>

#### 조건문 종류
* if 문
  * if (조건) {내용} : <font color='red'><strong>조건이 true 인 경우에 내용이 실행</strong></font>

  ~~~javascript
  let age = 19;
  if (age > 18) {
    console.log("당신은 성인입니다.");
  }

  // "당신은 성인입니다." 출력
  ~~~

  <br>

* else if, else 문
  * <font color='red'><strong>'else if' 는 조건을 여러개로 하고 싶을 때 사용</strong></font>
  * <font color='red'><strong>'else' 는 'if' 조건이 false 일 때 실행</strong></font>

  ~~~javascript
  let hour = 14;
  if (hour < 10) {
      console.log("Good Morning!");
  } else if (hour < 18) {
      console.log("Good Afternoon!");
  } else if (hour < 21) {
      console.log("Good Evening!");
  } else {
      console.log("Good Night!");
  }

  // "Good Afternoon!" 출력
  ~~~

  <br>

* switch 문
  * <font color='red'><strong>'switch' 뒤에 오는 값으로 'case' 에 해당하는 조건 실행</strong></font>
  * <font color='red'><strong>'default' 는 어떤 조건에도 해당이 안 될 때 실행</strong></font>

  ~~~javascript
  let day = new Date().getDay();
  let dayName;
   switch (day) {
     case 0:
         dayName = '일요일';
         break;
     case 1:
         dayName = '월요일';
         break;
     case 2:
         dayName = '화요일';
         break;
     case 3:
         dayName = '수요일';
         break;
     case 4:
         dayName = '목요일';
         break;
     case 5:
         dayName = '금요일';
         break;
     case 6:
         dayName = '토요일';
         break;
     default:
         dayName = '';
         break;
 }

   console.log(dayName); // 0 ~ 6 : 일요일 ~ 토요일 출력
  ~~~

  <br>
