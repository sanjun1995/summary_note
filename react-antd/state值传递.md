## state用法
```
import React, { Component } from 'react'

class StateTest extends Component {
    state = {
        name: "test"
    }
    render() {
        const { name } = this.state
        return (
            <div>{name}</div>
        )
    }
}

export default StateTest;
```

