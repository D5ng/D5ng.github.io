---
title: 9장. 타입변환과 단축평가
author: D5ng
date: 2023-01-24 00:00 +09:00
layout: post
category: JavaScript
---

### 타입변환이란 ?

자바스크립트의 모든 값은 타입이 있다.  
자바스크립트는 동적타입언어라서 개발자의 의도에 따라 다른 타입으로 변환할 수 있다.  
개발자가 의도적으로 값의 타입을 변환하는 것을 <strong><u>명시적 타입 변환</u></strong>또는 <strong><u>타입캐스팅</u></strong> 이라고 한다.

개발자의 의도와는 상관없이 표현식을 평가하는 도중에 자바스크립트 엔진에 의해 암묵적으로  
타입이 자동변환되기도 한다. 이를 <strong><u>암묵적 타입 변환</u></strong> 또는 <strong><u>타입 강제 변환</u></strong> 이라고한다.

### 문자열 타입으로 변환

```js
1 + "2"; // "12"
```

위 예제의 + 연산자는 문자열 연결 연산자로 동작한다.  
문자열 연결 연산자의 역할은 문자열 값을 만드는것이기 때문에 숫자 3이아닌 문자열 1 + 문자열 2로 해석해서  
문자열 “12”로 나오는것이다.

### 숫자 타입으로 변환

```js
1 - "1"; // 0

1 * "10"; // 10

1 / "one"; // NaN (Not a Number) 피연산자를 숫자 타입으로 변환할 수 없는 경우는 NaN이 된다.
```

### 불리언 타입으로 변환

자바스크립트 엔진은 조건식의 평가 결과를 불리언 타입으로 암묵적 타입 변환한다.

```js
if ("") console.log(1);
if (true) console.log(2);
if (0) console.log(3);
if ("dongs") console.log(4);
if (null) console.log(5);
```

자바스크립트 엔진은 불리언 타입이 아닌 값을 <strong><u>Truthy (참으로 평가되는 값) Falsy(거짓으로 평가되는 값)</u></strong>
으로 구분한다.

### Falsy 값 (거짓으로 평가되는 값)

- false
- undefined
- null
- ""(공백, 빈 문자열)
- 0, -0
- NaN (Not a Number)

### Truthy 값 (참으로 평가되는 값)

Falsy한 값을 제외한 모두는 Truthy한 값이다.

```js
if ("안녕!!!") {
	// true
	console.log("실행이 돼 ???"); // 실행이 돼 ???
}
```

### 단축평가 (ES6)

논리 연산의 결과를 결정하는 피연산자를 타입 변환하지않고 그대로 반환한다. 이를 단축 평가라고 한다.  
단축 평가는 표현식을 평가하는 도중에 평가 결과가 확정된 경우 나머지 평가 과정을 생략하는 것을 말한다.

#### 논리곱 연산자

논리곱 연산자는 두개의 피연산자가 모두 true로 평가될 때 true를 반환한다. 논리곱 연산자는 좌항에서 우항으로 평가가 진행된다.

```js
var name = "truthy" && "Dongs"; // dongs
```

첫번째 피연산자 truthy는 truthy한 값이므로 true로 평가된다.  
하지만 이 시점까지는 위 표현식을 평가할 수 없다. 두번째 피연산자까지 평가해 보아야 위 표현식을 평가할 수 있다. 결국 <strong><u>논리연산의 결과를 결정하는 두번째 피연산자를 반환하게 된다.</u></strong>

#### 논리합 연산자

논리합 연산자도 좌항에서 우항으로 평가가 진행된다.  
논리합 연산자는 하나만 Truthy로 평가되어도 true를 반환한다.

```js
var name = "Dongs" || false; // Dongs
```

첫번째 피연산자 Dongs는 Truthy한 값이므로 true로 평가된다. 이 시점에서 두번째 피연산자까지 평가해 보지않아도 위 표현식을 평가할 수 있다. 이때 논리합 연산자는 <strong><u>논리 연산의 결과를 결정한 첫번째 피연산자를 반환한다.</u></strong>

### 단축평가를 사용한 if문 대체

어떤 조건이 Truthy 값일때

```js
var done = true;
var message = "";

// if문
if (done) {
	message = "완료";
}

// 단축평가
var message = done && "완료"; // done이 true면 '완료'를 반환
```

Falsy한 값일 때.

```js
var done = false;
var message = "";

message = done || "미완료";
```

### 옵셔널 체이닝 연산자

ES11(ECMAScript 2020)에서 도입된 옵셔널 체이닝 연산자는 ?.는 좌항의 피연산자가 null 또는 undefined인 경우 undefined를 반환하고, 그렇지 않으면 우항의 프로퍼티 참조를 이어간다.

```js
var elem = null;

var value = elem?.value;
console.log(value); // undefined
```

### null 병합 연산자

ES11(ECMAScript 2020)에서 도입된 병합 연산자 ??는 좌항의 피연산자가 null 또는 undefined인 경우 우항의 피연산자를 반환하고, 그렇지 않으면 좌항의 피연산자를 반환한다.

```js
var foo = null ?? "default String";
var space = "" ?? "white Space";

console.log(foo); // 'default String'
console.log(space); // ''
```
