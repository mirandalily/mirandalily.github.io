---
layout: post
title:  "Hoisting in JavaScript"
date:   2017-04-25 23:55:28 +0000
---


Let's talk about hoisting in JavaScript. Here is some code that I want to run in my browser:

```
var a = "Hello, I'm A!"

function b() {
   console.log("called function b!");
}

b();
console.log(a);
```

When I run this code and open up my dev tools, I expect to see in order: 

called function b!
Hello, I'm A!

And sure enough, that is exactly what is outputted to the console in dev tools. Now let's switch up the code to something that, in most languages, we would expect to receive an error for.

```
b();
console.log(a);

var a = "Hello, I'm A!"

function b() {
   console.log("called function b!");
}
```

Most programming languages execute their code one line at a time. Because we have called function b on line 1, and haven't defined it until line 6...I would expect not to be able to use that function yet. But here is the ouput in the console that we receive when we refresh the browser:

called function b!
undefined

We didn't receive the error that we thought we might. JavaScript did in fact run the function. The variable "a" also did not throw an error, even though we received undefined in our console.log. This is called hoisting. 

Often times hoisting is explained as "Oh, JavaScript moves (hoists) the variables and functions up to the top so that they work". But this isn't really what hoisting is, as we can see with the previous example. We did define the variable "a", however it still showed up as "undefined". If the JavaScript engine was physically moving our code around and placing variables and functions at the top...then we wouldn't have received "undefined".

This can all be explained by understanding the Execution Context. We want to focus on the "creation phase". When you first run your code in the browser the Javascript engine runs what is known as the creation phase. That is where a global object, a special variable called 'this', an outer environment, and memory space for variables and functions are all created. The memory space is what is called "hoisting". The JavaScript engine essentially stores functions and variables. Functions are set up in their entirety, however it assigns variables to the special keyword "undefined". ALL variables in JavaScript, in the creation phase, are set to "undefined". 

So, as a final note it's important to understand that the keyword "undefined" does not mean that you haven't defined that variable. The JavaScript engine knows that the variable is there, it has just assigned it to a special keyword that signifies it has been initialized by the engine but not set to a value yet. That's why it is best coding practice to never set a variable to undefined yourself (which you actually can do). In the long run it will confuse you and other developers that may be looking at your code.





