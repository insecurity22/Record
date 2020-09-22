##### JSX : class -> className



```css
.react {
    background: aqua;
    color: black;
    font-size: 48px;
    font-weight: bold;
    padding: 16px;
}
```



```react
import React from 'react';
import './App.css';

function App() {
    const name = 'React';
    return <div className="react">{name}</div>;
}

export default App;
```

