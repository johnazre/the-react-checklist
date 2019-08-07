# Creating a reducer file

* The reducer is a function that takes 2 parameters: state and action (order matters).
* The reducer contains a switch statement that takes the action.type and runs the code for the corresponding case scenario.

1. Create constants.js file containing the constant variables that will be used for all needed dispatch types.
2. Import constants into your reducer.js file.
3. Declare variable "initialState" and assign it to a default value.
4. Export a default function that has 2 parameters -> state and action.
    * Use a default param that sets state equal to initialState.
5. Write a conditional using a switch statement that will take action.type
6. Write a case for each action type using the constant variables imported from constants.js.
    * Each case will return some form of state, provided that the API call is successful.
    * If API call fails, should return action.payload (which contains the error).
7. Write a default case, which will return state.

```js
import {
  ADD_SUCCESS,
  ADD_PENDING,
  ADD_FAILED
} from './constants'

let initialState = []

export default (state = initialState, action) => {
  switch (action.type) {
    case ADD_PENDING:
      return state
    case ADD_SUCCESS:
      let theNewThing = action.payload
      return [...state, theNewThing]

    case ADD_FAILED:
      return action.payload

    case 'REMOVE_':
      return state.filter(thing => thing !== action.payload)
    default:
      return state
  }
}
```