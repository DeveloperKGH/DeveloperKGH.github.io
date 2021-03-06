---
layout: post
title: (Javascript) Number 64비트 부동소수점
categories: Javascript
tags: [Javascript, 기본문법]
---

## :bulb: Javascript Number 64비트 부동소수점
* 컴퓨터는 '0' 과 '1' 로 이루어진 2진법으로 계산
* 자바스크립트에서 숫자는 '64 비트 IEEE 754 형식'으로 다뤄짐 <font color='red'><strong>(64비트 중 52비트는 숫자를 저장하는 데 사용되고, 11비트는 소수점 위치를(정수는 0), 1비트는 양수/음수 부호를 저장하는 데 사용)</strong></font>
* <font color='red'><strong>10진법으로 표현된 수를 2진법으로 변환 시 무한소수가 발생할수도 있는데(64비트를 초과하는), 64비트 공간에 맞도록 유한하게 표현하려다 보니 미세한 값들이 초과하거나 손실 (근사치로 표현)</strong></font>
* 2진법으로 변환 된 수가 무한소수인 경우 근사치로 저장하기 때문에, 계산시 미세한 오차가 발생
* Javascript 를 사용하여 수를 연산하는 경우 '64비트 부동소수점'을 고려하여 올바르게 연산할 수 있는 외부 라이브러리를 사용 ('BigNumber.js', 'Big.js', 'Decimal.js')
