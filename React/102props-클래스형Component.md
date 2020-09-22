```react
import React, { Component } from 'react';
import PropTypes from 'prop-types';

class MyComponent extends Component {
    render() {
        const { name, favoriteNumber, children } = this.props; // 비구조화 할당
        return (
        	<div>
            	Hi, my name is {name}.<br />
            	The children value is {children}.<br />
            	My favorite number is {favoriteNumber}.
            </div>
        );
    }
}

MyComponent.defaultProps = {
    name: 'defaultname'
};

MyComponent.propTypes = {
    name: PropTypes.string,
    favoriteNumber: PropTypes.number.isRequired
};

export default MyComponent;
```



OR 내부에서 지정

```react
import React, { Component } from 'react';
import PropTypes from 'prop-types';

class MyComponent extends Component {
    static defaultProps = { // <------
        name: 'defaultname'
    };
	static propTypes = { // <------
        name: PropTypes.string,
        favoriteNumber: PropTypes.number.isRequired
    };
	render() {
        const { name, favoriteNumber, children } = this.props; // 비구조화 할당
        return (...);
    }
}

export default MyComponent;
```

