---
layout: post
title: "Using Underscore.js Effectively"
description: ""
category: 
tags: []
---
{% include JB/setup %}

<div style="margin-bottom: 1.5em;">
	<div>
		<a href="https://twitter.com/share" class="twitter-share-button" style="vertical-align: bottom">Tweet</a>
	</div>
	<div>
		<span class="fb-share-button" data-href="http://rafaelcfreire.github.io/2015/03/28/using-underscorejs-effectively/" data-layout="button"></span>
	</div>
</div>

Hello readers,

If you have read any of my previous posts probably you noticed that I really appreciate <a href="http://en.wikipedia.org/wiki/Functional_programming" target="_blank">Functional Programming</a>. Personally, I have been working with Java for the last 7 years and dealt millions of poor written code in many ways, even that there are a variety of tools to increase the leverage and quality of code but in my perspective it is not the definitive shift. During this time I have maintained code from junior to experienced developers, some of them people that I know from heart that priorizes quality but even so, there are a plenty of scaring bugs that probably were implemented in a friday after midnight with no test at all to be released at saturday morning in the production environment.

As described in my previous post <a href="http://rafaelcfreire.github.io/2014/10/30/Where-to-start-with-functional-programming/">Where to Start With Functional Programming?</a>, I think that functional programming is a splendid and stable solution for <a href="http://programmers.stackexchange.com/questions/155488/ive-inherited-200k-lines-of-spaghetti-code-what-now" target="_blank">bad spaghetti code</a>. The sluggish <a href="https://www.jcp.org/en/home/index">Java Community process</a> has finally discovered it in his Java 7 release but in many other languages it has been around since their foundations. In Javascript functions has always been at the core of the language, probably you have already heard the term that functions are 'first class citizen' in many languages and in JS in each new edition of the language it becomes more and more flexible. The flexibility in Javascript permits you even to not use it in a functional way and here is where Underscore.js takes action. Some of the best way to take real advantage of Functional code is using <a href="http://underscorejs.org/">Underscore.js</a> library.

Even those javascript developers that aren't familiar with Underscore.js probably have already used it indireclty because provides features for other popular libraries like <a href="http://backbonejs.org/" target="_blank">JQuery</a> and <a href="http://backbonejs.org/" target="_blank">Backbone</a>. 

<script type="text/javascript" src="/js/main.js"></script>