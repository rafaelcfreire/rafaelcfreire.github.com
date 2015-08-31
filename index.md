---
layout: page
title: Welcome
tagline:
---
{% include JB/setup %}

<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-56746688-1', 'auto');
  ga('send', 'pageview');

</script>

Welcome to Rafael Freire's Tech Blog. Here you will find some of my thoughts about software development. I'll try to update it always as possible with what I'm currently studying, reviews about books I've read or thar I'm reading and some cool stuff I find over the internet. Feel free to share your opinion in our posts. ;).



<div class="secondaryContent">
	<span class="postSection">
		<header class="PostsHeader"><h4>Recent Posts</h4></header>
		<ul>
		    <h5><li><a href="{% post_url 2015-06-22-the-books-that-influenced-my-career %}">The Books That Influenced My Career - 22 Jun 2015</a></li>
		    <li><a href="{% post_url 2015-02-24-useful-tools-to-test-the-responsiveness-of-your-site %}">Useful Tools to Test the Responsiveness of Your Site - 24 Feb 2015</a></li>
		    <li><a href="{% post_url 2014-11-12-free-ebook---modern-web-essentials-using-javascript-and-html5 %}">Free EBook: Modern Web Essentials Using JavaScript and HTML5 - 12 Nov 2014</a></li>
		    <li><a href="{% post_url 2014-10-30-Where-to-start-with-functional-programming %}">Where to Start With Functional Programming? - 30 Oct 2014</a></li>
		    <li><a href="{% post_url 2014-10-11-javascripts-this-nightmare %}">Javascript's this nightmare - 11 Oct 2014</a></li>
		    </h5>
		</ul>
		<!--
		<ul>
			{% for post in site.posts %}
		<li>
			
			<h6><a href="{% post_url 2015-02-24-useful-tools-to-test-the-responsiveness-of-your-site %}">{{ post.title }} - {{ post.date | date_to_string }}</a>
</h6>
		</li>
			{% endfor %}
		</ul> -->
	</span>

	<span class="quotesSection">
		<p>
			<script type="text/javascript" src="http://www.brainyquote.com/link/quotebr.js"></script>
			<small><i><a href="http://www.brainyquote.com/quotes_of_the_day.html" target="_blank">more Quotes</a></i></small>
		</p>
	</span>
</div>

<script type="text/javascript" src="/js/main.js"></script>
<link rel="stylesheet" type="text/css" href="/css/styles.css">