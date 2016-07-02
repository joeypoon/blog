---
layout:     post
title:      "Performance Optimization"
subtitle:   "JavaScript Profiling with Chrome Dev Tools"
date:       2016-07-01
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---
### The Problem
So these last couple of days, I have been trying to optimize a certain page at work. It already received a partial rebuild from Angular to React but we were starting to see some slow down when the page got busy. The busiest part of the page is a table (about 25 rows x 10 columns) that received 1 or 2 updates every 5 seconds per row. This proved to be a performance problem with the <a href="{{ site.baseurl }}/understanding-angular-data-binding" target="\_blank">`$digest` cycle constantly retriggering</a> so we rewrote the table in React. This improved the situation but we still see a slowdown when it gets busy; enter JavaScript profiling with Chrome Dev Tools.

### JavaScript Profiling
JS profiling allows us to see exactly what functions are using up our resources and how long they are running for. To start profiling: cmd + alt + i to open up dev tools, click profiles, select collect JavaScript CPU profile, and click start. Click stop when you're ready to stop recording. By default you'll see the data organized by 'Heavy (Bottom Up)' which shows you the most time intensive functions on top. I like to use the flame chart since it's more visual; click 'Heavy (Bottom Up)' and select chart. Here's what mine looked like:

<a href="{{ site.baseurl }}/img/performance-optimization-before.png" target="\_blank">
  <img src="{{ site.baseurl }}/img/performance-optimization-before.png" />
</a>

It defaults to a zoomed out view but you can zoom in to the trouble areas for a more detailed look as I have above. I can see here that my `$digest` cycle is taking a good ~150ms. I can also see that the vast majority of the `$digest` cycle is being taken up by `angular.copy`. `angular.copy` is used by `$digest` to copy the value of a `$watch` for dirty checking. This tells me that I should probably look at my `$watch`ers.

### Watching the `$watch`ers
If you're interested in an easy way to look at your `$watch`ers, I found this <a href="https://medium.com/@kentcdodds/counting-angularjs-watchers-11c5134dc2ef#.cpc8prsle" target="\_blank">post</a> to be especially useful; it's what I used. A quick check gives me >300 `$watch`ers. That's more than I expect given that the main table is built with React. 300 is a bit much to look through manually so I remove all the elements on the page other than the main table itself. This leaves me with 16 `$watch`ers, much more managable. Digging through the `$watch`ers I find something interesting, an array with the same length as the current number of table rows (of course it's the last one I check...).

<a href="{{ site.baseurl }}/img/performance-optimization-watchers.png" target="\_blank">
  <img src="{{ site.baseurl }}/img/performance-optimization-watchers.png" />
</a>

Looking through the code, I see that the array is actually a `$scope`d Angular model being passed in to the React table as a prop. I know that the objects inside the array are fairly complex so my theory at this point is that `angular.copy` is having trouble deep copying all the objects.

### Testing my Theory
I had already setup a Redux store so it is easy to test my theory. Instead of passing the array directly to the React table, I will send it to the store using `store.dispatch` and use `ReactRedux.connect` to hook it into the React table. Let's test the results:

<a href="{{ site.baseurl }}/img/performance-optimization-after.png" target="\_blank">
  <img src="{{ site.baseurl }}/img/performance-optimization-after.png" />
</a>

I can't even find `$digest` or `angular.copy` on the flame chart anymore. What a beautiful time improvement :).
