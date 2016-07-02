---
layout:     post
title:      "Week 5 The Iron Yard"
subtitle:   "Databases, tables, and PostgreSQL"
date:       2015-06-07
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---
### Databases, oh my
It's finally time for databases! I have been waiting for this moment. All of my ideas require databases(what doesn't nowadays?) so I'm super excited to build some awesome database backed projects. Let's jump right into it.

### Monday
Our first <a href="https://github.com/tiy-hou-q2-2015-rails/day-21">challenge</a> of the week is a review on Rails routes. We have to define a routes file that produced a predefined set of urls. My solution <a href="https://github.com/joeypoon/iron_yard/blob/master/day-21/challenge/config/routes.rb">here</a>. Funny thing about the challenge is that everyone in class did a full Rails app when apparently Jesse only wanted a routes file.

Lecture this week begins with an intro to postgresql and using psql. We went over the most common queries:

    create table table_name (column data_type, column2 data_type);
    insert into table (column, column2) values (value1, value2);
    select * from table where column = 'value';
    delete from table where column = 'value';
    drop table table_name;

Jesse shared with us that this is the first time TIY Houston Rails Engineering is getting lectured over SQL queries. Some students from past cohorts told them that they wished that they had more SQL knowledge. It's super cool to see them take feedback seriously and I'm glad that I can better understand what calling <code>Model.all</code> in Rails actually does in the background.

Homework today is completing <a href="http://www.sqlcourse.com">sqlcourse</a> and creating a script to accomplish <a href="https://github.com/tiy-hou-q2-2015-rails/day-21">this</a>. My solution is <a href="https://github.com/joeypoon/iron_yard/blob/master/day-21/sql_assignment.txt">here</a>. I'll note that it's pretty important to look at your classmates' solutions after completing it yourself. You'll sometimes discover better ways to solve the problem. In this case, I learned that I can insert all my cities in the same statement. This would have saved me quite a number of lines.

### Tuesday
Tuesday <a href="https://github.com/tiy-hou-q2-2015-rails/day-22">challenge</a> is to create a table for storing panda information. After creating the table, we have to write queries that will pull the largest male and largest female panda. My solution <a href="https://github.com/joeypoon/iron_yard/blob/master/day-22/pandas.txt">here</a>.

Lecture today is pretty heavy. We covered multiple tables and joins, ActiveRecord, and migrations. I think now is a good time to mention how important it is to attend meetups even if you don't fully understand the topic at hand. Last month's Ruby meetup had Derek Anderson introducing us to his Rails tool <a href="https://github.com/keredson/ruby-db-evolve">db:evolve</a>. db:evolve allows you to update your tables by changing the schema directly. The basic premise is that it takes git diffs of the schema and updates the tables according to the differences. This method is way easier and, in my opinion, more intuitive than creating migrations. We hadn't even touched Rails when this meetup occurred so my knowledge of the topic at the time was limited at best. Looking back at it, I can now understand how awesome this tool is.

Homework is to create a <a href="https://github.com/tiy-hou-q2-2015-rails/day-22">blog</a> (no scaffolding, of course). It's a basic blog so all it needs is a <code>:title</code> and <code>:body</code>. We need to populate the blog with seed data and it should have a working index action and show action. As an addition, we have to add a <code>published_on:date</code> column using a migration and only display posts that are published. My <a href="https://github.com/joeypoon/iron_yard/tree/c52e656019ab2c395d152f7544fd5f59b4bbbb4d/day-22/blog">solution</a>.

### Wednesday
<a href="https://github.com/tiy-hou-q2-2015-rails/day-23">Challenge</a> for the day is to create a migration to add a column to a table and another migration to remove a column. The challenge itself wasn't too difficult, but we did get to learn how to deal with typos and such. You can't just change a migration file that has already been run since Rails will think that it has already run and won't make apply the changes. You instead have to <code>db:migrate:down VERSION=version_number</code> first. My solution <a href="https://github.com/joeypoon/iron_yard/tree/master/day-23/day-23/pins/db/migrate">here</a>.

We covered forms and validations in lecture today. Jesse first made a form using only HTML, then he used the <code>form_tag</code>, then he used <code>form_for @model</code>. It's pretty interesting to see the different methods as it helps me visualize exactly what <code>form_for</code> does. I have actually used <code>form_for</code> in conjunction with a <code>scaffold</code> in a <a href="http://joeypoon.com/blog/working-efficiently.html">project</a> before and had trouble making it work without scaffold. Now I can see that I simply didn't set up my RESTful actions properly, it's actually quite embarrassing when I look back at it. For validations, we covered a basic presence and numericality assertion. It's pretty cool that you can validate input with just a single line. I remember when I <a href="https://github.com/joeypoon/Summer_FA_Calculator">manually</a> did input validations.

Our <a href="https://github.com/tiy-hou-q2-2015-rails/day-23">homework</a> today is an add-on to <a href="https://github.com/tiy-hou-q2-2015-rails/day-22">yesterday's homework</a>. We have to add the ability to create posts, edit posts, and validate all fields. My <a href="https://github.com/joeypoon/iron_yard/tree/master/day-22/blog">solution</a>.

### Thursday
Sing it with me, lab day~~~lab day~~~. It's always so exciting to see what awesome project we get to build over the weekend. Anyways, morning <a href="https://github.com/tiy-hou-q2-2015-rails/day-24">challenge</a> is to write methods into the Buyer model to make the tests pass. This is our first time dealing with tests within a Rails environment so it was actually pretty difficult. I was able to get write a naive solution for checking age but I kept having issues getting the tests to pass. Eventually I noticed that the methods tested end in ? so they should return a boolean. Given our heavy use of assert_equal in the past, my brain automatically thought that the methods should return the string at the end of each test. Silly mistake. My solution <a href="https://github.com/joeypoon/iron_yard/blob/master/day-24/validity/app/models/buyer.rb">here</a>.

Our last lecture of the week is over table relationships, Heroku, and flash messages. Rails again shows its awesomeness by making relationships easy to manage with:

    belongs_to
    has_many

It's funny how easy Heroku seems when someone walks you through it. I can't count the amount of time it took me to deploy my first app on my own.

Time for weekend fun! <a href="https://github.com/tiy-hou-q2-2015-rails/week-5-lab">Lab this week</a> is to recreate reddit.

    Normal mode:
    * Index of user posted links that are ranked by votes
    * Votes increment when a link is clicked
    * No downvotes

    Hard mode:
    * Downvotes
    * Add relationships between User and Posts
    * Allow selection of User when creating a post
    * Validate link uniqueness

    Nightmare mode:
    * Add User sign-in
    * Add testing

Something I noticed when doing this project is that I tend to drift into multiple features at the same time. This leaves me with multiple half finished features and I get lost in thought. I've decided to start using Trello to write out features to add. I then work on them one at a time and move them to done as I go. It also helps me not forget features that I want to add. It's working out pretty well so far.

One technical problem I had with this project is trying to integrate <code>gem devise</code> into my project. I found it pretty hard to implement when I didn't understand what it was doing and I honestly wasn't very fond of its documentation. I ended up scrapping devise and at the same time, blowing up my project. Not knowing what devise installed made it even harder to remove all its pieces. Thank goodness for git, I just reverted back to my last working version. I still have quite a few features that I want to add to make it more reddit-like but functionality-wise, nightmare mode <a href="https://github.com/joeypoon/reddit_clone">solution</a> is complete (<code>has_secure_password</code> is awesome). Here's the <a href="https://joey-reddit-clone.herokuapp.com">live version</a>.

### Friday
Our guest for the week is Amanda Shih from OpenStax. Amanda is super active around the Houston tech community and showed us some awesome JS robotics. She actually hooked up a robot that we could control through her server. She then walked us through the setup process. It's pretty cool to see how simple it is to do something like get a robot to move with some of the tools that are already available.

Our projects are getting pretty awesome. To be able to build something like Reddit is amazing. To think that just over a month ago we wrote our first loop, it is amazing the amount of ground we have covered in such a short time. Time to get back to work 😀. See you all next week.
