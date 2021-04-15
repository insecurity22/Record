##### Hooks



1. usestate

```react
import React, { useState } from 'react';

const Counter = () => {
    const [value, setValue] = useState(0); // 상태의 기본값, 기본값을 0으로 설정하겠다는 의미
    // 1, 상태 값
    // 2, 상태를 설정하는 함수
    // - 이 함수에 파라미터를 넣어 호출하면 전달받은 파라미터로 값이 바뀜
    
    return(
    	<div>
        	<p>
            	현재 카운터 값은 <b>{value}</b>입니다.
            </p>
            <button onClick={() => setValue(value + 1)}>+1</button>
            <button onClick={() => setValue(value - 1)}>-1</button>
        </div>
    );
};

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



1. 여러번 사용 시

```react
import React, { useState } from 'react';

const Info = () => {
    const [name, setName] = useState('');
    const [nickname, setNickname] = useState('');
    
    const onChangeName = e => {
        setName(e.target.value);
    };
    
    const onChangeNickname = e => {
        setNickname(e.target.value);
    };
    
    return (
    	<div>
        	<div>
            	<input value={name} onChange={onChangeName} />
                <input value={nickname} onChange={onChangeNickname} />
            </div>
            <div>
            	<div>
                	<b>이름:</b> {name}
                </div>
                <div>
                	<b>닉네임:</b> {nickname}
                </div>
            </div>
        </div>
    );
};

export default Info;
```



2. useReducer

- 현재 상태, 업데이트를 위해 필요한 정보를 담은 action 값을 전달받아 새로운 상태를 반환하는 함수