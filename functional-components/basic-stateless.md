# General steps on creating a basic stateless functional component

1. On line 1 of the file: `import React from 'react'`
1. Create a function named whatever you want the component to be called: `const App = () => {...}`
1. Return some arbitrary JSX, like `<div>Hello</div>` or something that you'll update later

## Final Result

Should look something like this:

```js
import React from 'react'

const App = () => {
  return (
    <div className="App">
      <p>{todo}</p>
    </div>
  )
}

export default App
```
