---
layout: post
title: "Useful Tools to Test the Responsiveness of Your Site"
description: ""
category: tips
tags: [HTML5, CSS3]
---
{% include JB/setup %}

Hello everyone, 

One important part of the web developer's job nowadays is assure the responsiveness of the pages that he is creating. It is impossible to start a project which <a href="http://speckyboy.com/2013/01/17/the-evolution-of-responsive-web-design-responsivity-analysis/">responsivity analysis</a> is not a mandatory requirement, the therm <a href="http://www.uxmatters.com/mt/archives/2012/03/mobile-first-what-does-it-mean.php">Mobile First</a> is a topic that every software developer should be comfortable  a exhausted discussed <a href="http://www.webinsation.com/why-should-i-design-for-mobile-first/">here</a> and <a href="http://www.wearejh.com/design/benefits-of-a-mobile-first-approach/">here</a> by instance.
But even responsive development being not exactly a new trend, responsiveness test still being a <a href="http://stream1.gifsoup.com/view/656679/pitfall-o.gif" target="_blank">challenging</a> task once is impossible for a developer (even for a company) to have all devices to perform his tests and simulate specific scenarios for each case.
In this article I'll show the tools I normally use (does not mean that these are the best, just that I am familiar with). In my opinion, the most important factor to decide a tool amongst others is how much productive you are with it, in my case includes avoid repetitive work, prevents you wasting too much time to find their resources and to understand how it works and obviously, give a decent emulation of the device you're aiming to.

I classified the tools in two sections, first those that you can use during the development time, that is, tools embedded in browsers toward get a notion of your design while it is being created, the second part consists of tools to check the overall result of your work after it has been deployed. Things like layouts, font-sizes, distances and menus are extremely sensibles for differents environments so it is really worth to exhaustly test them all in at least the most common environments.

### During Implementation

Major moderns browsers have their ours developer tools. Although it is a embedded feature, they are highly mature with all that is needed to develop a page fully responsive together with <a href="http://www.w3schools.com/cssref/css3_pr_mediaquery.asp" target="_blank">Media Queries</a> which you can emulate different types of screen. Personally, I use <a href="https://www.google.com/chrome/browser/desktop/" target="_blank">Google Chrome</a> for development because I use some of his features such as CPU Profile, Network analysis and memory leaks (if you are not familiar with those resources in Chrome, attend the free course <a href="https://www.codeschool.com/courses/discover-devtools">Discover DevTools</a>). However, the Safari and Firefox version will be described here. Let's see each one at a glance:

### Google Chrome

It is very easy to emulate a device in Google Chrome, first all open the 'Developer Tools' in View -> Developer -> Developer Tools then you will notice a cell phone image in the upper left side of the tool bar as you can see in the image behind.

### Mozilla Firefox

### Safari


### After Deployment

The 'After Deployment' tools are important for the overall look, to catch specific details that are hard to be tracked during development when you are most occupied trying to getting your page into details. There are some online services that simulate the access to your site from different devices and in all of them you need to have your pages published in a public URL, unfortunatelly you can't point to your localhost. I will the two services that I like most to work with, the first is <a href="http://responsive.is/typecast.com" target="_blank">Responsive.is</a>, a lean and direct tool to test the responsiveness of your pages. All you have to do is 

<a href="http://ami.responsivedesign.is">Responsive Design</a>



<script type="text/javascript" src="/js/main.js"></script>