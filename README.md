# Redux

Redux attempts to make state mutations predictable by imposing certain restrictions on how and when updates can happen. These restrictions are reflected in the three principles of Redux.

- [Pure / Impure Functions](pure_impure_function.md) 
- [The Reducer Function](reducer_function.md)
- [Store](store.md)
- [Avoid Array Mutations](array_mutations.md)


## Why?

**A little background :**

- Facebook's Flux Architecture.
- Dependencies between models and data between these models.

## Redux

Way simpler.

Main Ideas:
 - Single source of truth
 - Unidirectional Data Flow
 - Read Only State
 - Enforces immutability
 - Composable
 - "It's all just functions"

We can say, Redux is divided in three parts:
 
Model | VIEW | UPDATE from Elm Language.

**STATE --> VIEW --> UPDATE**

## Action

An action should have a type, mostly a string.
```javascript
{ type: 'SOME_VALUE'
  payload: {}
}
```

## Dispatcher

The action goes into the Dispatcher function,

```javascript
store.dispatch({
  type: 'SOME_VALUE'
})
```


## Reducer
It receives two arguments.

```javascript
const initialState = {}

function reducer(state = initialState, action){
  return state;
}
```

A normal symple how a reducer function normally works:

```javascript
const initialState = {};

function reducer(state = initialState, action){
  switch(action.type) {
    case LOG_EVENT:
      return [action.payload, ...state];
  }
  return state;
}
```

## Subscribe

```javascript
store.subscribe(() =>
  let currentState = store.getState();
);
```

## Middleware

It provides a third-party extension point between dispatching an action, and the moment it reaches the reducer. People use Redux middleware for logging, crash reporting, talking to an asynchronous API, routing, and more.


## Simplicity

`(state, action) => state`


