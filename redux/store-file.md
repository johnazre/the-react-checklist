1. Store lives in the index.js file of the store folder.
2. Import the reducer function from reducer.js, import createStore, combineReducers, and applyMiddleware from redux, and whatever middleware you are using.
3. Declare your reducer which will call combineReducers and take an argument of an object that contains your reducer function.
4. Export the call of createStore, which will take your reducer, and the call of applyMiddleware as arguments.
   a) applyMiddleware will take any middleware you imported at the beginning as arguments such as thunk or logger.

import { createStore, combineReducers, applyMiddleware } from 'redux';
import myReducer from "./todos/reducer";
import logger from 'redux-logger';
import thunk from 'redux-thunk';

const rootReducer = combineReducers({
todos: myReducer
})

export default createStore(rootReducer, applyMiddleware(thunk, logger));
