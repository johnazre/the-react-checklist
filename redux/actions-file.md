# Creating an actions file

1. Create constants.js file

2. Import constants.
3. Import axios or whichever library you are using to get your api calls.

import {
ADD_TODO_PENDING,
ADD_TODO_SUCCESS,
ADD_TODO_FAILED,
REMOVE_TODO_PENDING,
REMOVE_TODO_FAILED,
REMOVE_TODO_SUCCESS
} from './constants'
import axios from 'axios'

4. First export and declare the function variable and create a function that will return another function that inculdes 3 dispatches (see example).

   export const addTodos = () => {
   return dispatch => {}
   }

   a) The pending dispatch is first, which will return an action that only has a type of pending.

   export const addTodo = newTodo => {
   return dispatch => {
   dispatch({
   type: ADD_TODO_PENDING
   })

   b) The success dispatch includes the API call. There will be a .then in the Success dispatch, which returns the payload of res.data.

   axios
   .post('http://localhost:8082/api/todos')
   .then(res => {
   dispatch({
   type: ADD_TODO_SUCCESS,
   payload: res.data  
    })
   })

   c) Next will come the failure dispatch which has a .catch that will return a payload of err.

   .catch(err => {
   dispatch({
   type: ADD_TODO_FAILED,
   payload: err
   })
