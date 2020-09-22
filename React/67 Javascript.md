##### Javascript 변수, 문법

```react
import React from 'react';

function App() {
    const name = 'React'; // 변수
    return (
    	<div>
    		{name === 'React' ? (  {/* Javascript 문법 */}
             	<h1>React.</h1>
             ) : (
    			<h2>Not React.</h2>
    		 )};
    	</div>
	);
}

export default App;
```



JS에서는 문자열을 표현할 때 작은 따옴표를 써도 되고, 큰 따옴표를 써도 된다.
