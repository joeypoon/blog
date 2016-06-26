---
layout:     post
title:      "Undertanding JavaScript"
subtitle:   "Fundamentals"
date:       2016-06-25
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---
This week I spent quite a bit of time brushing up on some JavaScript fundamentals so I thought it would be a good idea to do a review.

### Variable Hoisting
In JavaScript, variable declarations are automatically hoisted to the top of the current scope. This means that

<script src="https://gist.github.com/joeypoon/76788be38e5e6c79cc32dfb7ab8db438.js"></script>

Is the same as

<script src="https://gist.github.com/joeypoon/cf554a9ad025fba8d96f15080561ee81.js"></script>

Only declarations are hoisted

<script src="https://gist.github.com/joeypoon/e1990515253f1a5204196e88a9db508d.js"></script>

Is *not* the same as

<script src="https://gist.github.com/joeypoon/1c6f8cf036ca47a1ebdfae3ccd251d59.js"></script>

It logs undefined because only the declaration and not the initialization is hoisted to the top.

### Closures
You may have seen something like this before

<script src="https://gist.github.com/joeypoon/5bf7e02fe8b96480f2737f75291d7896.js"></script>

Albeit simple, this is an anonymous function in a closure which calls itself. So what good are closures? Closures are great for emulating private variables and methods. Let's look at an example:

<script src="https://gist.github.com/joeypoon/f8534b27a9653cec9b4a60698dcedb70.js"></script>

The count variable is private and can't be modified outside of the increment method we defined.

### Classes
Prior to ES2015 and the class keyword, constructor functions were the only way to create classes in JS.

<script src="https://gist.github.com/joeypoon/f01b85b585afcbb27dd4a21249cec811.js"></script>

Now with ES2015 we can do:

<script src="https://gist.github.com/joeypoon/33d61d85e5036b40ddfc92d3acdf178c.js"></script>

As you can see above, you can also use the static keyword to create a class method. Now, we can't talk about JS classes without talking about prototypes. JS isn't really a classed language, it is a prototype-based language. Even the class keyword in ES2015 is just syntax sugar. Under the hood, JS still uses prototypes. A prototype is just an object's parent object. What this means is that we can inherit methods through the prototype.

<script src="https://gist.github.com/joeypoon/12e5f90b4cf3139ac07a22e1047532da.js"></script>
