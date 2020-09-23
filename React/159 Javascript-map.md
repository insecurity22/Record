##### map

- map 함수를 사용하여 반복되는 컴포넌트 렌더링 할 수 있음

```react
var numbers = [1, 2, 3, 4, 5];

var processed = numbers.map(function(num){
    return num * num;
});

console.log(processed);
// ---> [1, 4, 9, 16, 25]
```



ES6

```react
const numbers = [1, 2, 3, 4, 5];
const result = numbers.map(num => num * num);
console.log(result);
```



1. map 사용

```react
const articleList = articles.map(article => (
	<Article
        title={article.title}
        writer={article.writer}
        key={article.id}
   />
);
```

게시판의 게시물을 렌더링한다면 게시물 번호를 key 값으로 설정



2. map 사용

```react
import React from 'react';

const IterationSample = () => {
    return (
    	<ul>
        	<li>눈사람</li>
        	<li>얼음</li>
        	<li>눈</li>
        	<li>바람</li>
        </ul>
    );
};

export default IterationSample;
```

```react
import React from 'react';

const IterationSample = () => {
    const names = ['눈사람', '얼음', '눈', '바람'];
    const nameList = names.map((name, index) => <li key={index}>{name}</li>);
    return <ul>{nameList}</ul>;
};

export default IterationSample;
```

이 때 Key 값을 가지고 있어야하고, Key 값은 유일해야한다.



