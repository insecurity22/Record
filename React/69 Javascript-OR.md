##### Javascript ||

```react
import React from 'react';

function() {
    const name = undefined;
    return name || "값이 undefined입니다.";
}

export default App;
```



```react
const name = undefined;
return <div>{name || 'React'}</div>;
```

JSX 내부에서 렌더링하는 건 가능
