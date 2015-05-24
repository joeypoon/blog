---
layout:     post
title:      "Week 3 The Iron Yard"
subtitle:   ""
date:       2015-05-24
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---

###Long Weekend!
It's memorial weekend, yay! Except, I haven't had a weekend since I started TIY. It doesn't seem like I'll have one anytime soon either. I spent all of yesterday trying to migrate out of WordPress. I fixed up my <a href="http://joeypoon.com">portfolio</a> and moved it to Github pages. It loads so much faster now that it brings a tear to my eyes. I was actually planning to write this blog post yesterday but I ended up spending literally an entire day trying to configure my DNS to get my custom domain working. In the end, I was wasting my time because the settings were fine, my hosting provider was just having some issues. Wonderful timing. If you've been following my blog, you'll notice that it looks a little different now too. That's because I am now blogging with Jekyll and Atom :).
<pre>nerd_level++</pre>

###Monday
<a href="https://github.com/joeypoon/iron_yard/blob/master/day-11/triangle_challenge.rb">Challenge</a> today is to determine the type of a triangle given the length of its 3 sides. Starting today, our challenges are supposed to be in a new form. We're given tests and we write code to make it green. I like this change as it forces us to get use to testing. Honestly, this challenge was a little tough for me. I'm not sure why, but I have been having a strange aversion to if/elsif trees. I kept trying to find some elegant loop solution. After wasting enough time, I still ended up using a bunch of if statements (original solution is commented out). Funny enough, my original solution used more if statements and the logic behind the solution is fuzzy at best. I'll need to work on that weird mentality of mine. Red, Green, Refactor -- not Red, Refactor, Green.

Lecture today is over testing and some HTML/CSS. Jesse walked us through creating a bowling score calculator with TDD. It is interesting to see how even someone as experienced as Jesse backtracks with solutions. While I like the idea of testing, I don't think I'll be as zealous about testing every single method. To me, methods are to break things down into manageable parts. If these parts are small enough, it feels almost pointless to test the smaller methods. I also don't like the idea of not looking at the problem as a whole and just letting TDD guide you. I find that doing so will sometimes waste time by forcing you to rewrite previous solutions. I do like that TDD forces you to write better(?) code but at the same time I think that looking at the problem at a higher-level can help prevent some rewriting down the road (I have opinions, please don't grab the pitchforks).

Homework is additional review on testing. We had to write code to pass the <a href="https://github.com/joeypoon/iron_yard/tree/master/day-11">bob_test</a>.

###Tuesday
Our first HTML/CSS <a href="https://github.com/tiy-hou-q2-2015-rails/day-12">challenge</a>. The challenge itself is pretty simple, just some practice with HTML and CSS. <a href="http://codepen.io/joeypoon/pen/XbKOmg">Challenge result</a>.

Today's lecture is a more in-depth look at HTML and CSS. We were shown the hover element, using background-image + cover, how to tint an image, and SCSS. Not everyone submitted last week's <a href="https://github.com/joeypoon/BlackJack">BlackJack lab assignment</a> so Jesse didn't assign any homework so that everyone could have some breathing room.

###Wednesday
Today's <a href="https://github.com/tiy-hou-q2-2015-rails/day-13">challenge</a> is to recreate a chess board with pure HTML and CSS. No ERB 😢. This challenge definitely made a lot of use out of copy paste. I didn't get to <a href="http://codepen.io/joeypoon/pen/VLKvda">finish</a> within the time-limit.

The challenge led perfectly into our lecture topic: Middleman and ERB. (E)mbedded (R)u(B)y allows you to use Ruby within your html file. This is awesome because you no longer need to copy paste 64 divs to make a chess board, just loop. Middleman is interesting because it's so similar to Rails. Seems almost like Rails integrated Middleman? Asset pipeline and Middleman build is awesome. Use ERB to create your page and just use Middleman build to generate the HTML. We also did review of our lab today. I'm a little guilty of zoning out a little during today's review but in my defense, I did a lot of reading on Jekyll and Github pages. It's what inspired me to migrate my blog 😀.

Homework today is to create a simple website for yourself. It was left as an optional assignment since our review ran a little long. Being inspired by my Jekyll and Github pages reading, I spent pretty much the entire night trying to make a decent looking website. Deploying to Github pages is ridiculously easy with Jekyll. Middleman is pretty easy too with Middleman deploy but Jekyll still wins in ease of use. It makes sense to teach Middleman over Jekyll in class, however, as it provides a perfect entry point for Rails. I probably should have taken a screenshot of how my site looked but I forgot, sorry 😶.

###Thursday
Data parsing is today's <a href="https://github.com/joeypoon/iron_yard/tree/master/day-14">challenge</a>. We have to parse through the Gettysburg address and display the number of times each word appeared, minus common words like "the". My <a href="https://github.com/joeypoon/iron_yard/tree/master/day-14">solution</a>.

I got excited because I thought it might lead into a little machine learning. It didn't 😞. It did lead into cool things you could do with .inject though. I don't think anyone in class used .inject in their solution so that was interesting to see. The major chunk of today's lecture was over Git and Github. Jesse went over the basic commands:

    $ git init
    $ git add .
    $ git commit -m "Message"
    $ git remote add origin url
    $ git push -u origin master

He also showed us what to do if we get stuck in vim or get a merge error. It definitely took me a long time to figure out what was going on the first time I had a merge error or when I forgot my -m so that was useful to learn.

<a href="https://github.com/tiy-hou-q2-2015-rails/week-3-lab">Lab</a> this week is to recreate a webpage using HTML/CSS and deploy to Github pages using Middleman. Hard-mode includes making the page responsive (No UI frameworks allowed).

###Friday
This week's guest speaker is <a href="https://twitter.com/RookieOne">Jonathan Birkholz</a>. JB runs the Houston-JS meetup group and is an all-around outstanding guy. He gave us tons of encouragement and really drove home the point that as developers, we never stop learning. There are always new technologies being invented and new technologies to learn.

I'm slacking a little on this week's lab. I haven't even looked at it yet. I'm way too absorbed in trying to get a decent looking portfolio.

###Confessions
I was having some weird moral guilt about <a href="http://joeypoon.com/blog/2015/05/18/week-2-the-iron-yard-and-my-first-hackathon/">building Houston.Vote</a> with WordPress. Near the end of the week, I came to terms that this was a silly thing to feel guilty about. We initially tried to use Rails but we decided that we didn't know it well enough to finish the product within 24 hours. We were 2 weeks into TIY and we're still learning. So there you have it. We used WordPress. We still got a working <a href="http://Houston.vote">website</a> and I am proud of what we did in 24 hours.

I bought a theme for my <a href="http://joeypoon.com">portfolio</a>. I actually don't feel guilty about this. The fact is that I'm not a designer, nor do I seek to be. I want to develop back-end logic and understand how to do front-end. I could spend days trying to make a decent looking website or I could spend 10 dollars to buy a way better looking theme. I actually did end up spending a ton of time trying to get the theme to work properly but I'd attribute that to my lack of understanding of Jekyll/Middleman. It was a good learning experience on using Jekyll/Middleman so I'm not unhappy about the time I spent. I know now that if I have to apply another theme, I could do it quickly.

###Other Stuff
I'm still having some trouble getting redirects to work properly so unfortunately some links for my blog might be broken but I'll hopefully have it working soon™. I really need to get started on my lab. I was suppose to have my blog fully migrated midday yesterday but I'm still not completely done. Better hop to it.
<img src="http://temp.nickydisla.com/temp/wp-content/uploads/2015/05/goat_flip.gif">
