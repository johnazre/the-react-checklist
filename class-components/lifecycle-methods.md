# Using lifecycle methods in a class component

## componentDidMount

1. Import React
2. Create class component with desired name
3. Create a render method in the class that returns some arbitrary JSX (or your JSX of choice)
4. Create the state property and add whichever key/value pairs you would like as the default values
5. Create a method above the render method called `componentDidMount`
6. Inside the `componentDidMount` method, make an API call to whichever server/API you need to in order to get the data for your application.
7. After the API call resolves, use the callback function inside the `.then()` method to add the necessary data to the application state.

```
import React, { Component } from 'react'
class SomeComponent extends Component {
  state = {
    someData: ["some value"]
  }

  componentDidMount() {
    fetch(`http://localhost:8082/api/whatever`)
      .then(res => res.json())
      .then(data => this.setState({ someData: data }))
  }

  render() {
    return (
      <div></div>
    )
  }
}
export default SomeComponent
```
