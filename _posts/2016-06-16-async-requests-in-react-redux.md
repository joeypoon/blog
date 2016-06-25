---
layout:     post
title:      "Async requests in React + Redux"
subtitle:   "Remote action middleware"
date:       2016-06-16
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---
So recently I had the pleasure of integrating React + Redux into an Angular/Rails project at work and I needed to come up with a good way to organize async requests. For some reason I neglected to google at the time to see that there were options like redux-thunk but I’m kind of happy with the result. So without further ado:

Just a regular ajax request.

<script src="https://gist.github.com/joeypoon/ddd0ee5b8ca58ef7f7897b6177668c1c.js"></script>

Include the request and request params in the action.

<script src="https://gist.github.com/joeypoon/dd91899a25945291e6bed749342f818b.js"></script>

Check in the middleware for a remote action and call it with the params.

<script src="https://gist.github.com/joeypoon/897247cb88a0934e18bed97b1373d0d9.js"></script>

Hook the middleware into the store.

<script src="https://gist.github.com/joeypoon/7fbfd8bf65984f1f50bdc488dad36459.js"></script>

So basically anytime an action with a remote is created, the async request will automatically be called in the middleware.
