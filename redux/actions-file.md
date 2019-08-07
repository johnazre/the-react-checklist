# Creating an actions file

1. Create constants.js file containing the constant variables that will be used for all needed dispatch types.
2. Import constants into your actions.js file.
3. Import axios
4. Declare functions with dispatches corresponding to each action type.
    * First dispatch action: "Pending"
        - Payload is not required
    * Second dispatch action: "Success"
        - Execute API call (will include type and payload)
    * Third dispatch action: "Failed"
        - Catch for unsuccessful API call (error will be payload)


Example: 

```js
import {
  ADD_PENDING,
  ADD_SUCCESS,
  ADD_FAILED,
} from './constants';
import axios from 'axios';

export const add = newThing => {
  return dispatch => {
    dispatch({
      type: ADD_PENDING
    })
    axios
      .post(`http://localhost:8082/api/#`)
      .then(res => {
        dispatch({
          type: ADD_SUCCESS,
          payload: res.data
        })
      })
      .catch(err => {
        dispatch({
          type: ADD_FAILED,
          payload: err
        })
      })
  }
}
```