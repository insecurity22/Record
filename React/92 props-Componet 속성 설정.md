##### props

- 컴포넌트 속성을 설정할 때 사용하는 요소

- 해당 컴포넌트를 불러와 사용하는 부모 컴포넌트에서 설정할 수 있다.

```react
// MyComponent.js
import React from 'react';

const MyComponent = props => {
    return <div>Hi, my name is {props.name}.</div>;
};

export default MyComponent;
```

```react
// App.js
import React from 'react';
import MyComponent from './MyComponent';

const App = () => {
    return <MyComponent name="React" />
};

export default App;
```

컴포넌트 함수의 파라미터로 받아와 사용 가능하다



1. props 기본값 설정

   - props 값을 따로 지정하지 않았을 때 보여줄 기본값 설정

   ```react
   import React from 'react';
   
   const MyComponent = props => {
       return <div>Hi, my name is {props.name}.</div>;
   };
   
   MyComponent.defaultProps = {
       name: 'default name'
   };
   
   export default MyComponent;
   ```

   - 그럼 결과가 Hi, my name is default name. 이렇게 나오겠쥬



2. 태그 사이의 내용을 보여주는 children

   - MyComponent 태그 사이에 작성한 React 문자열을 MyComponent 내부에서 보여주려면 props.children 값을 보여주어야합니다.

   ```react
   import React from 'react';
   import MyComponent from './MyComponent';
   
   const App = () => {
       return <MyComponent>React</MyComponent>;
   };
   
   export default App;
   ```

   ```react
   import React from 'react';
   
   const MyComponent = props => {
       return (
       	<div>
           	Hi, my name is {props.name}.<br />
           	The children value is {props.children}.
           </div>
       );
   };
   
   Mycomponent.defaultProps = {
       name: 'default name'
   }
   
   export default MyComponent;
   // Result : Hi, my name is default name.<br />
   //        	The children value is React.
   ```



3. 비구조화 할당 문법을 통해 props 내부 값 추출
   - props 값을 조회할 때마다 props.name, props.children과 같이 props. 이라는 키워드를 앞에 붙여주고 있는데 이러한 작업을 더 편하게 하기 위해 ES6의 비구조화 할당 문법을 사용하여 내부 값을 바로 추출 가능

   ```react
import React from 'react';
   
   const MyComponent = props => {
       const { name, children } = props; 
       return (
       	<div>
           	Hi, my name is {name}.<br />
           	The children value is {children}.
           </div>
       );
   };
   
   ...
   ```
   
   ```react
   import React from 'react';
   
   const MyComponent = ({ name, children )} => {
       return (
       	<div>
           	Hi, my name is {name}.<br />
           	The children value is {children}.
           </div>
       );
   };
   
   ...
   ```
   
   

4. props의 타입 지정

   ```react
   import React from 'react';
   import PropTypes from 'prop-types';
   
   const MyComponent = ({ name, children }) => {
       return (...);
   };
   
   MyComponent.defaultProps = {
       name: 'default name'
   }
   
   MyComponent.propTypes = { // <---- ★
       name: PropTypes.string
   };
   
   export default MyComponent;
   ```

   - 이렇게 설정해주면 name 값은 무조건 string 형태로 전달해야 된다는 것을 의미합니다.



5. isRequired를 사용하여 필수 propTypes 설정

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

MyComponent.defaultProps = {
    name: 'default name'
}

MyComponent.propTypes = {
    name: PropTypes.string,
    favoriteNumber: PropTypes.number.isRequired // <---- ★
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
    
export default App;
```

- propTypes을 지정할 때 뒤에 isRequired를 붙여주면 된다.

- prop가 제공되지 않았을 때 경고가 보이도록 할 수 있다.