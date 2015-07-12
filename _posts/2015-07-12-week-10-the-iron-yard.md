---
layout:     post
title:      "Week 10 The Iron Yard"
subtitle:   "The search and more Rails"
date:       2015-07-12
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---
### The Search Begins
With only 2 weeks remaining, job searching is naturally becoming a larger part of day-to-day life. I had my first interviews this week and boy did I screw up. I'm not sure what happened but I completely blanked out at a simple question like 'describe your rails experience.' Fortunately this served as a good wake up call as I performed much better subsequently.

I also had my first whiteboarding experience. It was both fun and terrifying. It's great in the sense I get to do what I love during an interview and secondly, I am no longer judged by my resume but my actual coding ability. It is terrifying in the fact that you're put on the spot without your dev tools. I actually blanked out for what felt like an eternity for one of the whiteboard problems. Practice more Ruby before you interview.

### Project Update
Since lectures are over and our remaining time is self-paced final projects, I won't be going over the days separately. As my project is actually quite large in scope, I'm working in a team of 3. If you're thinking about attending Iron Yard, I highly recommend doing a team project for your final project as well. My reasoning is that one, you can have a larger and more impressive project. Second, it is great practice for an agile development environment.

I'm feeling a lot better about our project this week. Last week I still wasn't sure how far we would get in terms of going mobile. This week, we've gotten a lot of our views up and running on mobile and I can definitely see us finishing a demo ready product by July 24.

### Coding vs. Critical Thinking
An interesting dynamic I saw with my back-end is the planning time versus the coding time. This reminds me of an article <a href="http://blog.texmexconsulting.com/clients-do-not-pay-you-for-the-code/" target="\_blank">Jesse wrote about writing 10 lines of code for $1000</a>. I have data and I know what I want to do with it. Before I can write code to tell the computer what I want it to do with the data, I need to structure the data. How do I break down the relationships? What data do I put in which table? These are questions that I have to whiteboard out and spend a significant time thinking about it. The result? Hours of critical thinking and far less than a hundred lines of code. Coding certainly doesn't happen the way movies portray.

### More Rails
Even though I'm taking a Rails course, I've talked more about JavaScript than I have about Rails in my last couple of posts. With interviews happening, I'm realizing how much more there is to learn about Rails. This means that I have been doing lots and lots more reading.

<code>has_many :through</code> vs. <code>has_and_belongs_to_many</code><br>
Throughout the course, we've basically been fine with <code>belongs_to</code> and <code>has_many</code>. Occasionally I've had to bust out the <code>has_and_belongs_to_many</code> but nothing super complicated. Apparently Rails also has a <code>has_many :through</code> and the like. This allows you to have an intermediate table between relationships.

<code>dependent: :destroy</code><br>
I didn't realize that destroying a model didn't automatically destroy its dependents, I'm so spoiled. Good thing Rails makes it easy to implement.

<code>add_index :table, :foreign_key</code><br>
This one I admit I'm having trouble seeing the value. If I have a relationship between two models using <code>has_many</code> and <code>belongs_to</code>, there is already a <code>foreign_key</code> like <code>user_id</code> which links the models together. What value does adding an index of that same <code>foreign_key</code> contribute? I'll need to dig more into databases for this one.

<code>scope :name, where(attribute: value)</code><br>
I love this one. Jesse very briefly showed this to me when he was helping me with one of my projects but I had since forgotten about it. Being able to define a named scope makes your controller so much cleaner. Nothing is sexier than clean code.

<code>before_save</code><br>
Callbacks allow you to run code based on the life cycle of an object. How did I not use these before?

### The Talks
We have two awesome talks this week. Brian gave us a job talk. If you've looked at dev job postings, you know how terrible most of them are. Brian shared with us how to interpret the postings into what they're really looking and how to target your cover letter. Admittedly, I wish this talk took place before I started apply for jobs :sadface:

Our second equally awesome talk is from Hesam Panahi from Red Labs, UH's accelerator arm. For my team, Hesam is coming at a perfect time because we're very heavily considering a startup. To be able to get an inside look at Houston's accelerators is exciting.
