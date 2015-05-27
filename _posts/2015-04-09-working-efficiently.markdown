---
layout:     post
title:      "Working Efficiently"
subtitle:   ""
date:       2015-04-09 00:37:46
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---

<p>I am lazy. I had a huge stack of applications to process at work (I work in higher education) today. It didn't help that most of the applications had to be done manually. Faced with such a repetitive task, I did what any reasonable programming addict would do: write a program to do my job. I spent the next hour writing the basic form of the program and another hour just tweaking. I was pretty happy with the result:</p>

<a href="{{ site.baseurl }}/img/summer-fa-calc-2.png"><img class="alignnone" src="{{ site.baseurl }}/img/summer-fa-calc-2.png" alt="joey-poon-summer-fa-calc"></a>

<p>And like every other program, disaster strikes. Negative numbers, explosions, Michael Bay, wait... Anyways, I completely neglected to account for each students' EFC when generating awards. Oh no! Okay, I lie. I didn't neglect it, I didn't want to do it because it's calculated based on this <a href="http://ifap.ed.gov/dpcletters/attachments/20142015PellGrantPaymentandDisbursementSchedules.pdf" >monstrosity</a>. Fortunately, math saves the day! I was able to find a pattern in the chart and make a solution like so:</p>

<a href="{{ site.baseurl }}/img/summer-fa-calc.png" ><img class="alignnone" src="{{ site.baseurl }}/img/summer-fa-calc.png" alt="joey-poon-summer-FA-calc"></a>

<p>It definitely still needs some tweaking and refactoring but that's not work ;). If you have to do this exact repetitive work, help yourself to the <a href="https://github.com/joeypoon/Summer_FA_Calculator">program</a>.</p>
