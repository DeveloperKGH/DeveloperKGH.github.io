---
layout: post
title: (Javascript) 반복문
categories: Javascript
tags: [Javascript, 기본문법]
---

## :bulb: Javascript 반복문
* **반복문이란 반복문이란 프로그램 내에서 똑같은 명령을 일정 횟수만큼 반복하여 수행하도록 제어하는 명령문**
* ex) for, for in, for of, while, do while 등
<br>

#### 반복문 종류
* **for**
  * **초기식**, **조건식**, **증감식**을 포함하고 있는 고전적인 형태의 반복문
  * for (초기식; 조건식; 증감식) {조건식의 결과가 참인 동안 반복적으로 실행}

  ~~~javascript
  //EX1
  for (let i = 0; i < 5; i++) {
      console.log("The number is " + i); // 0, 1, 2, 3, 4 출력
  }

  //EX2
  let j = 1;
  let total = 0;
  for (; j <= 10; j++) {
      total = total + j;
  }
  console.log("total : ", total); // 55 (1 ~ 10 까지의 합) 출력

  //EX3
  let nums = [17, 23, 5, 39];
  let len = nums.length

  for (let k = 0; k < len; k++) {
      console.log(nums[k]); // 배열의 idx 순서대로 17, 23, 5, 39 출력
  }
  ~~~

  <br>

* **for in**
  * 객체의 프로퍼티 키 열거 전용 반복문

  ~~~javascript
  //EX1
  let nums = [17, 23, 5, 39];
  for (let i in nums) {
          console.log(i); // 배열의 idx 0, 1, 2, 3 출력
          console.log(nums[i]); // 배열의 idx 순서대로 17, 23, 5, 39 출력
      }

  //EX2
  let person = {
      firstName : "Beau",
      lastName : "Kim",
      age : 29
  };

  for (let key in person) {
      console.log(key); // 객체의 key 값 'firstName', 'lastName', 'age' 출력
      console.log(person[key]); // 객체의 key 값 순서대로 'Beau', 'Kim', 29 출력
  }
  ~~~

  <br>

* **for of**
  * 이터러블(Iterable) 순회 전용 반복문
  * **이터러블(Iterable)** : 이터레이터를 반환하는 메서드 가지는 자료를 반복할 수 있는 객체(Array, String, Map 등)

  ~~~javascript
  let cars = ["KIA", "Volvo", "BMW"];
  for (let car of cars) {
      console.log(car); // 배열의 idx 순서대로 "KIA", "Volvo", "BMW" 출력
  }
  ~~~

  <br>

* **while**
  * 특정 조건을 만족할 때까지 계속해서 주어진 명령문을 반복 실행
  * while (조건식) {조건식의 결과가 참인 동안 반복적으로 실행}

  ~~~javascript
  let l = 1;
  while (l <= 10) {
      console.log("l : ", l); // 1 ~ 10 까지 순차적으로 출력
      l++; // while 문에서 빠져나오기 위하여 조건식 값을 ++
  }
  ~~~

  <br>  

* **do while**
  * 'while'의 변형으로 do의 내용을 최초 1번 먼저 실행 후 조건을 비교
  * do {해당 블럭의 내용을 선 실행후 조건식 체크} while (조건식)

  ~~~javascript
  let m = 11;
    do {
        console.log("m : ", m) // while 조건식은 false 이지만, do 블럭의 내용이 1번 실행되어 11이 출력됨
        m++;
    } while (m <= 10);
  }
  ~~~

  <br>

#### :exclamation: **'Break' 와 'Continue'**
  * **'Break'** 문은 자신이 포함된 가장 가까운 반복문을 벗어남
  * **'Continue'** 문은 반복문의 끝으로 이동하여 다음 반복으로 넘어감
  * 차이점 : 'Continue' 문은 'Break' 문과 다르게 **반복문 전체를 벗어나지 않고, 다음 반복을 계속해서 수행**

  ~~~javascript
  // break
  for (let i = 0; i < 10; i++){
    if(i == 5){
      break; // i값이 5가 되는 순간 반복문 탈출 : 0~4 까지만 출력
    }
    console.log(i);
  }

  // continue
  for (let i = 0; i < 10; i++){
      if(i % 2 === 0){
        continue; // i가 짝수라면, 다음 반복으로 넘어감 : 홀수만 출력
      }
      console.log(i);
  }
  ~~~
<br>
