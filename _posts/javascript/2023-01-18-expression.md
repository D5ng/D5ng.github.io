---
title: 5장. 표현식
author: D5ng
date: 2023-01-18 00:00 +09:00
layout: post
category: JavaScript
---

### 값이란 ?

값은 표현식이 평가되어 생성된 결과를 말한다.

```javascript
// 변수에 할당되는것아 값이다.
var addNumber; // 10 + 20 = 표현식이다.
```

### 리터럴이란 ?

**사람이 이해할 수 있는 문자 또는 약속된 기호**를 사용해 값을 생성하는 표기법이다.

```javascript
var arr = []; // 배열 리터럴
var obj = {}; // 객체 리터럴
var fn = function (ratio) {
	return ratio;
};
```

### 표현식이란 ?

표현식은 값으로 평가될 수 있는 문이다.  
리터럴은 값으로 평가되기에 리터럴도 표현식이다.

표현식인 문과, 표현식이 아닌 문을 구별하는 가장 쉬운방법은 변수에 할당하는 방법이다.
