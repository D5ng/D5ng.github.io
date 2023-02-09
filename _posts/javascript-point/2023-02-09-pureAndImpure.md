---
title: 순수 함수와 비순수 함수
author: D5ng
date: 2023-02-06 00:00 +09:00
layout: post
category: JavaScript 핵심
---

함수형 프로그래밍에서는 외부 상태에 의존하지도 않고, 변경하지도 않는 부수 효과가 없는 함수를  
순수함수(pure function)라 하고 외부 상태에 의존하면서 변경하는 함수를  
비순수 함수(impure function)라고 한다.

## 순수 함수

<span class="bg_strong">순수 함수는 동일한 인수를 전달하면 언제나 동일한 값을 반환하는 함수</span>를 말한다.  
어떤 외부 상태(외부 스코프의 변수)에도 의존하지 않고 오직 매개변수를 통해 함수 내부로 전달된  
인수에게만 의존해 값을 생성해 반환한다.

❗️함수 내부에서 호출될 때 마다 바뀌는(newDate, Math.random)값이라면 순수함수가 아니다.

### 비순수 함수

비순수 함수는 <span class="bg_strong">함수 외부 상태를 변경 시키는 부수효과가 있고 외부상태</span>에 의존한다.

```js
// 비순수 함수
let greeting = "Hello";

// 전역변수 greeting을 참조하고 있기 때문에 비순수 함수다.
const sayGreeting = (name) => `${greeting} ${name}`;

sayGreeting("dongs"); // Hello dongs

greeting = "My name is";

// 외부상태에 의존하고있으므로 비순수 함수다.
sayGreeting("dongs"); // My name is dongs
```

```js
// 순수 함수
const sayGreeting = (greeting, name) => `${greeting} ${name}`;

// 외부 상태를 변경하지 않고 매개변수를 받아 그대로 출력한다.
sayGreeting("Hello", "dongs");
sayGreeting("OMG", "dongs");
sayGreeting("My name is", "dongs");
```

### 객체조작 순수 함수, 비순수 함수

```js
// 순수 함수
const userArray = [
	{ user: "woojin", age: 21 },
	{ user: "dong", age: 25 },
	{ user: "jihye", age: 24 },
];

const findUser = (userArray, name) => {
	// Deep Copy
	const [find] = userArray
		.map((u) => ({ ...u }))
		.filter((u) => u.user === name);
	return find;
};

const user = findUser(userArray, "dong"); // userArray를 변경하지 않는다.

user.nickname = "dongs";

console.log(user); // { user: 'dong', age: 25, nickname: 'dongs' }

console.log(userArray);
// [
//  { user: 'woojin', age: 21 },
//  { user: 'dong', age: 25 },
//  { user: 'jihye', age: 24 }
// ]
```

```js
// 순수 함수
const userArray = [
	{ user: "woojin", age: 21 },
	{ user: "dong", age: 25 },
	{ user: "jihye", age: 24 },
];

const findUser = (userArray, name) => {
	// Deep Copy
	const [find] = userArray
		.map((u) => ({ ...u }))
		.filter((u) => u.user === name);
	return find;
};

const user = findUser(userArray, "dong"); // userArray를 변경하지 않는다.

user.nickname = "dongs";

console.log(user); // { user: 'dong', age: 25, nickname: 'dongs' }

console.log(userArray);
// [
//  { user: 'woojin', age: 21 },
//  { user: 'dong', age: 25 },
//  { user: 'jihye', age: 24 }
// ]
```

### 순수 함수에서 사용하면 안되는것

- HTTP 요청
- 데이터 변경
- DOM 조작
- Math.random()
- 현재 시간 얻기
- console.log(), alert, prompt 등등 입출력

### 순수 함수를 사용하면 이점.

순수 함수와 같은 함수형 프로그래밍 개념을 수용하고 부작용을 줄이면 코드를 더 잘 관리하고  
유지 관리 할 수 있다. 다음은 이점에 대한 리스트다.

- 버그 감소
- 문제의 빠른 식별
- 문제 격리
- 재사용 가능성 및 테스트 가능성 증가

<br />

<span class="bg_strong">현재 만들고 있거나, 앞으로 해야할 프로젝트에서 모두 순수 함수로 작성할 수 없다.  
그렇지만 웬만하면 순수 함수로 사용하려고 노력을 해야한다는게 포인트인것 같다.</span>

#### 참고자료.

- 출처 - [자바스크립트 Deep Dive](https://wikibook.co.kr/mjs/)
- 링크 - [웹 튜토리얼 이웅모](https://poiemaweb.com/)
- 저자 - 이웅모
- 출판사 - 위키북스
