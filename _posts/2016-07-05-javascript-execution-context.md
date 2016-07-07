---
layout:     post
title:      "JavaScript Execution Context"
subtitle:   "What happens when functions get called"
date:       2016-07-05
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---
<a href="{{ site.baseurl }}/understanding-javascript.html" target="_blank">Variable hoisting</a> is simple enough to understand; variable declarations are hoisted to the top of the current scope. Why does this happen? Let's take a look.

### Execution Context
When you call a function, you enter a new *execution context*. Think of it as the context of this function's execution; the function's stuff if you will. Within the *execution context*, there are actually two stages.

### Creation Stage
The first stage is the *creation stage*. Code is not executed during the creation stage, it simply sets up the context for the function to run later. The first thing it does is set the *scope chain*. The *scope chain* is basically all the scopes this function can access.

<script src="https://gist.github.com/joeypoon/097119fdea1d858ba7c7279266d8ee06.js"></script>

Next, the variables will be setup. This is called the *variable object* and it holds the arguments, function declarations, and variable declarations. Every function has access to an object called arguments which represents the arguments passed into the function. This is where the arguments object is set.

<script src="https://gist.github.com/joeypoon/a32efd5eddc6542705aec3f1893c7ed4.js"></script>

Following the arguments object, any function declarations are set on the *variable object* with the function name as its key. Note that `function foo () {}` is a function declaration but `var foo = function () {}` is not. The latter is just a variable holding a pointer to an anonymous function. This is important because the way variable declarations are set is different from the way arguments and function declarations are set.

Variable declarations are similar to function declarations in that they are set as a property on the *variable object* with its name as the key. However, unlike function declarations, the value of these properties are set to `undefined`.

The last step of the creation stage is to set the value of `this`.

### Activation Stage
The next stage after the creation stage is the *activation stage*. This is simply running through each line of the code sequentially and executing.

### Visualing the Execution Context
The execution context can be visualized as an object. Let's take a look at what it looks like after the creation stage.

<script src="https://gist.github.com/joeypoon/d8a2b6d67bae6b5c5cc72ad8637d3b4b.js"></script>

You can see here that the variables x and y are undefined. This is where hoisting comes from. This is why:

<script src="https://gist.github.com/joeypoon/ec047c1e6e1574065f75a2aa846a9b16.js"></script>

`bar` is set to `undefined` at the end of the creation stage and since `console.log(bar)` executes before `var bar = 1` during the activation stage, it logs `undefined`.

### What about global
You might be wondering why hoisting works in the global context. Well, that's because there's a *global execution context* that operates exactly like the function *execution context*.

If you want a more in depth look at *execution context* from a much smarter person, I highly recommend this <a href="http://davidshariff.com/blog/what-is-the-execution-context-in-javascript/" target="_blank">post by David Shariff</a>.
