---
layout: post
title: "Javascript's This Nightmare"
description: ""
category: lessons
tags: [Javascript]
---
{% include JB/setup %}



<div style="margin-bottom: 1.5em;">
	<div>
		<a href="https://twitter.com/share" class="twitter-share-button" style="vertical-align: bottom">Tweet</a>
	</div>
	<div>
		<span id="facebook-share" class="fb-share-button" data-href="http://rafaelcfreire.github.io/lessons/2014/10/11/Javascripts-this-nightmare/" data-layout="button"></span>
	</div>
</div>

Hi there,

This is the first formal post of my blog, the idea here is to bring relevant topics and discussions that I have faced in my career. Considering that, I decided to pick up a subject that is very confusing even for experienced developers, specially for those who came from an object oriented programming and aren't so familiar with Javascript. The "this nightmare" can bring on some bugs that are really messy and hard to track. Actually it is some of the basic knowledge of the Javascript language that took me a long time to understand and consequently decided to write about. So, let's dive into how the <i>this</i> reference works in Javascript.

### Different Types of Invocation

The first step to understand how the <i>this</i> reference works in Javascript is know that it depends on how it is being referenced. There are four distinguished ways to do that and they are:

- As a simple function invocation.
- As a method invocation.
- As an object creation.
- Using the .apply and .call functions.

Let's see each one and discuss the contrasts between them.

### As a Simple Function Invocation
That's the simplest way to invoke a function, in a direct function call in Javascript the <i>this</i> reference is bound to the global object at runtime. Let's go for some real life examples:

- Open a Chrome browser and then open the Developer Tools (F12).
- Go to Console item in the toolbar.
- Create a simple function called doSomething as follow.

{% highlight ruby %}
		function doSomething(){
 console.log( this ); 
}
{% endhighlight %}

- Call the doSomething function.
{% highlight ruby %}
		doSomething();
{% endhighlight %}
 
- Note that the <i>this</i> points to the window object.


At this point you should have the same as image below:


![My helpful screenshot](/assets/image_post_2014_10_11.png)


### As a Method Invocation
For those with a object oriented background the method invocation is the mostly natural way to be understood. When a function is a property of an object it can be invoked as a method for the instance of that object and in this case the <i>this</i> reference clearly will be bounded to the instance of that object. Here's an example:

- Open a Chrome browser and then open the Developer Tools (F12).
- Go to Console item in the toolbar.
- Create a Javascript object called <i>simpleObject</i> and add a method <i>simpleMethod</i> as follow.

{% highlight ruby %}
var simpleObject = 
{ 
 counter: 0, 
 addCounter: function(value){ 
  this.counter += value;
 } 
};
{% endhighlight %}

- Then, call our method <i>addCounter</i> on the instance of <i>simpleObject</i>.
 
{% highlight ruby %}
		simpleObject.addCounter(1);
{% endhighlight %} 

- Print the value of our variable counter by doing

{% highlight ruby %}
		simpleObject.counter;
{% endhighlight %} 


So, you'll have the following values in your console:

![My helpful screenshot](/assets/image2_post_2014_10_11.png)

What happened in the example above? We created an object called <i>simpleObject</i> with two attributes: <i>counter</i> and <i>addCounter</i>. An <a href="http://en.wikipedia.org/wiki/Anonymous_function#Javascript" target='_blank'>anonymous function</a> that is responsible for add an value to the counter attribute is associated with the addCounter attribute using the <i>this</i> to point to the instance of the object, then we call the method addCounter with "1" as parameter and next check the value of counter attribute. So, in a method invocation inside an Javascript object the this reference points to the instance of the object.

### As an Object Creation
AKA referenced as Constructor Invocation, this method considers that any named function can be used as a constructor. There's no difference in the function declaration, the difference is in how the function is invoked once it uses the <i>new</i> keyword. If a function is invoked with the <i>new</i> prefix a new object is created and <i>this</i> is assigned to that object. Let's see how it works:

- Open a Chrome browser and then open the Developer Tools (F12).
- Go to Console item in the toolbar.
- Create a Javascript function called <i>Creation</i> (By convention, once it's a constructor we'll keep it with a capitalized name). In this function, create an attribute called <i>firstAttribute</i> and bound it to a function associated with <i>this</i>. 

{% highlight ruby %}
function Creation()
{
 this.firstAttribute = function () { return this; };
}
{% endhighlight %} 

- Now, create an object using the constructor.

{% highlight ruby %}
	var objectOne = new Creation();
{% endhighlight %} 

- Check the value of firstAttribute inside objectOne.

{% highlight ruby %}
	objectOne.firstAttribute();
{% endhighlight %} 

So, the value of <i>this</i> is an empty object created when the function <i>Creation</i> was called with the prefix <i>new</i> as in the following image:

![My helpful screenshot](/assets/image3_post_2014_10_11.png)

### Using the .apply and .call Methods
And last, the <i>.apply</i> and <i>.call</i> methods are those who you can set any object you want as <i>this</i>. Once functions are what we call as <a href="http://en.wikipedia.org/wiki/First-class_function" target='_blank'>first class citizens</a> they can have properties and methods, just like an object and <i>.apply</i> and <i>.call</i> are two methods available for all functions in Javascript. First class citizens is one of the mostly important definitions of Javascript functions and you should read about it if don't feel confident enough in this subject. So, as said before, <i>.apply</i> and <i>.call</i> are opened for you choose which will be your <i>this</i> reference, let's practice:

- Open a Chrome browser and then open the Developer Tools (F12).
- Go to Console item in the toolbar.
- Create a function <i>sumArray</i> that sum the values of an array.

{% highlight ruby %}
function sumArray(){
 var sum = 0;
 for(var n = 0; n < arguments.length; n++){
  sum += arguments[n];
 }
 this.sum = sum;
}
{% endhighlight %}
 
- Create two variables and name then as <i>object1</i> and <i>object2</i>.
- Call the <i>sumArray</i> function using the <i>apply</i> method. As parameter pass the <i>object1</i> to be the reference of <i>"this"</i> and an array with the values will be used to sum.

{% highlight ruby %}
	sumArray.apply(object1, [1,2,3]);
{% endhighlight %}

- Call the <i>sumArray</i> function using the <i>call</i> method. As parameter pass the <i>object2</i> to be the reference of <i>"this"</i> and the values separated with commas to be used to sum.

{% highlight ruby %}
	sumArray.call(object2, 3, 4, 5);
{% endhighlight %}

- Note that the first parameter will be our <i>this<i> in both cases, the difference between the two methods is that <i>.apply</i> expect an array and <i>.call</i> values separated by a single comma.
- Inside <i>sumArray</i> function, we setted <i>this.sum</i> value, so let's check those values. Type <i>object1.sum</i> and <i>object2.sum</i> to see if they were setted right.

{% highlight ruby %}
	object1.sum;
	object2.sum;
{% endhighlight %}

![My helpful screenshot](/assets/image4_post_2014_10_11.png)

### Strict Mode
We mentioned some times that the this reference is bounded to the global object at runtime but, what it means? It depends on the environment you're executing the code. If you run the example above in the console it will be the <a href="http://www.w3schools.com/js/js_window.asp" target="_blank">window object</a>, if you run inside a <a href="http://nodejs.org" target="_blank">NodeJS</a> environment it will be the NodeJS global object. But both environments has (<a href="http://www.yuiblog.com/blog/2010/12/14/strict-mode-is-coming-to-town/" target="_blank">Strict Mode</a>. Strict mode sets the <i>this</i> to an undefined reference. You can see in the link above the advantages of using Strict mode.

### For Further Reading
To go deeply in this subject I suggest the following books, both focused in Javascript. The first is a book of <a href="https://github.com/getify/You-Dont-Know-JS/blob/master/README.md#you-dont-know-js-book-series" target="_blank">You Don't Know JS Series</a> which I'm currently reading and highly suggest for deeper understanding of the mechanism of <i>this</i>. In the link above you can see that's there are more interesting topics about JS like Scope, Closures. If you want to buy a copy of the book, click on the link below. The second link is one of the greatest books about JS. Javascript: The Good Parts is an introdutory reference to some of the most important points in JS. Written by <a href="http://Javascript.crockford.com" target="_blank">Douglas Crockford</a>, creator of JSON.


 
<iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-na.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=US&source=ac&ref=tf_til&ad_type=product_link&tracking_id=raffretecblo-20&marketplace=amazon&region=US&placement=1491904151&asins=1491904151&linkId=463ZW6OOIPXPIIB5&show_border=true&link_opens_in_new_window=true">
</iframe>

 
<iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-na.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=US&source=ac&ref=tf_til&ad_type=product_link&tracking_id=raffretecblo-20&marketplace=amazon&region=US&placement=0596517742&asins=0596517742&linkId=ZTOWF5DCU6HUXDRX&show_border=true&link_opens_in_new_window=true">
</iframe>

<script type="text/Javascript" src="/js/main.js"></script>



