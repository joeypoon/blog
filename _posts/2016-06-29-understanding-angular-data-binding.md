---
layout:     post
title:      "Understanding Angular Data Binding"
subtitle:   "$watch, $digest, $apply"
date:       2016-06-29
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---
So this is a little late now that Angular 2 is coming out but I still have to write Angular at work so here it is: how Angular knows when data has changed.

### Angular Context
*Angular context* basically means something that Angular knows about. You've probably heard of `$watch`, `$digest`, and `$apply` before but may not have actually used them. This is because everything you use from the Angular library is automatically executed in the *Angular context* and will use `$watch`, `$digest`, and `$apply` for you. However, sometimes you run into bugs that you can't explain or performance issues and that is when knowledge of `$watch`, `$digest`, and `$apply` will be useful.

### $watch
`$watch` tells Angular to watch something for changes. Angular automatically adds a `$watch` when you use directives (`ng-model`, `ng-repeat`, etc) or data-binding \{\{ myModel \}\}. You can also manually tell Angular to `$watch` something:

<script src="https://gist.github.com/joeypoon/8ec148cb05ce428db9ebffe59d53dcb6.js"></script>

`$watch` checks by reference by default so if you need to check by value such as in the second example above, you need to pass `true` as the third param. It is important to note that `$watch` doesn't actually do dirty-checking or change the DOM to reflect the changes. When does that happen you ask?

### $digest
`$digest` is what actually checks for and triggers changes. When `$digest` is called the `$digest` cycle starts. During the `$digest` cycle, all of the `$watch`ers on the current and children scope are checked for changes. If any changes are present, the cycle is repeated. This will continue until no more changes are found (or 10 cycles looped) and the cycle ends leaving the DOM to be updated with the reported changes.

### $apply
So if `$watch` and `$digest` are enough to check for changes and update the DOM, why is this post not finished? Because when Angular runs the `$digest` cycle for you, it is actually calling `$apply` first. `$apply` calls `$rootScope.$digest`. This is an important difference for two reasons. First, this executes from the `$rootScope` instead of the current scope. Second, `$apply` will apply the `$digest` to the *Angular context*. This is good since Angular will be able to catch any exceptions.

And now you're an expert on Angular data binding.
