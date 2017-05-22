---
layout: post
title:  Under The Hood: Coercion
date:   2017-05-22 22:39:47 +0000
---


Coercion, in JavaScript, means converting a value from one type to another. It's an important concept to learn in JavaScript because it happens frequently since JS is dynamically typed. It's one of those concepts that you want to really understand what's going on "under the hood". 

Let's look at an example:

```
var x = 2 + "3";
console.log(x);
```

When I first began learning JavaScript I thought that the above code would output an error. You can't add a number and a string. That doesn't make sense! However when you run the above code in your browser, the console.log outputs "23". What?
It turns out that, under the hood, the JavaScript engine *coerced* the first number (2) into a string and concatenated the two strings to output "23". The creators of JavaScript basically wrote in a "best guess" chunk of code that decides when it sees the number and the string, it will coerce the number into a string.

Coercon is a fundamental part of the JavaScript language. It isn't a ridiculously complicated concept, however, knowing what's going on under the hood can really help you debug code in the future if you're receiving something that doesn't look quite right. 
