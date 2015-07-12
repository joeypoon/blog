---
layout:     post
title:      "Week 9 The Iron Yard"
subtitle:   "More React.js, some Backbone.js, and distributed systems"
date:       2015-07-04
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---
### JavaScript is kind of...cool
Okay, I'm really starting to like JS. Rails is awesome but with the current state of web applications, a full Rails app doesn't produce the kind of UX that's needed for a serious product. While I wish this wasn't the case, at least I can still use Rails to be awesome for the back-end. I actually tried Meteor.js and found it super intuitive and easy to use but the part of me that paid to learn Rails won't let me go on without Rails. Fortunately, we have front-end frameworks and libraries to supplement our Rails back-end.

### Monday
This is speculation but it looks like we won't be getting anymore challenges for remainder of the program. This is end of week 9 and the end of our main lecture topics. Since we didn't get a challenge today, I imagine we won't be having anymore.

Today's lecture is over the super important topics of ecommerce and mailers. Jesse starts with a brief history of internet payments that leads to Stripe. Jesse then shows us how to integrate Stripe payments using the Payola gem. We are then shown how to utilize the built in Rails mailer to send receipts. It's super awesome how easy Rails makes things. That's how technology should be, making things easier.

<a href="https://github.com/tiy-hou-q2-2015-rails/day-41" target="\_blank">Homework</a> is optional but...yeah I still did it. Basically we are to make an app that displays products that you can then fake buy with Stripe. Solution: <a href="http://joey-store-front.herokuapp.com/" target="\_blank">Site</a> \| <a href="https://github.com/joeypoon/store_front" target="\_blank">Code</a>.

### Tuesday & Wednesday
So this week is a little different. The next two days actually take place in the commons room because we're having joint lecture. Jesse and Matt will be creating a web app together. The goal of this joint lecture is to demonstrate some issues you run into working on a distributed project, how to solve them, and best practices.

The project that Jesse and Matt decided to create is an imgur clone called imgderp. Jesse created the Rails API while Matt developed the front-end with React.js and Backbone.js. This is probably one of my favorite lectures during my time at the Iron Yard. As you know, I have been playing around with different front-end frameworks and libraries. To see someone as experienced as Matt explain and walk us through his thought process on the front-end was tremendously helpful for me. Your mileage may vary, however. I have no doubt that if I didn't play with React.js just a couple days earlier that I would not have gained as much out of it.

One of the challenges I had with React.js was routing. Rails makes routing ridiculously easy. Needing to handwrite the logic for routing was a little daunting for me. Matt walked us through the process of routing in Backbone.js and how to proxy the request through the server so that we wouldn't get CORS errors when connecting to our API. A second challenge I had with React.js was structuring my application in a way that data could flow through parent-child relationships. Witnessing Matt build the front-end of the app from ground up really helped me grasp the structure better.

### Thursday
On the agenda today is a revisit from <a href="{{ site.baseurl }}/week-3-the-iron-yard/" target="\_blank">JB</a> to do a TDD coding dojo. Kind of. We ended up doing this instead:
<a href="https://twitter.com/JoeyFPoon/status/616675374177615874" target="\_blank"><img src="https://pbs.twimg.com/media/CI7e-mYW8AMLeH_.jpg" /></a>
(Note: Based on how Jesse plays Sheriff of Nottingham, there is a high probability that he runs the blackmarket.)

Just another day at TIY :). Friday is no class for Independence day, happy 4th all!

### Other stuff
So I'm sure you've noticed, we didn't have lab this week. We were planning on having a distributed systems project between the front and Rails classes but Jesse and Matt made the executive decision that the scope of the project was probably too large and would take too much time. We are instead to work on our final projects. Yep. That's right, it's time for final projects. I still don't know where the last 9 weeks have gone and it is definitely a bittersweet feeling. Jesse did post an <a href="https://github.com/tiy-hou-q2-2015-rails/week-9-lab" target="\_blank">optional lab</a> for us which I may work on if I have the time but right now I'm focusing on my final project.

I am a little scared about the scope of my project. My plan is to develop a mobile app that lets you see and share contact info with those around you. Think meetups and events. It's entirely possible that two weeks in, I will realize that I've dug myself too deep. The Rails part should be pretty simple but creating a mobile app will require a well built front-end wrapped in Cordova or perhaps React native. The basic API and React/Backbone is done already so hopefully the fine-tuning and mobile'fying won't be too bad. Jesse approved the project so I'm hoping that means that he knows it can be done by demo day.
