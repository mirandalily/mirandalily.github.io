---
layout: post
title:  "Anonymous Functions and Hoisting"
date:   2017-06-22 16:06:04 -0400
---


I ran into some code this weekend that acted a little differently than I think most people would expect it to act. Here's an example of the code:

```
hello();

function hello() {
 console.log("Howdy!");
}

var anonymousHello = function() {
 console.log("Hey");
}

anonymousHello();
```
 
So the code above is pretty straighforward. Now I want to switch around 1 line and see how it affects my code. So the code ends up looking like this:

```
hello();

function hello() {
 console.log("Howdy!");
}

anonymousHello();

var anonymousHello = function() {
 console.log("Hey");
}
```

If you didn't know about execution context, you may expect that this code would still run the same as the original code that I first wrote out. But it doesn't. We know that in the execution context, variables are given a namespace and set as undefined, then the JavaScript code is read line by line. Because we have an anonymous function stored within a variable, it's value is set to undefined, so when we call the function anonymousHello after the execution context, but before the variable's value is set...the function call will return an Uncaught TypeError: undefined is not a function! 

This is another great example of how execution context works - and it really cements the idea about namespace being reserved for variables.
