---
layout:     post
title:      "Week 7 The Iron Yard"
subtitle:   "Learning JavaScript"
date:       2015-06-21
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---
### Week of JavaScript
This week is the week of the all too essential JavaScript. I can't say that I'm too fond of the language itself but I can't deny that you can do some awesome things with JS and that it is a must learn for any web dev. I'm actually teaching myself Ember.js on the side since I plan on using ember-rails-cordova to create a mobile app in my final project. I am really starting to feel the sleep deprivation this week. Having to work while doing TIY is exhausting. Software is never finished and there is never enough time to add and fix everything you want to. I really need to work on getting to sleep earlier.

### Monday
Today starts our JavaScript adventures. <a href="https://github.com/tiy-hou-q2-2015-rails/day-31" target="\_blank">Challenge</a> today is to write a program that will return the worst movie provided a <a href="https://github.com/tiy-hou-q2-2015-rails/day-31/blob/master/movies.json" target="\_blank">list</a> of movies. We never formally covered JSON but I imagine Jesse gave a brief explanation on how to read a JSON file in Ruby. I was a little late this morning so I unfortunately missed out on that. Fortunately, JSONs seem simple enough to use. When you look at the file, you can see that it is just a hash so completing the challenge is just a matter of pulling out the right information. <code>movies.json</code> provides an enormous amount of information so my first step is to use <code>.map</code> to extract the movie titles and ratings. I can now sort the new mapped array by the ratings and simply return the first movie in the array. My <a href="https://github.com/joeypoon/iron_yard/blob/master/day-31/challenge.rb" target="\_blank">solution</a>.

Our first JS lecture starts with a brief history on the interwebs. After history, we start playing around in jsbin. Jesse's philosophy of learning a new language is to draw parallels to your primary language. Such was our lesson. We would write out how to do something in Ruby and then translate it into JavaScript, each time noting the differences. We covered the basics such as <code>var</code>, <code>function()</code>, <code>console.log()</code>, <code>alert()</code>, and debugging with the inspector. We also briefly touched on <code>underscore.js</code> which is pretty awesome because it basically gives us access to Ruby methods.

<a href="https://github.com/tiy-hou-q2-2015-rails/day-31" target="\_blank">Homework</a> is a carbon copy of <a href="{{ site.baseurl }}/week-1-the-iron-yard/" target="\_blank">day 1</a> but in JavaScript. My <a href="" target="\_blank">solution</a>.

### Tuesday
Uncle (tropical storm)Bill didn't want us to have class today.
<img src="{{ site.baseurl }}/img/hurricane-bill.jpg" alt="hurricane-bill">

### Wednesday
Morning challenges are being cancelled for the rest of the week. We've now missed 2 days of class due to weather so we're trying to keep up with the lectures. Straight into lecture we go!

Today we have jQuery and remote forms in Rails. jQuery makes using JavaScript so much more bearable. Being able to get elements with <code>$('.className')</code> as opposed to <code>document.getElementByClass('className')</code> makes me so much happier. The number of lines of code you save using jQuery over vanilla JS makes me cry salty nerd tears. Remote forms are basically JS forms. The response is provided in JS instead of HTML. This is useful for responsive sites since you don't have to reload the entire page.

Tonight's <a href="https://github.com/tiy-hou-q2-2015-rails/day-33" target="\_blank">homework</a> is practice with enumerables in JavaScript. We get to cheat and use <code>underscore.js</code> since we're not a JS class 😀. Honestly, I considered just teaching myself to use CoffeeScript since it seems much more intuitive to my brain but I figured that I would need vanilla JS in the future. My <a href="http://jsbin.com/hepekiteva/edit?js,console" target="\_blank">solution</a>.

### Thursday
Today is mostly a review day. The only real addition is lots of modals and throwing remote forms into modals. Bootstrap is your friend.

<a href="https://github.com/tiy-hou-q2-2015-rails/week-7-lab" target="\_blank">Lab</a> this week is building Pinterest using tons of modals and remote forms. The goal is to only refresh on login and on <code>root_path</code>. I actually planned to speed through this lab and spend the weekend filling my brain with some more <code>Ember.js</code> but things got complicated fast. I never used Pinterest before but researching Pinterest made me realize that it actually has a ton of features so my Trello board kept getting longer and longer. I found myself rethinking how I want to implement certain features constantly. As a result, I kept backtracking.

It is funny how some things may seem complicated at first but once you break it down into pieces it eventually comes together. It's one of the reasons I love programming so much. When I started planning allowing users to favorite posts, I actually ended up taking a loooooong break because the thought of the number of things I need to do just sounded like a lot when I bunched it all together. When I finally sat back down and broke it into pieces it looked simple:

    * need a place to save favorited posts - add column to users table
    * need a way to view own favorited posts - add route/action/view
    * need to see a user's favorited posts - add that user's favorited posts to displayed posts
    * repeat some of the above and modify for un-favoriting

Of course there was some debugging thrown in but the ability to break problems down into such small pieces is just such an amazing part of coding. Also praise version control. I would be way too scared to make changes to my code without <code>git checkout -b branch_name</code>. Since I am praising things, <a href="https://github.com/github/hub" target="\_blank">hub</a> is an awesome addition for git. I'm not entirely happy with the number of features yet but here's where I'm at currently for my lab: <a href="https://github.com/joeypoon/staple" target="\_blank">site</a> \| <a href="https://joey-staple.herokuapp.com/" target="\_blank">code</a>.

### Friday
Our guest for the week is Darren Ansley. Darren comes to us today with an inspiring story of how he started from humble origins and over the years has become an amazing programmer. It is a great reminder that if you stick to your passion relentlessly, you will succeed.

With final projects closing in, Martin and I had a little planning session. It's pretty amazing how much you can learn and the number of ideas you can get from asking others. The current iteration of my final project idea sounds nothing like my initial idea. It will be interesting to see how much more it'll evolve in the coming weeks.

### Other Things
It's amazing when I look at how much I've learned during my time at the Iron Yard. While it's great that I can build more cool things now, I think what's more amazing are the skills that I have learned along the way. One of the most important skills I have gained is definitely debugging. I mean it's almost embarrassing when I look at my old stuff.

<a href="{{ site.baseurl }}/learning-rails" target="\_blank">This</a> for example. I spent an entire day trying to figure out what was going on. When I look at it now, I can only slap myself for my stupidity. It had nothing to do with my JS not loading, I simply needed <code>$(document).ready</code> since my code was loading before my window was ready. If I had simply used the inspector, I would have seen that my JS was loaded but too early. I hope that I will continue to find the stupidity in my past code 😀.
