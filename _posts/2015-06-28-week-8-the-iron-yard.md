---
layout:     post
title:      "Week 8 The Iron Yard"
subtitle:   "APIs, Ember.js, and React.js"
date:       2015-06-28
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---
### Learning to learn
It's hard to believe but we are now 2/3s done with Rails Engineering at The Iron Yard. We only have one more month left and so many more things to learn. One of TIY's sayings is that they teach you how to learn. To this end, I often see Jesse purposely not give a full answer because he wants you to bang your head a little. Make no mistake, you don't magically learn stuff at The Iron Yard. You have to work for it. On our first day, Jesse was clear that the only way for us to learn enough to become junior dev ready in 12 weeks is to push us just beyond our comfort zone. In recognition of this, I must say, I have learned an amazing amount and I have definitely learned how to learn more efficiently. I mean, I am no <code>React.js</code> expert but the fact that I can read and understand docs enough to build a working product (albeit simple) within a day is amazing. There is no way I could have reached this point in two months by myself. I love what TIY has helped me accomplish. I am excited what another month at TIY will bring.

### Monday
We're still in catch up mode due to our missed days so no challenges for this week either. Today's lecture is over consuming APIs. Basically, we are shown how to make requests to other people's APIs and how to process the response. I think the coolest thing is learning about the some of the awesome APIs that are already out there. Jesse showed us the <a href="http://deckofcardsapi.com/" target="\_blank">deckofcardsapi</a> and you can hear everyone asking in their heads why we made <a href="{{ site.baseurl }}/week-2-the-iron-yard-and-my-first-hackathon.html" target="\_blank">blackjack</a> from scratch. It's funny how complicated it use to sound when I heard something like, "make an API request." Now it's just like, oh it's just going to a URL and pulling a hash.

<a href="https://github.com/tiy-hou-q2-2015-rails/day-36" target="\_blank">Homework</a> is to deploy a Rails app that will get the 10 most recent Etsy listings using the Etsy API. Solution: <a href="https://github.com/joeypoon/etsy_api" target="\_blank">Code</a> \| <a href="https://joey-esty-api.herokuapp.com/" target="\_blank">Site</a>.

### Tuesday
Today's lecture is the meat of the week. Creating an API. Rails maybe a full-stack framework but it is extremely common for it to be used just for back-end. I imagine this is because Rails makes it super easy to create an API server that spits out json data using jbuilder. To demonstrate how to create an API and why we create APIs, we created a <a href="https://github.com/tiy-hou-q2-2015-rails/day-37/tree/master/atm" target="\_blank">bank ATM API</a> in class. This ATM API would be able to deposit and withdraw money from a customer's account securely through use of a token. The main difference between a Rails API and a full-stack Rails app is that you don't return html to the browser, but json which is really just a hash.

For <a href="https://github.com/tiy-hou-q2-2015-rails/day-37" target="\_blank">homework</a>, we are to create a Rails API which does the following:

    GET /posts to return all posts
    GET /posts/:id gives details of a post
    POST /posts creates a post
    PUT /posts/:id updates a post
    PATCH /posts/:id updates a post
    DELETE /posts/:id deletes a post

My <a href="https://github.com/joeypoon/day-37" target="\_blank">solution</a>.

### Wednesday
Today is a review day. Jesse went over both using and creating an API by building two separate Rails apps, one for front-end and one for back-end. Our example for this review is an <a href="https://github.com/tiy-hou-q2-2015-rails/day-38" target="\_blank">application for displaying books and authors</a>. I know I have the tendency to gloss over reviews in my posts so let me clarify how helpful they actually are. People do not usually learn things the first time they see it. This was what I experienced a lot of when I was self-learning how to program. I would finish a tutorial and be like hah! ezpz. But when I was done, I still had trouble applying it more broadly to build something from scratch. It would take me almost a year before I could even <a href="{{ site.baseurl }}/working-efficiently.html" target="\_blank">start writing something from scratch</a>.

It's vastly different to go over a scripted tutorial versus seeing a programmer (who has an aptitude for teaching) write something from scratch. You get to see the thought process, the problems that occur and how to solve them, and you get to ask questions right then and there. This has been essential to my rapid growth. Information is far more easily absorbed when I can understand why each step is taken. Even the best tutorials do not do this perfectly. This is especially important when learning something like Rails which makes a lot of assumptions about how you should program and name things. I have spent countless hours trying to figure out why something didn't work only to realize that I didn't name it correctly.

Another vital part of being in a classroom with someone like Jesse is that you learn how to debug. The fact is that your program will almost never work the first time. You need to learn how to figure out what the problem is in a systematic way. Being able to watch Jesse run into problems and how he thinks through them has been essential to my ability to debug.</rambling>

Jesse is going to be out for the rest of the week so we get <a href="https://github.com/tiy-hou-q2-2015-rails/week-8-lab" target="\_blank">lab</a> early this week. This week is our first paired project (kind of...). Each pair is to create an API server and a front-end to request and display that data. The app itself is basically an anonymous messaging board. It's super cool to see group projects because this will give you a good idea of the workflow when employed as a dev. I imagine the hardest part of this lab for most pairs will simply be to effectively separate tasks/features(Trello is awesome for this) and manage their git repo. However, our Rails Engineering class has 9 people. As Jesse worded it: "Joey, you will not so randomly be working by yourself." I am a little sad that I won't be able to experience a paired project yet but also a little happy with his confidence in me. Either way, next week's lab will be a group project with the front-end class so I'm not too worried about it.

Another interesting thing about separating the front-end and back-end is that we now have to think slightly differently. We now have to not only think about features but also break those features down into which parts should be back-end and which parts should be front-end. For example, when you log in a user, you need to both authenticate the user and change the UI to reflect that the user has been signed in. So we now have to break the login feature into a back-end user authentication and a front-end rendering of UI. The back-end then has to determine what info they want for authentication and what data do they need to feed back to the front-end. The front-end then has some UI and UX decisions to make with the data that was fed back. I'm glad that we get to start learning to think this way.

### Thursday
Jesse is out and I'm doing the lab on my own so I decided to just work from home today. The lab itself calls for a Rails back-end and a Rails front-end but I decided that I wanted to make it a little more interesting by using a JavaScript front-end framework instead, <code>Ember.js</code>. I did a quick version of the back-end since I knew I would be spending a ton of times in Ember docs. Jesse is huge on Ember.js and I can understand why. Ember-cli makes it very similar to Rails and it took me almost no time to get a semi-working front-end. It took me less than half a day to get Ember to display my posts list, create a post, create a user, and send a request to authenticate a user. The problem came when I had to find a way to do user sessions. Theoretically, I should be able to easily use Ember Data's <code>DS.store</code> to hold the session data. I spent an entire day trying to get it to work.

Matt (Our Houston front-end instructor) gave me a hand and used some expert JS debugging skills to give me a solution but as I continued trying to use Ember, I realized that the session info was not persisting between page reloads. I love the idea of Ember, but I found the docs to be quite outdated. To be fair, I was probably a little too confident with my learning ability to try to learn Ember while our resident Ember.js expert (Jesse) was out. I'm sure if I were more experienced that I could figure it out but there was no way I could finish my lab before the end of the weekend at the pace I was going. And so I made the decision to put Ember on hold and at the advice of Matt, try <code>React.js</code>.

The first thing I can say about React.js is that it has some pretty nice docs. It took me about a day but I was able to implement a basic version of the lab in React. One of the key ideas of React is the use of components. Components are basically custom made HTML elements which enjoys some custom implementations. For example, I can make a <PostForm> component and reuse it. I think of it as I think of Rails partials. The cool thing is that components are a thing in Ember too and I do plan on re-visting Ember again next week. Another key idea of React is that components should be structured in a way that data flows in a linear fashion. Basically, data should only be accessible within parent-child relationships. This was a little tough for me and I ended up cheating by not using React's <code>setState</code> but instead using <code>sessionStorage.setItem()</code>. I think I can fix that by creating an app component and nesting but... time. I'm sure that I'm missing out on a lot of the React.js way of doing things, but here's my current solution: <a href="https://github.com/joeypoon/secrets" target="\_blank">Code</a> | <a href="http://joeypoon.com/secrets/" target="\_blank">Site</a>. The posts may take a second to load in the beginning since my back-end is on Heroku and the server will go to sleep if unused for a period of time. I am super proud of the non-existent load time when creating a new post though :).

### Friday
Our guest speaker today is Jeff Reichman from January Advisors. I met Jeff back during the <a href="{{ site.baseurl }}/week-2-the-iron-yard-and-my-first-hackathon.html" target="\_blank">3rd annual Houston Hackathon</a> and he is big on making Houston a better place using technology. He shared with us the some amazing facts about the City of Houston government and how we as devs can help make the city a better place. The City of Houston has a huge amount of data that isn't being utilized and as devs we are in prime position to help make the data useful.

I also spotted Efrain, who we had as a speaker during our <a href="{{ site.baseurl }}/week-1-the-iron-yard.html" target="\_blank">first week</a>, in the building so I checked in with him to see how his accelerator experience was going. Apparently he's in Houston this weekend to meet with some investors. Such cool, much jealous.

### Other things
I have to admit that I am loving the things I can do with JavaScript. Looking at my previous Rails apps, they feel kind of clunky in terms of load times. The language itself still hasn't made much of an impression on me but I definitely can't live without it anymore.

So I was asked yesterday about how I organize my Trello boards for projects. I'm still learning and adapting but here's the <a href="https://trello.com/b/VkKMuy6X/staple" target="\_blank">board</a> I used for <a href="{{ site.baseurl }}/week-7-the-iron-yard.html" target="\_blank">last week's lab</a>. It's terrible and I'm still trying to figure out a systematic way of organizing it but the basic idea is that each card should be a feature. If I think of a feature I want, I add it to the board immediately so I don't forget it. If I'm in the middle of working on a feature, I don't stop and switch but just add the idea to the board and finish my current feature card.

When I implement a feature, I always start with the simplest implementation. In the same way, I usually work on cards in order of simplicity. If I think of something that I feel like the feature should also do, I just add a card. For example, let's say I want a login form within a modal. Well, that's really multiple steps:

    1: login form
    2: form submission
    3: processing form request
    4: moving the form to a modal

In Trello, I would probably make all 4 a separate card. I'm not 100% sure on this since one can argue that a login form automatically means that you will need to have form submission. However, when programming, I would definitely create the form first and make sure that it displays before I worry about the form submission. This is a vital idea since if you implement an entire feature and it doesn't work, it makes it harder to figure out what part of it is broken. Always get one thing working before you move on to the next part.

Well, that's it for this week. As always, if you have any questions or concerns, feel free to tweet <a href="https://twitter.com/JoeyFPoon" target="\_blank">@joeyfpoon</a>.
