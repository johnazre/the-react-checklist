# Creating an index.js file for React/Redux

1. On line 1 of the file: `import { createStore, combineReducers, applyMiddleware } from 'redux'`
1. On line 2 of the file: `import "Your Reducer/Reducers"` from the reducer file location
1. on line 3 of the file: `import thunk` from 'redux-thunk'
1. Below your imports you will then create your `rootReducer` Your root-reducer uses `combineReducers` which takes a combination of all the reducers passed into it and combines it into one reducer.
1. After your `rootReducer` is created, you will then need to `Export default` and export the results of `createStore` which takes a `reducer` as an arguemnent with the optional arguement of `applyMiddleware`.

## Final Result

Should look something like this:

```js
import { createStore, combineReducers, applyMiddleware } from "redux";
import todosReducer from "./todos/reducer";
import thunk from "redux-thunk";

const rootReducer = combineReducers({
  todos: todosReducer
});

export default createStore(rootReducer, applyMiddleware(thunk));
```
