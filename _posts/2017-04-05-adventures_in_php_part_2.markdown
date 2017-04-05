---
layout: post
title:  "Adventures in PHP (Part 2)"
date:   2017-04-05 19:20:47 +0000
---


New week, new concept! Let's talk about reusable pieces of code that we can use in multiple places throughout applications that we build. There's a name for those. Functions. 

One of the fundamental principles in programming is "don't repeat yourself". Often times I hear people shorten it to DRY. Keep your code dry. PHP has a lot of useful built in functions which are easy to look up online. However we want to learn how to build our own functions in PHP. 

The syntax of functions in PHP is much the same as in JavaScript. In PHP, functions are case insensitive and you can use numbers, letters, underscores, or dashes.

```
function name(parameters) {
  statement;
}
```

Remember that defining a function doesn't mean that we are putting it to use. We have to call it, just like in JavaScript, to actuall use the function. Here's an example of a function with the call.

```
function favoriteFood() {
  echo "Pizza4Lyfe";
}

favoriteFood();
```

The function above will display "Pizza4Lyfe"! In PHP, echo or print just display what the function results in. What we usually want to use is the *value* that the function returns. To use this value, we use the keyword "return". If I replaced the word "echo" in the function above with "return", the word "Pizza4Lyfe" would not display on screen, however the function would be returning that value. 

So, I want to write out a basic function in PHP to wrap up. 

```
function helloWorld($name, $location) {
  echo "Hello! My name is " . $name . " and I am a developer located in " . $location . " - the best city in the world!";
}

$name = "Miranda";
$location = "Seattle";

helloWorld($name, $location);
```

The function above will output "Hello! My name is Miranda and I am a developer located in Seattle - the best city in the world!"

Functions in PHP are pretty simple and straightforward - especially if you have previous knowledge of JavaScript. The fun part though happens when objects are thrown into the mix. Next week I'll continue my adventures in PHP when I learn and write about objects. It's always helpful to write out and explain (like in this blog post) new concepts. It really cements things. 

See you next week! 



