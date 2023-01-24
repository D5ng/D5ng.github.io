---
title: 8장. 제어문
author: D5ng
date: 2023-01-23 00:01 +09:00
layout: post
category: JavaScript
---

### 제어문

제어문은 조건에 따라 코드 블록을 실행하거나 반복 실행 할 때 사용한다.  
일반적으로 코드는 위에서 아래로 순차적으로 실행된다.  
제어문을 사용하면 코드의 실행 흐름을 인위적으로 제어할 수 있다.

### 블록문

블록문은 0개 이상의 문을 중괄호로 묶은것으로, 코드 블록 또는 블록이라고 부른다.  
자바스크립트는 블록문을 하나의 실행 단위로 취급한다.

### 조건문

조건문은 주어진 조건식의 평가 결과에 따라 코드 블록의 실행을 결정한다.  
조건식은 불리언 값으로 평가될 수 있는 표현식이다.

### if ~ else문, if ~ else if ~ else

```js
// 문법

if(조건식){
	// true일때 실행
}

if(조건식){
	// true일때 실행
} else {
	// 위 조건식을 만족못하면 실행 (false일 때)
}


if(첫번째 조건식){
	// true일때 실행
} else if(두번째 조건식){
	// 첫번째 조건식을 만족못하면 두번째 조건식을 실행한다.
	// 두번째 조건식도 만족을 못하면 바로 else문으로 간다.
} else {
	// 위 조건식을 만족못하면 실행 (false일 때)
}
```

### 예시코드

```js
var yourName = prompt("당신의 이름은?");

if (yourName === "dongs") {
	alert("당신의 이름이 맞습니다.");
}

if (yourName === "dongs") {
	alert("당신의 이름이 맞습니다.");
} else if (yourName === "동현") {
	alert("당신의 이름이 맞습니다.");
} else {
	alert("당신의 이름이 아닙니다. 다시 시도하세요");
	window.location.reload();
}
```

### 삼항 연산자

if문과 else문만 사용한다면, 삼항연산자로 코드를 더 간결하게 표현할 수 있다.  
삼항 연산자는 값으로 평가되는 표현식을 만든다. 반면에 if else는 표현식이 아닌 문이다.

```js
// 문법
// 조건식 ? true일 때 : false일 때

10 > 5 ? console.log("true 입니다.") : console.log("false 입니다.");
```

### switch문

if ~ else if문처럼 조건이 여러개가 생겨야한다면 Switch문으로 간결하게 표현이 가능하다.

```js
// 문법
switch (표현식) {
	case 표현식1:
		// 표현식이 표현식1과 일치하면 실행
		break; // break는 switch문을 탈출하는 역할을 한다. 표현식1번이 일치하면 코드를 실행하고
	// 밑에 있는 case들을 안거치고 바로 탈출한다.

	case 표현식2:
		// 표현식이 표현식2과 일치하면 실행
		break;

	case 표현식3:
		// 표현식이 표현식3과 일치하면 실행
		break;

	default:
		// 위에 표현식에 일치하는게 없을때 실행.
		break;
}

// 예제
var drink = prompt("어떤 음료수를 마시고싶으신가요?");

// 사용자가 입력한 값이 drink라면
switch (drink) {
	case "콜라":
		console.log(`${drink}를 선택하셨습니다!`);
		break;
	case "사이다":
		console.log(`${drink}를 선택하셨습니다!`);
		break;
	case "환타":
		console.log(`${drink}를 선택하셨습니다!`);
		break;
	default:
		console.log("고르신 음료가 여기에는 없습니다.");
}
```

### 반복문

반복문은 조건식의 평가 결과가 참인 경우 코드 블록을 실행한다.  
그 후 조건식을 다시 평가하여 여전히 참인경우 코드 블록을 실행한다.

### for문

for문은 조건식이 거짓으로 평가될 때까지 코드 블록을 반복 실행한다.

```js
// 문법
for(변수 선언문 또는 할당문; 조건식; 증감식){
	// 반복적으로 실행할 코드
}
```

```js
// 예제코드
// 구구단 2단 출력하기.

for (var i = 1; i <= 9; i++) {
	console.log(`2 * ${i} = ${2 * i}`);
}
```

### while문

while문은 주어진 조건식의 평가 결과가 참이면 코드 블록을 무한반복한다.  
for문은 반복횟수가 정해질때 사용하고, while문은 반복횟수가 불명확할때 사용한다.

```js
var count = 0;

while (count < 3) {
	console.log(count); // 1, 2, 3
	count++;
}

// 조건식이 true라면 무한루프를 돌게된다.
// 따라서 while문 안에서 탈출 할 수 있게 조건문을 만들고 break로 해결 할 수 있다.

var count = 0;

while (true) {
	if (count === 999) {
		// count가 999가되면 탈출.
		break;
	}

	count++;
}
```

### break문

break문은 레이블 문, 반복문(for, for in, for of, while, do while) 또는 switch문의 코드 블록을 탈출한다.  
레이블문, 반복문, switch문을 제외하고 break문을 사용하게되면 SyntaxError(문법에러)가 발생한다.

```js
for (let i = 0; i < 10; i++) {
	if (i === 5) {
		break;
	}

	console.log(i); // 0, 1, 2, 3, 4
}

// i가 5일때 코드 블록을 탈출하는 break문을 사용했기 때문에 5에서 for문을 반복하지않고 끝낸다.
```

### continue문

continue문은 break문과 달리, 코드 블록을 탈출하지않고 한 턴 건너뛴다.

```js
for (let i = 0; i < 10; i++) {
	if (i === 5) {
		continue;
	}

	console.log(i); // 0, 1, 2, 3, 4, 6, 7, 8, 9
}

// i가 5일때 건너뛰고 다시 반복문을 돌면서 6으로 넘어간다.
```
