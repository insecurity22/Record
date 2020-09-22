##### props

- 컴포넌트가 사용되는 과정에서 부모 컴포넌트가 설정하는 값
- 컴포넌트 자신은 해당 props를 읽기 전용으로만 사용 가능
- 즉 props를 바꾸려면 부모 컴포넌트에서 바꿔주어야함

```react
import React from 'react';

const MyComponent = props => {
    return <div>Hi, my name is {props.name}.</div>;
};

export default MyComponent;
```

```react
import React from 'react';
import MyComponent from './MyComponent';

const App = () => {
    return <MyComponent name="React" />
};

export default App;
```

컴포넌트 함수의 파라미터로 받아와 사용 가능하다



1. 기본값 설정

   ```react
   import React from 'react';
   ```

const MyComponent = props => {
    return <div>Hi, my name is {props.name}.</div>;
};

MyComponent.defaultProps = {
    name: 'defaultname'
};

export default MyComponent;
   ```



2. 코드 줄이기

​```react
import React from 'react';

const MyComponent = props => {
    const { name, children } = props; // <--------
    return (
    	<div>
        	Hi, my name is {name}.<br />
        	The children value is {children}.
        </div>
    );
};

...
   ```

OR

```react
import React from 'react';

const MyComponent = ({ name, children }) => { // <------
    return (
    	<div>
        	Hi, my name is {name}.<br />
        	The children value is {children}.
        </div>
    );
};

...
```

props.name -> name



3) props의 타입 지정

```react
import React from 'react';
import PropTypes from 'prop-types';

const MyComponent = ({ name, children }) => {
    return (...);
};

MyComponent.propTypes = { // <---
    name: propTypes.string
};

export default MyComponent;
```

```react
import React from 'React';
import MyComponent from './MyComponent';

const App = () => {
    return <MyComponent name={3}>React</MyComponent>;
};

export default App;
```

Warning: Failed prop type: Invalid prop ...



4) 필수 propTypes 설정

```react
import React from 'react';
import PropTypes from 'prop-types';

const MyComponent = ({ name, favorateNumber, children }) => {
    return (
    	<div>
        	Hi, my name is {name}.<br />
            The children value is {children}.<br />
            My favorite number is {favoriteNumber}.
        </div>
    );
};

MyComponent.propTypes = {
    name: PropTypes.string,
    favoriteNumber: PropTypes.number.isRequired // <----
};

export default MyComponent;
```

```react
import React from 'react';
import MyComponent from './MyComponent';

const App = () => {
    return (
    	<MyComponent name="React" favoriteNumber={1}>
        	React
        </MyComponent>
    );
};
    
export efault App;
```

.isRequired