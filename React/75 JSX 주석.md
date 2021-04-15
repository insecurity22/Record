```react
...

function App() {
    const name = 'React';
    return (
    	<>
    		{/* 주석 */}
                <div
                      className="react" // 시작 태그를 여러 줄로 작성하게 된다면 여기에 주석 작성 가능
                >
                      {name}
                </div>
                // 하지만 이런 주석이나
                /* 이런 주석은 페이지에 그대로 나타남 */
    	</>
    );
}

export default App;
```

