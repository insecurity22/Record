```react
import React, { Component } from 'react';

const EventPractice = () => {
    const [username, setUsername] = useState('');
    const [message, setMessage] = useState('');
    const onChangeUsername = e => setUsername(e.target.value);
    const onChangeMessage = e => setMessage(e.target.value);
    const onClick = () => {
        alert(username + ': ' + message);
        setUsername('');
        setMessage('');
    };
    const onKeyPress = e => {
        if(e.key === 'Enter') {
            onClick();
        }
    };
    
    return (
        <div>
            <h1>Event Practice</h1>
            <input
                type="text"
                name="username"
                placeholder="User name"
                value={username} 
                onChange={onChangeUsername}
            />
            <input
                type="text"
                name="message"
                placeholder="Please enter anything"
                value={message} 
                onChange={onChangeMessage}
                onKeyPress={onKeyPress}
                />
            <button onClick={onClick}>확인</button>
        </div>
    );
};

export default EventPractice;
```



useState에 객체를 넣었을 때

```react
    const [form, setForm] = useState({
        username: '',
        message: ''
    });
    const { username, message } = form;

    const onChange = e => {
        const nextForm = {
            ...form,
            [e.target.name]: e.target.value // 덮어씌우기
        };
        setForm(nextForm);
    };
    const onClick = () => {
        alert(username + ': ' + message);
        setForm({
            username: '',
            message: ''
        });
    };
    const onKeyPress = e => {
        if(e.key === 'Enter') {
            onClick();
        }
    };

...

                value={username} 
                onChange={onChange}
            />
            <input
                type="text"
                name="message"
                placeholder="Please enter anything"
                value={message} 
                onChange={onChange} // <---
                onKeyPress={onKeyPress}
                />
                    
...
```

여러 개의 input 상태를 관리하기 위해 useState에서 form 객체 사용하는 방법