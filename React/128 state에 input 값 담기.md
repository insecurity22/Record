##### state에 input 값 담기

```react
import React, { Component } from 'react';

class EventPractice extends Component {
    
    state = {
        message: ''
    }

	render() {
        return (
        	<div>
            	<h1>Event Practice</h1>
                <input
                    type="text"
                    name="message"
                    placeholder="Please enter anything"
                    value={this.state.message}
                    onChange={
                        (e) => {
                            this.setState({
                                message: e.target.value
                            })
                        }
                    }
                />
                <button onClick={
                        () => {
                            alert(this.state.message);
                            this.setState({
                                message: ''
                            });
                        }
                }>확인</button>
            </div>
        );
    }
}

export default EventPractice;
```

현재 message 값을 alert를 이용하여 화면에 표시