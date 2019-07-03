# General steps on creating a basic stateful functional component

1. On line 1 of the file: `import React, { useState } from 'react'`
1. Create a function named whatever you want the component to be called: `const App = () => {...}`
1. Return some arbitrary JSX, like `<div>Hello</div>` or something that you'll update later
1. Add as many const variables as need with a destructured array that has a "getter" and "setter" for each piece of data: `const [ todo, setTodo ] = useState([])` (YES, the order of "todos" and "setTodos" matters). To see the todo anywhere in the component, use the `todo` variable and to update the todo anywhere in the component, use the `setTodo` method
1. Add a form to the JSX and add any necessary inputs (in this case, we have just one for the "todo")
1. In each input element, add an `onChange` attribute that contains an arrow function within curly brackets. In that arrow function, call the "setter" method of the piece of state you wish to target with that input and pass in the current value of the input, which is `event.target.value`
1. In the opening tag of the `form` element, add an `onSubmit` attribute with a value of `handleSubmit`: `<form onSubmit={handleSubmit}>...</form>`
1. Create a function in the component called `handleSubmit`. Make any POST request (or any other method) you need to make, if needed, then update the state to reflect the changes in the `.then` method after the promise is resolved.

## Final Result

Should look something like this:

```js
import React, { useState } from 'react'

const App = () => {
  const [ todos, setTodos ] = useState([])
  const [ newTodo, setNewTodo ] = useState('')
  function handleSubmit(event) {
    event.preventDefault()
    setTodos([...todos, newTodo])
  }
  return (
    <div className="App">
      <form onSubmit={handleSubmit}>
        <p>Update todo:
          <input
            type="text"
            onChange={event => setNewTodo(event.target.value)}
          />
        </p>
        <button type="submit">Submit</button>
      </form>
    </div>
  )
}

export default App
```
