---
layout:     post
title:      "Week 4 The Iron Yard"
subtitle:   "Rails and dynamic pages"
date:       2015-05-31
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---

### Bittersweet
It's the end of my 4th week at TIY and it's a strange feeling. We've gone from variables and arrays on day 1 to creating <a href="https://github.com/joeypoon/surf_and_rails">dynamic pages with Rails</a> in less than 20 class days. With a third of the program now complete, I'm excited about what more I'll be able to do at the end of the whole program. At the same time, I'm sad to see time passing so quickly. These 4 weeks have been the busiest and yet the most rewarding weeks of my life. It's a bittersweet feeling. Oh, and I did <a href="{{ site.baseurl }}/week-3-the-iron-yard.html">eventually</a> finish our <a href="https://github.com/joeypoon/surf-and-paddle">week 3 lab</a>.

### Monday
Memorial day, no class 😢.

### Tuesday
Crazy rain caused some ridiculous flooding and freeways were all closed. Needless to say, TIY was closed too 😢.
<img src="{{ site.baseurl }}/img/houston-flood.jpg" alt="houston-flood-2015">

### Wednesday
Yay class! I have been so excited for this week to come. It's Rails week! But before that, <a href="https://github.com/tiy-hou-q2-2015-rails/day-16/blob/master/README.md">challenge</a>. Nothing too fancy today, just a bit of CSS positioning practice.

Lecture today is on...Rails! Bet you didn't see that coming! So excite, much knowledge. Jesse did a quick run through of a basic Rails app with static pages.

    rails new app_name
    rails g controller Pages action1 action2
    rails s

He talked us through a simple <a href="https://github.com/tiy-hou-q2-2015-rails/day-16/tree/master/texas">Texas Cities site</a>. During the walkthrough, he also went over routes, the gemfile, and the asset pipeline. No models yet.

After lunch, we had a review and Jesse ended up doing another talk-through of a <a href="https://github.com/tiy-hou-q2-2015-rails/day-16/tree/master/review">superhero static pages app</a>.

Homework is to create a basic Rails app with some pages. I made mine about <a href="https://github.com/joeypoon/iron_yard/tree/master/day-16">animals gifs</a> because why not.
<img src="{{ site.baseurl }}/img/dog-pooping.gif" alt="dog-pooping">

### Thursday
Today's <a href="https://github.com/tiy-hou-q2-2015-rails/day-17/blob/master/README.md">challenge</a> is some Ruby class review. The interesting thing about this challenge is the introduction of <code>class Date</code> to help us get the age of a person. I have to admit that I got a little cocky when I read challenge. <code>Date.today.year - @dob.year</code>, ezpz right? Nope. Doesn't pass the test because I forgot to account for whether the birthday has already passed or not for the current year. I was eventually able to come up with <a href="https://github.com/joeypoon/iron_yard/blob/master/day-17/person.rb">this</a> as a solution. I'm pretty sure this solution doesn't account for leap years and leap birthdays but our 15 minutes were up 😞.

What's not static? That's right, dynamic! Today's lecture is on dynamic pages in Rails. Jesse took our <a href="https://github.com/tiy-hou-q2-2015-rails/day-16/tree/master/texas">static Texas cities</a> app from yesterday and turned it into an app with dynamic pages. Dynamic pages are way cool. We basically deleted all of our views from the static example and were able to make a single view with changing content. This allows us to generate millions of pages for different products, like Amazon does, with just a handful of views. Dynamic routes are awesome too <code> get '/:post_name' => 'pages#show', as: :post </code>.

This is day 2 of the week but it is still Thursday so of course we still get a <a href="https://github.com/tiy-hou-q2-2015-rails/week-4-lab">lab</a> 😀. We basically have to take our <a href="https://github.com/joeypoon/surf-and-paddle">week 3 lab</a> and turn it into a Rails app with dynamic pages.

### Friday
Our guest speaker for the week is <a href="https://twitter.com/robyfitzhenry">Roby Fitzhenry</a>. Roby is a self-made entrepreneur and designer who speaks with passion. He shared his personal story with us and inspired us to follow our passion. One especially interesting moment to me was when someone asked Roby about front end vs back end pay. Roby's response was that you should do whatever you enjoy. If you enjoy it, you'll keep doing it and eventually you'll become great at it.

Roby also explained design in a very human way, simply as a narrative. The most important thing is the story that you are telling. I think that as someone who loves banging away at the keyboard to chip away at technical problems, I sometimes forget what the end goal is. That is that I am building products for humans. How I build and design my applications tell a story to my users. How the story is told is just as important as the story itself. <code>rambling.end</code>

So I actually finished the lab this week early and submitted it Thursday evening. Jesse, being the awesome instructor that he is, added nightmare mode Friday morning and made a point to let me know. You have to love it when an instructor adjusts for his students 😀. Since we're doing Rails now, I'll start adding both production and code links for Rails apps that I deploy. Week 4 lab: <a href="https://surf-and-rails.herokuapp.com/">production</a> \| <a href="https://github.com/joeypoon/surf_and_rails">code</a>. It's not really mobile responsive yet but I do plan on adding that in soon.

### Closing Thoughts
Rails is awesome. Small things like <code>.parameterize</code> and <code>.pluralize</code> really make Rails friendly to use. Ruby and Rails might not be the leanest but the ease of use makes it such a joy to program with. In the end, isn't that what technology is for? To make life easier? It's exciting to see how far we've come in 4 weeks and I definitely can't wait to see what we'll be able to produce by the end of 12 weeks. Next week is database stuff, can't wait!
