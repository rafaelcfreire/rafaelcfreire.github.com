---
layout: post
title: "What are the Real Benefits of Functional Programming?"
description: ""
category: 
tags: [languages, scala, javascript, java 8, functional]
---
{% include JB/setup %}

Hi all,

Nowadays it is very common to see people discussing the use of [functional programming](https://www.haskell.org/haskellwiki/Functional_programming), mostly of modern languages adopt some of his principles and seems that it is a new shift that will change the way you program, but isn't one or another. Functional programming has been around for a long time and there are some misconceptions, confusions and prejudice about the concept of functional programming that leds to misuse of a very useful paradigm but that isn't a silver bullet. People with background in [imperative programming](http://en.wikipedia.org/wiki/Imperative_programming) where the solution for an algorithm should be described step by step in a sequence of statements tends to feel love at first sight with functional programming due to the fact of writting much less code to achieve the same results and ease of reading.

### What is Functional Programming?

One of the misconceptions that we can mention is that functional programming is a replacement for object oriented programming. Definitely NOT...repeat it to yourself 3 times. There is no contradiction with OO ([Scala](http://scala-lang.org) use both for example), rather, you can use object oriented design with a functional implementation. Functional programming is a [paradigm](http://en.wikipedia.org/wiki/Programming_paradigm) focused in how should be the structure of the implementation, so, instead of describing all the steps to perform an action ending in a low level and verbose code, functional is more concise, easier and expressive. I have a fully background in imperative paradigm, mainly in Java and right in my firsts experiments with FP i was really excited, imagine a language with wich you code as simple as reading? Let's see in practice what it means comparing the old way in java with the [new syntax of Java 8 with Lambda expressions](http://www.oracle.com/webfolder/technetwork/tutorials/obe/java/Lambda-QuickStart/index.html). Here's a simple example of iterate through a collection

{% highlight ruby %}
final List<BigDecimal> valores = Arrays.asList(new BigDecimal("70"), new BigDecimal("25"), new BigDecimal("55"), new BigDecimal("12"));

for(BigDecimal doubleValue : valores){
 System.out.println(doubleValue);
}
{% endhighlight %}

Even the syntax of [enhanced loop](https://blogs.oracle.com/CoreJavaTechTips/entry/using_enhanced_for_loops_with) isn't so clear but brought a huge improvement in terms of reading. Under the hood the enhanced for uses the [Iterator interface](https://docs.oracle.com/javase/7/docs/api/java/util/Iterator.html) calling <i>hasNext()</i> and <i>next()</i> methods. Now let's see the functional way

{% highlight ruby %}
final List<BigDecimal> valores = Arrays.asList(
			    new BigDecimal("70"), new BigDecimal("25"), new BigDecimal("55"),
			    new BigDecimal("12"));

valores.forEach((BigDecimal doubleValue) -> System.out.println(doubleValue));
{% endhighlight %}

Noticed how is more readable? Makes more sense and clearly you can identify the meaning of that execution in terms of purpose but, thats just one of the characteristics of FP used to show the difference from an imperative to a functional paradigm in coding. The definition of FP isn't so clear but there are some features that can't be forgot when talking about the benefits of FP. According to [Gilad Bracha](http://bracha.org) in one [brilliant presentation about what is and what isn't FP]((http://www.infoq.com/presentations/functional-pros-cons)), the definitions of FP vary, but tend to involve [High order functions]() and [Abscence of effects]().

Those 2 things are really in the core of FP. Abscence of effects is one of the most important things when working with functions and you know that're prepared for the shift to FP when abscence of effects is automatic in your mind when modelling your functions, i'd enumerate others points to understand if you want to really dig into FP, that are:

- [Pure Functions](http://en.wikipedia.org/wiki/Pure_function)
- [Immutable variables](http://en.wikipedia.org/wiki/Immutable_object)
- [Currying](http://en.wikipedia.org/wiki/Currying)
- [Tail Recursion](http://en.wikipedia.org/wiki/Tail_call)
- [Pattern Matching](http://c2.com/cgi/wiki?PatternMatching)

When understanding these topics, you'll start to take advantage of FP principles and have a better coding with more pleasure and less error prone. Probably you'll never want get back to old imperative way and will notice yourself thinking functional for solving problems that you used to have. When its happen you've been bitten by the functional bug ;)

### For Further Reading
 
[Can Programming Be Liberated From the Von Neumann Style? A Functional Style and Its Algebra of Programs.](http://web.stanford.edu/class/cs242/readings/backus.pdf)

 For those who wants to have a deeper understanding of this separation of what is and what isn't the benefits of FP i highly recomend [this talk](http://www.infoq.com/presentations/functional-pros-cons), one of the authors of Java language [Gilad Bracha](http://bracha.org) explains how to distinguish FP hype from reality and to apply key ideas of FP in non-FP languages, separating the good parts of FP from its unnecessary cultural baggage.