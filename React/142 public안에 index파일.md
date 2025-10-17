public/index.html
```react
...
  <div id="root"></div>
...
```

src/index.js
```react
...
  ReactDOM.render(<App />, document.getElementById('root'));
```

React 컴포넌트 안에서는 id를 사용하면 안되나요?<br>
사용할 수는 있지만 특수한 경우가 아니면, 권장하지 않습니다.<br>
<br>
예를 들어 같은 컴포넌트를 여러 번 사용한다 가정하면<br>
HTML에서 DOM의 id는 유일해야하는데, 이런 상황에서는 중복 id를 가진 DOM이 여러개 생기니 잘못된 사용입니다.<br>
<br>
--> ref는 전역적으로 작동하지 않고 컴포넌트 냅에서만 작동하기 때문에 이런 문제가 생기지 않습니다.<br>
<br>
<br>
대부분은 id를 사용하지 않고도 원하는 기능을 구현할 수 있지만,<br>
다른 라이브러리나 프레임워크와 함께 id를 사용해야하는 상황이 발생할 수 있습니다.<br>
이런 상황에서는 컴포넌트를 만들 때마다 id 뒷부분에 추가 텍스트를 붙여서 ex) button01, button02, button03 ...<br>
중복 id가 발생하는 것을 방지해야합니다.<br>
