---
layout: post
title: "Where to Start With Functional Programming?"
description: ""
category: 
tags: [languages, scala, javascript, java 8, functional]
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

Hi all,

Nowadays it is very common to see people discussing the use of <a href="https://www.haskell.org/haskellwiki/Functional_programming" target="_blank">functional programming</a>, mostly of modern languages adopt some of his principles and seems that it is a new shift that will change the way you program, but definitely isn't. Functional programming has been around for a long time, the first functional language was <a href="http://www.princeton.edu/~achaney/tmve/wiki100k/docs/Lisp_(programming_language).html" target="_blank">LISP</a> back in 1959 and since then there are some misconceptions and  confusions about the concept of functional programming that leads to misuse of a very useful paradigm but that isn't a silver bullet. People with background in <a href="http://en.wikipedia.org/wiki/Imperative_programming" target="_blank">imperative programming</a> where the solution for an algorithm should be described step by step in a sequence of statements tends to feel love at first sight with functional programming due to the fact of write much less code to achieve the same results and ease of reading.

### Principles of Imperative Programming

To a better understand of Functional Programming let's see what are the principles of Imperative Programming, so we can have a trade between both. Basically Imperative Programming deals with:

- Modifying mutable variables
- Using assignments
- Control structures such as if-then-else, loops, breaks, continue, return

As mentioned by <a href="http://lampwww.epfl.ch/~odersky/" target="_blank">Martin Odersky</a> in <a href="https://class.coursera.org/progfun-2012-001" target="_blank">Functional Principles with Scala</a> the most common informal way to understand imperative programs is a <a href="http://www.c-jump.com/CIS77/CPU/InstrCycle/lecture.html" target="_blank">instruction sequences for a Von Neumann computer</a>. So, what's wrong here? The problem with Imperative Programming is his nature of state changes. Deal with huge imperative applications can be extremely improductive to be sustained once scaling is a big problem when shared mutable state is on the scene.

### What is Functional Programming?

One of the misconceptions that we can mention is that functional programming is a replacement for object oriented programming. Definitely NOT...repeat it to yourself 3 times. There is no contradiction with OO (<a href="http://scala-lang.org" target="_blank">Scala</a> use both for example), rather, you can use object oriented design with a functional implementation. Functional programming is a <a href="http://en.wikipedia.org/wiki/Programming_paradigm" target="_blank">paradigm</a> focused in how should be the structure of the implementation, so, instead of describing all the steps to perform an action ending in a low level and verbose code, functional is more concise, easier and expressive. I came from OOP with imperative background and right in my firsts experiments with FP in Scala i was really excited, imagine a language with wich you code as simple as reading? Now Java 8 has the <a href="http://www.oracle.com/webfolder/technetwork/tutorials/obe/java/Lambda-QuickStart/index.html" target="_blank">new syntax of Java 8 with Lambda expressions</a> which i just met but i always worked with Java's previous versions that everything is so <a href="http://en.wiktionary.org/wiki/verbose" target="_blank">verbose</a>, let's see a small example of iterating through a list.

{% highlight ruby %}
final List<BigDecimal> valores = Arrays.asList(new BigDecimal("70"), new BigDecimal("25"), new BigDecimal("55"), new BigDecimal("12"));

for(BigDecimal doubleValue : valores){
 System.out.println(doubleValue);
}
{% endhighlight %}

Even the syntax of <a href="https://blogs.oracle.com/CoreJavaTechTips/entry/using_enhanced_for_loops_with" target="_blank">enhanced loop</a> isn't so clear but brought a huge improvement in terms of reading. Under the hood the enhanced for uses the <a href="https://docs.oracle.com/javase/7/docs/api/java/util/Iterator.html" target="_blank">Iterator Interface</a> calling <i>hasNext()</i> and <i>next()</i> methods. 


{% highlight ruby %}
final List<BigDecimal> values = Arrays.asList(
			    new BigDecimal("70"), new BigDecimal("25"), new BigDecimal("55"),
			    new BigDecimal("12"));

values.forEach((BigDecimal doubleValue) -> System.out.println(doubleValue));
{% endhighlight %}

Noticed how is more readable? Makes more sense and clearly you can identify the meaning of that execution in terms of purpose but, thats just one of the characteristics of FP used to show the difference from an imperative to a functional paradigm in coding. The definition of FP isn't so clear but there are some features that can't be forgot when talking about the benefits of FP. According to <a href="http://bracha.org" target="_blank">Gilad Bracha</a> in (<a href="http://www.infoq.com/presentations/functional-pros-cons" target="_blank>">one brilliant presentation about what is and what isn't FP</a>, the definitions of FP vary, but tend to involve <a href="http://en.wikipedia.org/wiki/Higher-order_function" target="_blank">High Order Function</a> and [Abscence of effects]().

Those 2 things are really in the core of FP. Abscence of effects is directly related with immutability and one of the most important things when working with functions and you know that're prepared for the shift to FP when abscence of effects is automatic in your mind when modelling your functions, I'd enumerate others points to understand if you want to really dig into FP, that are:

- <a href="http://en.wikipedia.org/wiki/First-class_function" target="_blank">First Class Functions</a>
- <a href="http://en.wikipedia.org/wiki/Pure_function" target="_blank">Pure Functions</a>
- <a href="http://en.wikipedia.org/wiki/Immutable_object" target="_blank">Immutable variables</a>
- <a href="http://en.wikipedia.org/wiki/Currying" target="_blank">Currying</a>
- <a href="http://en.wikipedia.org/wiki/Tail_call" target="_blank">Tail Recursion</a>
- <a href="http://c2.com/cgi/wiki?PatternMatching" target="_blank">Pattern Matching</a>


So, let's see a brief explanation and a small example of each one in Scala of the above

### First Class Functions

First Class Functions are functions treated as objects themselves. It can be passed as a parameter to another function, return a function from a function or store a function in a variable. Functions which take other functions as parameter or return them are also known as <i>High Order Function</i>. Here is a small example, i decided to use Javascript for ours examples because it is a well known language and available in all modern browsers so you can easily open your browser and test the code.

{% highlight ruby %}
var myFunction = function(a, b){ return a + b }
myFunction(4,3);
function sumAllValues(a, b, c) { return a + b + c };
sumAllValues(myFunction(4,3), 5, 2)
{% endhighlight %}

In the example above we created a variable called <i>myFunction</i> and assigned an <a href="http://en.wikipedia.org/wiki/Anonymous_function" target="_blank">Anonymous Function</a> which sum two values. After I defined a function called <i>sumAllValues</i> where return the sum of his parameters that in our case one of them is the Anonymous Function assigned to myFunction variable, this is our small example of first class functions.

### Pure Functions

Pure Functions is a mathematical concept that relies on the fact that a function always evaluates the same value given the same arguments. In our subject it is directly associated with mutability and side effects or the absence of them. In FP we should not mutate variable values that are passed as parameters inside our functions and a function should be designed to <u>always perform the same computation, resulting in the same output given a set of inputs</u>. Larger functions tends to be hard to maintain and error prone, in a good functional design a function does exactly one computation and return the value of it.

### Immutable Variables

Immutable variables is a concept in the core of Functional Programming. It is related with side effects like Pure Functions, in therms of multi-thread applications an immutable object is totally reliable once it can't have his value changed so, if you want to change a value from a immutable object you should create a new one and reference to it. Immutable variables is not just a good practice in FP, languages like Java has lot of immutable classes in his core, <a href="http://docs.oracle.com/javase/6/docs/api/java/lang/String.html" target="_blank">String</a> is a classical example.

### Currying

Currying is a technique of changing the number of parameters of a function, so for example if a function has 5 parameters you can change it to one parameter. Currying is used behind the scenes in the <i>High Order Functions</i> mentioned above to simplify and reuse functions. Let's see a practical example with Javascript code:

{% highlight ruby %}
 function pow(i, j) { 
     return i * j;
 }
 
 function square (k) {
     return pow(k, 2);
 }
 
 alert(square(6));
{% endhighlight %}

The code above is a classical example where a function called <i>pow</i> that takes two parameters is used inside the <i>square</i> function instead of redoing his algorithm inside square function. As mentioned above, it enhances the flexibility and reuse of functions.

When understanding these topics, you'll start to take advantage of FP principles and have a better coding with more pleasure and less error prone. Probably you'll never want get back to old imperative way and will notice yourself thinking functional for solving problems that you used to have. When its happen you've been bitten by the functional bug ;)

### For Further Reading
 
If you want to go further, you can start by the John Backus paper <a href="http://web.stanford.edu/class/cs242/readings/backus.pdf" target="_blank">Can Programming Be Liberated From the Von Neumann Style? A Functional Style and Its Algebra of Programs.</a> where, back in 1977 he discuss some application for FP. Other good reference is the already mentioned presentation of Gilad Bracha where he explains how to distinguish FP hype from reality and to apply key ideas of FP in non-FP languages, separating the good parts of FP from its unnecessary cultural baggage.
What really made me fell confortable with FP as a beginner was the Martin Odersky course at <a href="https://www.coursera.org" target="_blank">Coursera</a> called <a href="https://class.coursera.org/progfun-2012-001" target="_blank">Functional Principles with Scala</a> that I mentioned before in this article. In this course you'll have a good understand of the difference between

Currently i'm reading the following book and finding it really helpful with good explanation about principles and techniques

<iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-na.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=US&source=ac&ref=qf_sp_asin_til&ad_type=product_link&tracking_id=raffretecblo-20&marketplace=amazon&region=US&placement=1449368174&asins=1449368174&linkId=LENUPRQEWK47BLGG&show_border=true&link_opens_in_new_window=true">
</iframe>

And you, from where you suggest to start with functional?