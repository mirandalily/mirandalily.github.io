---
layout: post
title:  Under The Hood: Operators
date:   2017-05-16 23:10:20 +0000
---


So Operators is a really simple concept in JavaScript, but I wanted to share something with you that I learned in my quest to better learn what's happening in JavaScript under the hood.

To start off, let's just remind ourselves what all of the operators in JavaScript are:

![](https://gyazo.com/0b0f5814667ea56b441a713fe4d2d062)

There are also assignment operators, but I want to specifically focus on the arithmetic ones today. So when we see something like `var a = 3 + 5` and we `console.log(a)`, it's pretty obvious that what is logged will be the sum of 3 + 5...8! But what's really happening under the hood in JavaScript? 

Under the hood the JavaScript engine actually provides a function for the operator `+`. It would look a little something like this:

```
function + (a, b) {
   return // add the two numbers
}
```

The difference is that instead of calling the function like you normally would as `+ (3, 5);` the JavaScript engine provides you the ability to write what is called *infix notation*. Infix means that the function name (which in this case is the operator) sits between the two parameters you are providing.

Operators are such a simple thing in JavaScript that I don't think many people take the time to really look into how operators work. We just kind of think, oh yeah - math. That's easy. But when I went to figure out such a simple "easy" topic, I realized I hadn't thought of operators as predefined functions provided by the JavaScript engine. I took operators for granted! 

I stand by the idea that to be a great coder, you *must* understand what's going on under the hood.
