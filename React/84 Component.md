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



2-1) 함수형 컴포넌트의 장단점

- 함수형 컴포넌트는 클래스형 컴포넌트보다 선언하기가 훨씬 편하고
- 메모리 자원도 클래스형 컴포넌트보다 덜 사용하며
- 프로젝트를 완성하여 빌드한 후 배포할 때에도 함수형 컴포넌트를 사용하는 것이 결과물의 파일 크기가 더 작지만, 성능과 파일 크기 면에서 사실상 별 차이가 없으므로 너무 중요하게 여기지 않아도 된다.
- 함수형 컴포넌트의 단점은 state와 라이프사이클 API 사용이 불가능하다는 점
- 하지만 React v16.8 업데이트 이후 Hooks이라는 기능이 도입되면서 해결되었다. (완전히 클래스형 컴포넌트와 똑같이 사용할 수 있는 것은 아니지만 조금 다른 방식으로 비슷한 작업을 할 수 있게 됨)

- React 공식 메뉴얼에서는 Component를 새로 작성할 때, 함수형 컴포넌트와 Hooks(state, 라이프사이클 API 사용가능)를 사용하도록 권장하고 있음