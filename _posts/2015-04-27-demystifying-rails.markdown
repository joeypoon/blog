---
layout:     post
title:      "Demystifying Rails"
subtitle:   ""
date:       2015-04-27 03:32:24 +0000
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---

It's been a busy week at work. I mean, look at how sad this <a href="https://github.com/joeypoon">past week</a> was. Fortunately, I was able to get my code on this weekend. I took a slight detour from Rails previously to brush up on my Ruby and am now back at Rails. It is so much easier to understand Rails when you know some Ruby. Things are definitely sticking better this time around. Some awesome things I was able to learn this weekend:

<h3>Sass</h3>
Okay, this isn't specifically Rails but it's still awesome. Syntactically awesome stylesheets could not be a more appropriate name. Being so use to nesting and variables, it definitely felt like hassle at times trying to write plain css. Yay for Sass!

<h3>Partials</h3>
There is just something so satisfying about breaking down chunky looking code into smaller chunks. Partials are welcome in my code any day. Hopefully I can commit another naming convention to memory (chanting: \_partial \_partial \_partial).

<h3>Paths</h3>
<pre>get 'some_page' =&gt; 'controller#action'</pre>
I've been wondering for a while how to customize urls so learning about paths in Rails was happy times.

<h3>Asset Pipeline</h3>
<pre>rails new my_app</pre> creates so many things that understanding where things were took a while. Learning about the asset pipeline was definitely a relief. Having the manifest include everything in the directory is so convenient.

<h3>Tests</h3>
I have been trying to write <a href="{{ site.baseurl }}/on-the-road-to-testing.html">my own tests</a> and doing a <a href="https://github.com/joeypoon/Summer_FA_Calculator">terrible job</a>. Rails makes testing so much easier. I'm just starting to grasp the amazing things I can do with
<pre>rake test</pre>
but I definitely feel like I'm getting closer to TDD. Thank you
<pre>validates</pre>
and
<pre>assert</pre>

<h3>Regex</h3>
Okay, I honestly still don't get regex. I've had to use regex in a couple of solutions before but I was able to find a suitable answer online so I didn't bother learning how to write one on my own. I'm going to do it this time. I promise!

What a great weekend :).
