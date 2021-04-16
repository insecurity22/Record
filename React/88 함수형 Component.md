##### function 키워드 대신 () => {}를 사용하여 함수 만들기

```react
import React from 'react';

const MyComponent = () => {
    return <div>함수형 컴포넌트</div>;
};

export default MyComponent;
```

위 화살표 함수는 ES6 문법에서 함수를 표현하는 새로운 방식이다.<br>



1. 예제(위 아래 같음)

```
setTimeout(function() {
	console.log('hello world');
}, 1000);

setTimeout(() => {
	console.log('hello world');
}, 1000)
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
