---
layout: post
title: "Javascript optimization performance"
description: ""
category: 
tags: []
---
{% include JB/setup %}
Performance tips for javscripts 

Load Script at the end of body
http://stackoverflow.com/questions/436411/where-is-the-best-place-to-put-script-tags-in-html-markup
Use common methods in the prototype chain
Dont update the DOM many times, use a document fragment (http://www.w3schools.com/jsref/met_document_createdocumentfragment.asp)
Declare variables a few times as possible
String concatenation (In a Array loop, instead of += use join, inherited from Array prototype)


Measuring performance