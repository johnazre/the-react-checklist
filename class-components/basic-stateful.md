# Creating a basic stateful class component

1. On line 1 of the file: `import React from 'react'`
1. Create class that inherits the React.Component class: `class Whatever extends React.Component {...}`
1. Add `render(){...}` method to the class that returns some arbitrary JSX, like `<div>Hello</div>` or something that you'll update later
1. Add the state property to the class: `state = {...}`

## Final Result

Should look something like this:

```js
import React from 'react'

class App extends React.Component {
  state = {
    someString: '',
    someArray: []
  }
  render() {
    return (
      <div className="App">
        <p>Blah</p>
      </div>
    )
  }
}

export default App
```
