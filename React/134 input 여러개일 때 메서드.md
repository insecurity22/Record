```react
import React, { Component } from 'react';

class EventPractice extends Component {
    
    state = {
        username: '',
        message: ''
    }

	handleChange = (e) => { 
        this.setState({
            [e.target.name]: e.target.value // <------
        });
    }

	handleClick = () => { 
        alert(this.state.username + ': ' + this.state.message);
        this.setState({
            username: '',
            message: ''
        });
    }

	render() {
        return (
        	<div>
            	<h1>Event Practice</h1>
                <input
                    type="text"
                    name="username" // <----
                    placeholder="User name"
                    value={this.state.username} 
                    onChange={this.handleChange}
                />
                <input
                    type="text"
                    name="message" // <----
                    placeholder="Please enter anything"
                    value={this.state.message} 
                    onChange={this.handleChange}
                />
                <button onClick={this.handleClick}>확인</button>
            </div>
        );
    }
}
```

input이 여러 개일 때는 메서드를 여러개 만들지 말고 event 객체를 활용할 것

e.target.name : 해당 input의 name을 가리킴



```
객체 안에서 key를 []로 감싸면
그 안에 넣은 레퍼런스가 가리키는 실제 값이 key 값으로 사용됨

ex)
	const name = 'variantKey';
	const object = {
		[name]: 'value'
	};
	
=>
	{
		'variantKey': 'value'
	}
```

