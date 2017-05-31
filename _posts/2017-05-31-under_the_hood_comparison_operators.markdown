---
layout: post
title:  Under The Hood: Comparison Operators
date:   2017-05-31 21:46:12 +0000
---


I learned something new the other day. I was looking into comparison operators in Javascript, and how they work under the hood, and I came across two interesting examples. 

```
console.log(1 < 2 < 3)
```

When running the above code example I expected to open up the console and see the word "true" console logged. And this was the case. 1 is less than 2 which is less than 3. However, when I reversed the order, something happened that I didn't fully expect.

```
console.log(3 < 2 < 1)
```

The above code returned true as well. But wait...3 isn't less than 2, and 2 isn't less than 1. So what's going on? Well, the Javascript engine isn't reading this statement like a human would. When looking up comparison operators we see that when using the less than symbol, the associativity is left to right. Okay, but that still doesn't seem to answer the question as to why we are getting true, when we know the above statement isn't true in human logic. It turns out that the JavaScript engine first reads 3 < 2 and returns false. The JavaScript engine wants to compare numbers, so it uses coercion to return false as a number. When the JavaScript engine coerces "false" into a number it becomes 0. So the JavaScript engine is really comparing the following statment:

```
console.log(false < 1)
```

Which, when coerced, turns into:

```
console.log(0 < 1)
```

0 is in fact less than 1, so the statement is returned to us as true.
