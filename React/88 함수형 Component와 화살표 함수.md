##### function 키워드 대신 () => {}를 사용하여 함수 만들기

```react
import React from 'react';

const MyComponent = () => {
    return <div>함수형 컴포넌트</div>;
};

export default MyComponent;
```

- 위 화살표 함수는 ES6 문법에서 함수를 표현하는 새로운 방식이다.



1. 예제(위 아래 같음)

```
setTimeout(function() {
	console.log('hello world');
}, 1000);

setTimeout(() => {
	console.log('hello world');
}, 1000)
```

```
function twice(value) {
	return value * 2;
}

const triple = (value) => value * 3;
// 따로 { }를 열어주지 않으면 연산한 값을 그대로 반환한다는 의미
```





2. 예제(가리키고 있는 this 값이 다름)

```
function BlackDog() {
	this.name = '흰둥이';
	return {
		name: '검둥이',
		bark: function() {
			console.log(this.name + ': 멍멍!');
		}
	}
}

const blackDog = new BlackDog();
blackDog.bark(); // 검둥이: 멍멍!

// ---------------------------------------------

function WhiteDog() {
	this.name = '흰둥이';
	return {
		name: '검둥이',
		bark: () => {
			console.log(this.name + ': 멍멍!');
		}
	}
}

const whiteDog = new WhiteDog();
whiteDog.back(); // 흰둥이: 멍멍!
```
- 일반 함수는 자신이 종속된 객체를 this로 가리키며, 화살표 함수는 자신이 종속된 인스턴스를 가리킵니다.



3. 끝으로

- 함수형 컴포넌트를 선언할 때 function 키워드를 사용하는 것과 화살표 함수 문법을 사용하는 것에는 큰 차이가 없다. 
- 화살표 함수를 사용하는 것이 좀 더 간결함. 어떤 방식을 선택할지는 단지 각자의 취향에 달려 있다.
