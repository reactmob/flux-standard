ReactMob Flux Standard (RMFS)
============================

## Introduction

A machine-friendly (ReactMob-friendly) standard for Flux objects. Feedback welcome.

### Motivation

See https://github.com/acdlite/flux-standard-action
And for ReactMob we like to define meaningful semantic to use across `component` and `middleware`.  

### Design goals

- **Semantic.** RMFS should be meaningful or describe their intent.
- **Simple.** RMFS should be simple, straightforward, and **MUST** to use `FSA.meta` in action.

### Implementation
RMFS's lib do nothing in `production` just check in `dev`.

### Action Example

ReactMob Flux Standard Action:

```js
{
  type: 'ADD_TODO',
  payload: {
    text: 'Do something.'  
  },
  meta: {
      show_loading_indicator: true
  }
}
```

### Component Example
TODO

### Middleware Example

```js
export const showLoadingIndicatorMiddleware = store => next => action => {
    
    switch (action.meta['show_loading_indicator']) {
        store.dispatch('somr action');
        // or
        actionSubscribers.reduce(store.dispatch)
    }
    
    next(action);
}
```
