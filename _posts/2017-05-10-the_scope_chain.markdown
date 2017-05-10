---
layout: post
title:  The Scope Chain
date:   2017-05-10 18:26:56 +0000
---


Back when I was first learning JavaScript, I looked at the code below and thought I knew the answer to what console.log would output:

```
function b() {
   console.log(myVariable);
}

function a() {
   myVariable = 2;
	 b();
}

myVariable = 1;
a();

```

I thought that because function b was being called within function a, that myVariable would console.log as 2. But that's not correct. When running the above code, myVariable is console.logged as 1. Why is this? The answer to this lies in The Scope Chain. 

Three execution contexts are created when we run the above code: the global execution context, function a's execution context, and function b's execution context. In a previous blog post I talked about how everytime an execution context is created some other things are created as well (like the variable this). But JavaScript also creates a reference to the outer environment. Every execution context has a reference to it's specific outer environment. In the case of function b, it's outer environment is the global execution context. This is also true for function a. Function b's outer environment is the global execution context because lexically, the function sits on top of the global environment. It's not inside of function a (although it is *called* in function a). When it comes to the outer reference that every execution context gets, JavaScript cares about the lexical environment. If you ask for a variable and JavaScript cannot find that variable within that execution context, it will go look in the outer reference for variables there. The outer reference is defined by where the function sits lexically. This act of JavaScript searching this *chain* of outer references for each execution context is called The Scope Chain! 

Let's try changing the lexical environment of function b so we can really cement the ideas explained above:

```
function a() {

   function b() {
      console.log(myVariable);
   }
	 
   myVariable = 2;
	 b();
}

myVariable = 1;
a();

```

We changed our code around and placed function b within function a...so now the lexical environment of function b has changed, meaning that we have changed where it physically sits in the code. Now function b's outer environment is function a, and function a's outer environment is the global execution context. 



