```react
import React, { useState } from 'react';

const Say = () => {
    const [ message, setMessage ] = useState('');
    const onClickEnter = () => setMessage('안녕하세요');
    const onClickLeave = () => setMessage('안녕히 가세요');
    
    const [ color, setColor ] = useState('black');
    
    return (
    	<div>
        	<button onClick={onClickEnter}>입장</button>
        	<button onClick={onClickLeave}>퇴장</button>
           
...
```



1. 주의사항

- 이벤트 이름은 카멜 표기법으로 작성
  - onclick(html) -> onClick(react)
  - onkeyup -> onKeyUp
- 이벤트에 실행할 JS 코드를 전달하는 것이 아니라, 함수 형태의 값을 전달

- DOM 요소에만 이벤트 설정 가능

  - 직접 만든 컴포넌트에는 이벤트를 자체적으로 설정할 수 없음

  ```react
  <MyComponent onClick={doSomething} />
  // 그냥 이름이 onClick인 props를 MyComponent에게 전달해줄 뿐
  ```

  

  즉 컴포넌트에 자체적으로 이벤트를 설정해줄 순 없지만,

  전달받은 props를 컴포넌트 내부의 DOM 이벤트로 설정할 수는 있다.

  ```react
  <div onClick={this.props.onClick}>
  	{ /* ... */ }
  </div>
  ```

  

  https://facebook.github.io/react/docs/events.html

  