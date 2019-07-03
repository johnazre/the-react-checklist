# General steps on creating a basic stateful functional component

1. On line 1 of the file: `import React, { useState } from 'react'`
1. Create a function named whatever you want the component to be called: `const App = () => {...}`
1. Return some arbitrary JSX, like `<div>Hello</div>` or something that you'll update later
1. Add a const with a destructured array that has a "getter" and "setter" for that piece of data: `const [ todo, setTodo ] = useState([])` (YES, the order of "todos" and "setTodos" matters)
1. To see the todo anywhere in the component, use the `todo` variable
1. To update todo anywhere in the component, use the `setTodo` method

## Final Result

Should look something like this:

```js
import React, { useState } from 'react'

const App = () => {
  const [ todo, setTodo ] = useState('')
  return (
    <div className="App">
      <p>{todo}</p>
    </div>
  )
}

export default App
```
