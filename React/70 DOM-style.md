##### DOM 요소에 스타일을 적용 할 때

객체 형태로 넣어주어야 한다.

또한 스타일 이름 중 background-color처럼 - 문자가 포함되는 이름이 있을 경우,

- 문자를 없애고 카멜 표기법으로 작성해야한다.

```react
import React from 'react';

function App() {
    const name = 'React';
    const style = { // 객체 선언
        // background-color -> backgroundColor 카멜 표기법으로 작성
        backgroundColor: 'black',
        color: 'aqua',
        fontSize: '48px',
        fontWeight: 'bold',
        padding: 16 // 생략 시, px로 지정
    };
    return <div style={style}>{name}</div>;
}

export default App;
```



미리 선언하지 않고 바로 style 값을 지정해주고 싶다면

```react
function App() {
    const name = 'React';
    return (
    	<div
            style={{
                backgroundColor: 'black',
                color: 'aqua',
                fontSize: '48px',
                fontWeight: 'bold',
                padding: 16
            }}
        ></div>
    );
}
```

