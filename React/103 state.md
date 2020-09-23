##### state

- 내부에서 바뀔 수 있는 값



1. 클래스형 컴포넌트

```react
import React, { Component } from 'react';

class Counter extends Component {
	constructor(props) {
		super(props);
		// state의 초깃값 설정
		this.state = {
			number: 0
		};
	}
    // 반드시 constructor를 작성할 때는 super(props)를 호출해 주어야 한다.
    // => 그래야 현재 클래스형 컴포넌트가 상속 받고 있는 
    // 리액트의 Component 클래스가 지닌 "생성자 함수"를 호출해줌
    
	render() {
		const { number } = this.state;
		return (
			<div>
				<h1>{number}</h1>
                <button
                    onClick={() => { // 버튼 클릭 시 호출할 함
                        this.setState({ number: number + 1});
                        // this.setState를 사용하여 state에 새로운 값 넣기
                    }}
                >
                 +1
                </button>
            </div>
		);
	}
}

export default Counter;
```

```react
import React from 'react';
import Counter from './Counter';

const App = () => {
    return <Counter />;
};

export default App;
```



​	1) state가 여러 값일 때

```react
this.state = {
    number: 0,
    fixedNumber: 0
};

...


render() {
    const { number, fixedNumber } = this.state;
    
    ...
}
```



​	2) 초깃값 설정하는 constructor 메서드 선언하지 않았을 때

```react
...

class Counter extends Component {
    state = {
        number: 0,
        fixedNumber: 0
    };

	...
```



​	3) 주의사항

```react
X

// 클래스형 컴포넌트
this.state.number = this.state.number + 1;
this.state.array = this.array.push(2);
this.state.object.value = 5

// 함수형 컴포넌트
const [object, setObject] = useState({ a: 1, b: 1 });
object.b = 2;
```

```react
O

// 객체 다루기
const object = { a: 1, b: 2, c: 3 };
const nextObject = { ...object, b: 2 }; // 사본을 만들어서 b 값만 덮어쓰기

// 배열 다루기
const array = [
    { id: 1, value: true },
    { id: 2, value: true },
    { id: 3, value: false }
];
let nextArray = array.concat({ id: 4 }); // 새 항목 추가
nextArray.filter(item => item.id !== 2); // id가 2인 항목 제거
nextArray.map(item => item.id === 1 ? { ...item, value: false } : item)); // id가 1인 항목의 value를 false로 설정
```


