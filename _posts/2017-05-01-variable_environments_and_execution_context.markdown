---
layout: post
title:  "Variable Environments and Execution Context."
date:   2017-05-01 23:39:01 +0000
---


When I first happened upon these two terms they were a little intimidating. A lot of under-the-hood JavaScript terminology can be. However when you break it down neither of the two are wildly complicated. So I want to explain them and make it a little bit easier for someone who might not understand these two things. Both of these concepts are really important in JavaScript to understand, and truly understanding them will make you a better programmer.

Let's talk about execution context first. I touched on it last week in my blog post about hoisting. The execution context is basically the environment that your code is run in. When you first run your program in the browser, a global object and a variable called 'this' are both created. Within that global object memory space is dedicated to the functions that you've written and the variables that you have created. 

Before we go any deeper into execution context, I want to circle back and talk about what is meant when the term 'variable environments' is used. What that boils down to is where variables live and how they relate to each other within your program's memory. In other words, where is the variable located?

Let's look at some example code and then talk about how it relates to the two terms we're focusing on learning today.

```
function x() {
   var myAge;
	 console.log(myAge);
}

function y() {
   var myAge = 26;
	 console.log(myAge);
	 x();
}

var myAge = 25;
console.log(myAge);
y();
```

If I were to run this code in my browser the output that I would receive in order is: 25, 26, and undefined. 

What exactly is happening as these functions are invoked? Well, first the global execution context is created. In our example, the variable myAge is created and executed in the global execution context...and at this point in time the value of myAge is 25. 

Then we invoke function y. A new execution context and variable environment is created for the function y. When it is created, myAge is going to to be defined as 26. Within the function y, we invoke the function x. Another new execution context variable environment is created. This time, because haven't defined myAge, the variable will be put into memory with the value 'undefined'. 

Each declaration of myAge is distinct and unique and they do not interact with each other. 



