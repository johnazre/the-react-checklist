1. Import constants from constants.js.

   import {
   ADD_TODO_PENDING,
   ADD_TODO_SUCCESS,
   ADD_TODO_FAILED,
   REMOVE_TODO_PENDING,
   REMOVE_TODO_FAILED,
   REMOVE_TODO_SUCCESS
   } from './constants'

2. Next declare the inital state which is almost always a []
   let initialState = [];

3. Declare a function called reducer or export default (no name necessary and you do not need to export at the bottom of the page)


    a) The function will take two parameters (state and action), and you will assign state to the initial state that you declared in step 2
     export default (state = initialState, action) {

4. Next your switch conditional with the peramiter action.type

5. First case is PENDING that returns state
   switch (action.type) {
   //if the action is 'ADD_TODO'
   case ADD_TODO_PENDING:
   return state
6. Second case is the SUCCESS retun state using the spread operator to return everything we have in state and what ever you are adding to state
   case ADD_TODO_SUCCESS:
   action.payload
   let theNewTodo = action.payload;
   return [...state, theNewTodo]

7. Third is FAILED returns action.payload which is the err from the action
8. Must put default at end of the switch to default to the initialState if none of the cases are true
