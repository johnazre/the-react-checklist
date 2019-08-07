* The store is created by the index.js file in the store folder/directory
* The store combines all reducers and adds middleware

1. Import createStore, combineReducers, and applyMiddleawre from 'redux'.
2. Import all reducers from each entity in the app (e.g. "todos", "users", etc.).
3. Import middleware that you will be using in your application (e.g. redux-logger, redux-thunk).
4. Declare constant variable called "rootReducer" that will combine the result of combineReducer function.
5. Export default createStore
    * The first parameter will take the rootReducer (which are the combined reducers)
    * The second parameter will take applyMiddleware function (which takes each middleware you are using as arguments)

```js
import { createStore, combineReducers, applyMiddleware } from 'redux';
import todosReducer from './todos/reducer';
import logger from 'redux-logger';
import thunk from 'redux-thunk';

const rootReducer = combineReducers({
    todos: todosReducer
})

export default createStore(rootReducer, applyMiddleware(thunk, logger));
```