---
layout:     post
title:      "Week 6 The Iron Yard"
subtitle:   ""
date:       2015-06-13
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---
### Half Way
This week marks the half way point of the Houston Iron Yard Rails engineering program, made official with some <a href="https://twitter.com/matthiasak/status/609347338276986880" target="\_blank">BBQ by our very own Dotron</a>. It is unbelievable that we're already half-way in. I have been having so much fun that I haven't really thought about it but it is actually super scary to think about what's going to happen in 6 weeks. Another 6 weeks from now, we are all going to be working as junior devs or starting our own companies. Will we be ready? The imposter syndrome is strong in us.

### Monday
Oh noes, a broken app! Our <a href="https://github.com/tiy-hou-q2-2015-rails/day-26" target="\_blank">challenge</a> today is to fix it. When you look at it, this challenge is actually really smart. I mean, as a dev, cloning the repo of a broken app and fixing it is probably quite a real and fairly common scenario. It's also a super good exercise in teaching yourself how to troubleshoot. You clone the repo and check if it runs. It runs but you get a default Rails screen? Okay, check the routes. Routes fixed, what does localhost:3000 show now? Nothing. Okay, let's follow the route into the controller and corresponding view. Still not working? Let's see what console/inspector shows. Ah, can't load bootstrap huh? application.css needs to be renamed application.scss. My <a href="https://github.com/joeypoon/iron_yard/tree/master/day-26/railsy" target="\_blank">solution</a>. The funny thing about this exercise is that there is barely any coding at all. It's a good reminder that sometimes what's broken isn't necessarily the code but the most obvious thing.

Agenda for the day:

    * Session and Authentication
    * has_secure_password
    * simple_form

Some super important stuff today. Almost all sites require signing up and signing in so this lesson is vital. It is always cool to see how much fun it is to develop in Rails. Being able to run a secure signup with just a single method <code>has_secure_password</code> and throwing up a form with just a couple lines of code using <code>gem simple_form</code> makes using Rails such a joy. It's funny how grand it sounds when you think of writing code for logging in a user when all we're doing is something as trivial as setting <code>session[:user_id]</code>. A great resource on the topic of user sign up is <a href="https://www.railstutorial.org/book/modeling_users#cha-modeling_users" target="\_blank">Chapter 6 of Michael Hartl's Rails Tutorial</a>.

No homework today.

### Tuesday
<a href="https://github.com/tiy-hou-q2-2015-rails/day-27" target="\_blank">Challenge</a> today is super hard to finish in fifteen minutes. We basically have to create a super naive version of Twitter. The challenge calls for a single page with a list of all tweets in descending order so I started with <code>rails g controller Posts index</code>. Since it's single page, I set the root to the index. Index page on <code>localhost:3000</code> as expected. Tweets need to be stored somewhere so I went ahead with <code>rails g model Post content:text</code>. It's a microblog post so <code>validates length: { maximum: 142 }</code> in <code>Post.rb</code> before I forget. Now I need a way to tweet so let's throw a <code>form_for @post</code> together. I want to put it at the top index so let's make it more readable by writing the form in a partial and rendering it in index. Index is broken on localhost due to missing route as expected. Let's add the needed route for the form

    post 'posts' => 'posts#create'

Localhost now shows missing action posts#create as expected so let's add a create method in <code>posts_controller.rb</code>. Now index loads but there's no tweets showing. Better add <code>Post.all</code> to the index action and throw an ordered loop into the view. My <a href="https://github.com/joeypoon/iron_yard/tree/master/day-27/deep_thought" target="\_blank">solution</a>. I'm actually super proud that I finished within the time limit 😎.

Today's lecture is over two very awesome gems. Carrierwave and Kaminari. Carrierwave is for image uploading and Kaminari is for pagination. With all the amazing things we have been doing with gems, we now have a joke in class that at the end of the program Jesse will tell us that we can finish our entire app with a single <code>rails g</code> line.

<a href="https://github.com/tiy-hou-q2-2015-rails/day-27" target="\_blank">Homework</a> today is practicing what we've learned these past two days. We are to create an online photo album with login authentication required for uploading. We need a controller with a list of photos so let's start with <code>rails g controller Photos index</code>. Let's set the index to the root path and since we're in routes, add <code>'/admin' => 'photos#new', as: :new_photo</code>. We will need a place to store photos so lets <code>rails g model Photo name</code> and add Carrierwave to the gemfile and bundle. Carrierwave needs us to run a generator and mount the uploader in the model so let's do that first.

The photo index needs to be paginated so let's add Kaminari to the gemfile and bundle. Run the Kaminari generators and update our controller so that it displays our photos. We need a way to add photos so let's add a <code>form_tag</code> to our <code>new</code> action. Lastly, we need to secure the upload form so let's add a session controller, User model, and <code>has_secure_password</code>. I don't want new User signups so we'll leave out a users controller and simply create a user in seeds. Solution: <a href="https://joey-photo-uploader.herokuapp.com/" target="\_blank">site</a> \| <a href="https://github.com/joeypoon/iron_yard/tree/master/day-27/photo_uploader" target="\_blank">code</a>.

### Wednesday
Our daily <a href="https://github.com/tiy-hou-q2-2015-rails/day-28" target="\_blank">morning mental stretch</a> is to, given a database table, write validations for all fields, mount Carrierwave, and add relationships. There's an added hard mode to write a getter and setter method that returns price in dollars and stores dollars into cents. My <a href="https://github.com/joeypoon/iron_yard/blob/master/day-28/challenge.rb" target="\_blank">solution</a>.

Lecture for the day:

    * dotenv-rails
    * carrierwave-aws
    * acts_as_follower
    * acts_as_taggable_on

Carrierwave, while awesome, stores files locally. This causes problems when you deploy through Heroku and scale beyond one. The simple solution is carrierwave-aws. carrierwave-aws allows you to easily route your Carrierwave images into your S3 account. Amazon S3 requires an access ID and secret key in order to access. As lazy programmers we definitely don't want to type it out every time so we put it into a <code>.env</code> file and load it by using <code>gem dotenv-rails</code>. We can make sure to not commit it into git by adding it to gitignore. However, now Heroku is broken. Git now ignores the <code>.env</code> file so Heroku doesn't get a copy. Unfortunately, we have to manually add the keys to <code>Heroku config:set</code>. On the bright side, it's not too troublesome.

acts_as_follower is basically a gem that simplifies the more complex challenge of allowing an object to follow another object. acts_as_taggable_on is the same but for creating category tags.

<a href="https://github.com/tiy-hou-q2-2015-rails/day-28" target="\_blank">Homework</a> is to upgrade yesterday's homework to use S3 for image storage and add image tagging. Solution: <a href="http://joey-photo-uploader.herokuapp.com/" target="\_blank">site</a> \| <a href="https://github.com/joeypoon/iron_yard/tree/master/day-27/photo_uploader" target="\_blank">code</a>. Basically it's integrating carrierwave-aws, dotenv, Heroku environment variables, and acts_as_taggable_on with yesterday's homework.

### Thursday
Our challenge today takes on the familiar form of tests. We are to write code to make these <a href="https://github.com/tiy-hou-q2-2015-rails/day-29/blob/master/caffeine/caffeine_tests.rb" target="\_blank">tests</a> pass. The only weird part about the challenge was getting the coffee to return empty after 3 drinks. I decided to do a 0 to 1 scale so subtracting .33 * 3 wasn't quite 0. I ended up doing an ugly if statement to set the coffee to 0. My <a href="https://github.com/joeypoon/iron_yard/blob/master/day-28/challenge.rb" target="\_blank">solution</a>. Jesse's solution used a scale of 0 to 99 which I find to be more elegant.

Today's lecture is just review. Our <a href="https://github.com/tiy-hou-q2-2015-rails/week-6-lab" target="\_blank">lab</a> this week is to recreate Twitter. My solution: <a href="https://joey-flatter.herokuapp.com" target="\_blank">site</a> \| <a href="https://github.com/joeypoon/flatter" target="\_blank">code</a>. I apologize for not being very descriptive with my thought process for the lab, I'm pretty tired right now but I did leave a nice commit trail 😀.

### Friday
Our guest speaker today is Mohammad Azam, senior mobile dev at blinds.com. He shared some cool knowledge of iBeacons with us. He also showed us an app he has been working on that notifies you when your luggage has arrived at the terminal. I know I'd pay money for that. Today is also the official half-way point of our program. We celebrated with some BBQ for lunch. Yum yum.

### Other Things
My classmates asked me a very interesting question this week - is The Iron Yard worth the money I put into it? This may seem like a strange question coming from someone else who is also currently attending TIY so let me provide some context. TIY is a 0 to 60 program. This means that they have the expectation that you have zero programming knowledge at the start of the bootcamp. There are other types of programming bootcamps. I believe Hack Reactor advertises itself as a 20 to 120 program, for example. I didn't come into TIY at zero. I had been teaching myself programming for about a year by the time I started Rails engineering at The Iron Yard. I certainly wasn't anything more than a novice and I certainly wasn't good enough for a junior dev position but my time in the program so far definitely has not been too head-banging.

So back to my classmates' question. Is TIY worth the price for me? Or perhaps more generally, is TIY worth the price for someone who isn't starting at zero? 100% yes. While I can't deny that I probably would have been a better fit at something like the Hack Reactor, I have no regrets with choosing TIY's program. The fact is that while I'm not banging my head, I am solidifying my programming ability. Things that worked but I had no understanding of are now making sense. Things that took hours to build or debug, now only take minutes. The direction I have received from Jesse alone has made my time at TIY invaluable to me. I certainly would not have reached my current level so soon without TIY. Unless you are already junior dev level (then you don't need a bootcamp at all!), you will most certainly get your money's worth at The Iron Yard.

As you've probably noticed, I wrote out my thought process a little more for some of the challenges and assignments. I unfortunately didn't have time to do all of them but let me know what you think. Is it boring? Too many words? Interesting? Tweet me <a href="https://twitter.com/joeyfpoon" target="\_blank">@joeyfpoon</a>.

Also new family member is settling right in:
<img src="{{ site.baseurl }}/img/tiger.jpg" alt="tiger">
