---
layout:     post
title:      "Love and Hate"
subtitle:   ""
date:       2015-02-13 21:51:30
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---

<p>Programming is such a love and hate relationship.  When I create a solution to a problem that works, it is the most amazing feeling in the world.  On the other hand, when I spend days trying to figure out what's wrong with my code I just want to rip someone's hair out (No, not my own, I like having hair).  Recently I was trying to create a solution to check if a sudoku answer is correct.  I decided to check each row and column independently and came up with this for my column checker:</p>

<img class="alignnone" src="http://temp.nickydisla.com/temp/wp-content/uploads/2015/05/sudoku_solution.png" alt="joey poon sudoku code">

<p>I spent an undisclosed (It's too embarrassing) amount of time writing and rewriting this function only to continuously come up with a near exact duplicate.  Then it hit me.  I forgot to reset my j index after each loop.  I crossed my fingers and prayed as I tested my solution.  I spent the rest of the day being bipolar with bouts of joy countered with equal bouts of shame.  I love how you make me feel programming.  No, I hate you.  Just kidding, I'm sorry programming.  Please be my Valentine.</p>
<pre>
     /-_-\
    /  /  \
  /  /    \
  \  \    /
   \__\__/
      \\
      -\\    ____
        \\  /   /
  ____   \\/___/
  \   \ -//
   \___\//-
      -//
       \\
       //
      //-
    -//
    //
    \\
     \\
 </pre>
(Flower from <a href="http://www.asciiworld.com/index.html" target="_blank">http://www.asciiworld.com/index.html</a>)
