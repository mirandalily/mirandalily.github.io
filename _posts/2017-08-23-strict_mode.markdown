---
layout: post
title:  "Strict Mode"
date:   2017-08-23 23:18:19 +0000
---


JavaScript is an incredible flexible language. There is a way, called strict mode, to "opt in" and tell the JS engine that you want it to be pickier about what it can do. Why would we want to do this? Well, it can prevent errors in certain circumstances. Let's look at an example.

```
var fruit;

friut = {};
console.log(friut);
```

If you notice above, I mispelled the word fruit on the third line. I would assume that JavaScript would present me with an error on line 4 where I console.log the errored typing. But it doesn't error. Friut exists. So does fruit. This can get really tricky when you have a bunch of code and there's just a tiny mispelling that can be hard to look back and find. So what can we do about this. Strict mode can implement some extra rules for you. At the top of your document you want to write:

```
"use strict";
```

In strict mode you must declare a variable in order to set it equal to something later on in your code. When adding "use strict"; above the first bit of code I wrote, the console will error and tell me that friut is not defined. You can also place "use strict"; *within* a function since there's a new execution context with every function. 

Strict mode saves me a lot of headaches at times because I definitely misspell things!

