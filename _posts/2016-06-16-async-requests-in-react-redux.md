---
layout:     post
title:      "Async requests in React + Redux"
subtitle:   "Remote action middleware"
date:       2016-06-16
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---
So recently I had the pleasure of integrating React + Redux into an Angular/Rails project at work and I needed to come up with a good way to organize async requests. For some reason I neglected to google at the time to see that there were options like redux-thunk but I’m kind of happy with the result. So without further ado:

Just a regular request.

```javascript
// utils/my_util.js
import fetch from 'isomorphic-fetch'

export default function myUtil () {
  fetch(‘/my_resource’)
    .then(data => //dispatch to store with new data)
}
```

Include the request and request params in the action.

```javascript
// action_creators/my_action.js
import myUtil from '../utils/my_util'

export default function myAction (myParam, myParam2) {
  return {
    type: 'MY_ACTION',
    meta: {
      remote: myUtil,
      remoteParams: [myParam, myParam2]
    }
  }
}
```

Make request with the params if there is a request in the action.

```javascript
// remote_action_middleware.js
export default store => next => action => {
  if (action.meta && action.meta.remote) {
    action.meta.remote.apply(this, action.meta.remoteParams || [])
  }
  return next(action);
}
```

Hook the remote action middleware into the store.

```javascript
// store.js
import remoteActionMiddleWare from './remote_action_middleware'
import { createStore, applyMiddleware } from 'redux'
import reducer from './reducer'

const createStoreWithMiddleware = applyMiddleware(
  remoteActionMiddleware
)(createStore)
export const store = createStoreWithMiddleware(reducer)
```

So basically anytime an action with a remote is created, the async request will automatically be called in the middleware.
