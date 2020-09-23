##### setState

- state 값 업데이트

```react
this.setState((prevState, props) => { 
    // prevState, 기존 상태
    // props, 현재 지니고 있는 props, 생략 가능
    return {
        // 업데이트 내용
    }
})
```



1) 예제

```react
<button onClick{() => {
            this.setState(prevState => { // <---- 똑같음
                return {
                    number: prevState.number + 1
                };
            });

            this.setState(prevState => ({ // <---- 똑같음
                number: prevState.number + 1
            }));
       	}}
    >
    +1
</button>
```

const sum = (a, b) => a + b

- 값을 바로 반환



2) this.setState 끝난 후, 특정 작업 실행

```react
...

this.setState({
    number: number+1
}, () => {
    console.log(this.state);
});

...
```

