##### DOM 요소에 스타일을 적용 할 때

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

