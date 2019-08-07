# Connecting a component to the store

1. In order to connect a comnponent to the Redux store, you would use the `Connect()` function.
1. In order to use connect, you need to `import { connect }` from `'react-redux'`
1. You then add `props` as an argument to you App Function so we can have access to it (functional component)
1. You then want to create the `mapStateToProps` function which will allow you to customize what part of state you want from the store. It is getting the application state from the store state, mapping the piece you asked for as props for this component.
1. Use the connect() function to connect to the store via the `mapStateToProps` function, and then use the result of that to re-render App. `export default connect(mapStateToProps)(App)`

## Final Result

```js
import React from "react";
import { connect } from "react-redux";

function App(props) {
  function handleClick(e) {
    props.dispatch(addTodo(""));
  }

  return {};
}

function mapStateToProps(state) {
  return {
    todos: state.todos
  };
}
export default connect(mapStateToProps)(App);
```
