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

