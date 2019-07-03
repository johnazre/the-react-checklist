# Creating a basic stateful class component with a form

1. On line 1 of the file: `import React from 'react'`
1. Create a class that inherits the React.Component class: `class Whatever extends React.Component {...}`
1. Add `render(){...}` method to the class that returns some arbitrary JSX, like `<div>Hello</div>` or something
1. Add the state property to the class: `state = {...}`
1. Create a form in the JSX and add necessary input fields
1. In each input element, add an `onChange` event listener that will run the `this.handleChange` event handler that we will create in the next step
1. Add a `handleChange = () => {...}` property to the class that will update the piece of state tied to each input form. Deconstructing the `event.target` object is optional, but is easier to read, in my opinion.
1. Update the state in `handleChange` using `this.setState({...})`
1. In the opening tag of the `form` element, add an `onSubmit` attribute with a value of `this.handleSubmit`: `<form onSubmit={this.handleSubmit}>...</form>`
1. Create a class property called `handleSubmit` that contains an arrow function. In that arrow function, make any POST request (or any other method) you need to make, if needed, then update the state to reflect the changes in the `.then` method after the promise is resolved.

## Final Result

Should look something like this:

```js
import React from 'react'
import axios from 'axios'

class App extends React.Component {
  state = {
    newTodo: '',
    todos: []
  }
  handleSubmit = event => {
    axios.post('https://jsonplaceholder.typicode.com/todos', { title: this.state.newTodo })
      .then(response =>
        this.setState({ todos: [...this.state.todos, response.data]})
      )
  }
  handleChange = event => {
    let { name, value } = event.target
    this.setState({
      [name]: value
    })
  }
  render() {
    return (
      <div className="App">
        <form onSubmit={this.handleSubmit}>
          <p>
            New todo:
            <input
              type="text"
              name="someString"
              onChange={this.handleChange}
            />
          </p>
        </form>
        <button type="submit">Submit</button>
      </div>
    )
  }
}

export default App
```
