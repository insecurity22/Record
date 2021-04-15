##### Javascript ||

```react
import React from 'react';

function() {
    const name = undefined;
    return name || "값이 undefined입니다.";
}

export default App;
```

리액트 컴포넌트에서는 함수에서 undefined만 반환하여 렌더링하는 상황을 만들면 안되므로

OR 연산자를 사용해 해당 값이 undefined일 때 사용할 값 지정 가능.


```react
const name = undefined;
return <div>{name || 'React'}</div>;
```

JSX 내부에서 렌더링하는 건 가능
