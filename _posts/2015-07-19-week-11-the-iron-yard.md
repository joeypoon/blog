---
layout:     post
title:      "Week 11 The Iron Yard"
subtitle:   "Angular.js, linux, and a new adventure"
date:       2015-07-19
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---
### Impending End and Beginning
Time passes far too fast. I honestly can't believe that my time as an Iron Yard student is coming to an end. It feels like just yesterday that I started learning Ruby. Today, building and deploying full stack Rails apps is an everyday fact. Thanks to Jesse and everyone at the Iron Yard, I can now call myself a software engineer. That's right, this past week I received and accepted an offer to be a full-time software engineer. It has been a long journey from my first line of html over a year and a half ago. I look forward to what I will learn in the next year and a half.

### Project Update
So much sadness and happiness but we're not quite there yet. With my start date on Monday, we have one less week to finish our final project. Fortunately we made some breakthroughs this week. Look at this beauty:
<img src="{{ site.baseurl }}/img/contacts-1.jpg" />

Okay, so it still needs tons of styling but most of the features essential for minimum viable product are up and running. An interesting challenge I faced this week is the restructuring of the data models. It was a ton of headache and fun because the most complicated data relationships I've had to deal with so far is probably my <a href="https://joey-staple.herokuapp.com/login" target="\_blank">Staple project</a> from <a href="{{ site.baseurl }}/week-7-the-iron-yard" target="\_blank">week 7</a>. Category tags and user follows are easy with gems.

This is the first time I had to create so many relationships by hand. The hard part isn't actually writing them, however. The hard part is figuring out the best way to structure your models. Users have contact information and locations that they need to share to other users. Users also need contact lists to store other users and they need to be able to choose what information to share on each share. At one point I tried putting everything in a separate model and it got messy fast. I have since found a happy medium but I still can't shake the feeling that my tables have too many columns that should be their own tables. Hopefully some time later I can look back at the models and laugh at how silly it is.

### Random Learning
A fairly common thing I see on job listings is the ability to setup a linux server. Wat. Can I just use Heroku? No clue how to linux so I asked Justin. I'm not sure if I have talked about it but Matt is moving up the Iron Yard ladder and Justin from <a href="{{ site.baseurl }}/week-2-the-iron-yard-and-my-first-hackathon" target="\_blank">week 2 fame</a> will be taking over Matt's teaching duties. So anyways, Justin showed me how he hosts his websites and I was like oh. Using linux is basically using terminal. It makes sense why TIY makes us use macs now. Just ssh into your linux box and ftp your Rails app and all is well. Definitely going to try to port some of my Rails apps to digitalocean or something.

During the interview for my new position, they mentioned that they need Angular.js so I started learning Angular this week. It's honestly pretty straight forward. You have controllers that you link to your html using directives. I haven't dug too deep yet but on the surface, it seems easier to understand than React. I still haven't formed an opinion on which one I like more.

### The Talks
Our speaker this week is a <a href="{{ site.baseurl }}/week-2-the-iron-yard-and-my-first-hackathon" target="\_blank">revisit</a> from Daniel @ Stackwave. Daniel's talk is a deeper look into SQL databases. Daniel went over the basic mathematical premise that powers SQL dbs. He also very succulently explained how certain SQL functions like table joins work. For me, the biggest ohhhhh moment is when he explained entity integrity and referential integrity. I had previously thought that uids and foreign keys were the same thing. This made it difficult to understand the point of something like add_index in Rails. I love listening to smart people.

My team and I also had the chance to meet with Hesam <a href="{{ site.baseurl }}/week-10-the-iron-yard" target="\_blank">again</a> for coffee. We arranged a meet time when we met him last week to get some tips on next steps and focus points for our project if we are to make it commercial. We have been so focused on getting a working product that we completely forgot about some important logistics. Things like time commitments from each member after Iron Yard, equity, and surveying users.

I believe that Brian also gave a cover letter talk but I wasn't able to make that one :sadface:.

### Other Stuff
This upcoming week will be my first week in my new career and demo day. Expect exciting things :).
