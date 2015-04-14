---
layout: post
title: "What is Reactive Programming ?"
description: ""
category: 
tags: [languages, scala, functional]
---
{% include JB/setup %}

  
Hi there,

As I mentioned in a previous post, currently I am studying <a href="http://www.scala-lang.org" target="_blank">Scala language</a> motivated by the course <a href="https://www.coursera.org/course/progfun">Functional Programming Principles in Scala</a> where I could understand some principles of FP that I already wrote about it [here](http://rafaelcfreire.github.io/2014/10/30/Where-to-start-with-functional-programming/). Recently I had the opportunity to be part of the review team of the book <a href="http://www.manning.com/blackheath/">Functional Reactive Program</a> (notice that it is in MEAP yet, so the name can change until his release) and partialy read the book written by <a href="http://blog.reactiveprogramming.org/">Stephen Blackheat</a>. Those references gave me an overview of what is and when and why to use Reactive Programming, an approach for a classic problem for systems when it trends to become complex event handlers 



Observer pattern
CallBack Hell


What is reactive programming?
A composable/modular way to code event-driven logic


Reactive Manifesto
In my readings about FP the term Reactive Programming were always recurrent in Scala docs or in other web resources. But what is it? The main resource related to the subject is the [Reactive Manifesto](http://www.reactivemanifesto.org) where there are some parts that defines the aim of Reactive Programming like "These systems are more robust, more resilient, more flexible and better positioned to meet modern demands.", okay, these adjectives are meaningless if we don't understand in depth the 4 principles of reactive systems according the above manifesto, that are: 

- Message Driven: Based in asynchronous communication through messages, the <a href="http://www.enterpriseintegrationpatterns.com/MessagingComponentsIntro.html" target="_blank">Message Driven Communication</a> lies on the principle of loose coupling that is essentially important for modern applications. 
- Elastic:
- Resilient:
- Responsive:

Reactive in practice - BaconJS and Sodium


Netflix JavaScript Talks - Async JavaScript with Reactive Extensions
https://www.youtube.com/watch?v=FAZJsxcykPs

<script type="text/javascript" src="/js/main.js"></script>