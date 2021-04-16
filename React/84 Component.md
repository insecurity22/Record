##### Component 기능

- 데이터가 주어졌을 때, 이에 맞추어 UI를 만들어줌

- 라이프사이클 API를 이용하여 컴포넌트가 화면에서 나타날 때, 사라질 때, 변화가 일어날 때 주어진 작업들을 처리할 수 있음
- 임의 메서드를 만들어 특별한 기능을 붙여줄 수 있음



##### Component 속성 값

- props



##### Component 상태 값

- state



##### Componet 선언 방식

1) 클래스형 컴포넌트

```react
import React, { Component } from 'react';

class App extends Component {
    render() {
        const name = 'react';
        return <div className="react">{name}</div>;
    }
}

export default App;
```

- state 기능 및 라이프사이클 기능 사용 가능
- 임의 메서드 정의 가능



​	1-1) 조건

- render 함수가 꼭 있어야함
- 그 안에서 보여주어야 할 JSX를 반환해야함



2) 함수형 컴포넌트

```react
...

function App() {
    const name = 'React';
    return <div className="react">{name}</div>;
}

export default App;
```

- React 공식 메뉴얼에서는 Component를 새로 작성할 때, 함수형 컴포넌트와 Hooks(state, 라이프사이클 API 사용가능)를 사용하도록 권장하고 있음
