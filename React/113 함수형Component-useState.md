##### useState

React 16.8 이전 버전에서는 함수형 컴포넌트에서 state 사용할 수 없었지만

16.8 이후부터는 useState 함수를 사용하여 state를 사용할 수 있게 되었다.



```react
import React, { useState } from 'react';

const Say = () => {
    const [ message, setMessage] = useState('');
    // useState 함수의 인자에는 상태의 초깃값을 넣어줌
    // 값의 형태는 자유, 숫자, 문자열, 객체, 배열 등
    // message, 현재 상태
    // setMessage, 상태를 바꿔주는 함수, Setter 함수
    const onClickEnter = () => setMessage('안녕하세요');
    const onClickLeave = () => setMessage('안녕히 가세요');
    
    return (
    	<div>
        	<button onClick={onClickEnter}>입장</button>
            <button onClick={onClickLeave}>퇴장</button>
        </div>
    );
};

export default Say;
```

```react
import React from 'react';
import Say from './Say';

const App = () => {
    return <Say />;
};
```



1) useState 여러번 사용 가능

```react
...

    const onClickEnter = () => setMessage('안녕하세요');
    const onClickLeave = () => setMessage('안녕히가세요');

    const [ color, setColor ] = useState('black');

    return (
        <div>
            <button onClick={onClickEnter}>입장</button>
            <button onClick={onClickLeave}>퇴장</button>

            <h1 style={{ color }}>{message}</h1> {/* 색 변경 */}
            <button style={{ color: 'red' }} onClick={() => setColor('red')}>빨간색</button>
            <button style={{ color: 'green' }} onClick={() => setColor('green')}>초록색</button>
            <button style={{ color: 'blue' }} onClick={() => setColor('blue')}>파란색</button>
        </div>
    );
};

export default Say;
```

