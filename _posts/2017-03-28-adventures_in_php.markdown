---
layout: post
title:  "Adventures in PHP"
date:   2017-03-28 18:51:31 -0400
---


I have officially graduated Flatiron's online Web Development program! So what's next for me? The job search is now in full swing, and I've decided to take up learning PHP. I'm always on the lookout for something new to learn, and lucky for me I've picked a career path where there is a plethora new material. I decided to begin learning PHP because I often hear it come up in conversations involving web design, which is what originally inspired me to start learning how to code.

I decided to use Codecademy to learn PHP, and I thought I would take any readers along with me. So let's just get into it and start out by talking about Loops in PHP. Loops are a useful tool that show up in numerous programming languages. Because I've seen it before in both JavaScript and Ruby, knowing the basics of how a loop works and what we use it for makes for an easy learn. However, for those of you who may not have encountered loops before, I'll explain! 


The definition of a loop is "a sequence of instructions that is continually repeated until a certain condition is reached." Simple enough. There are four types of loops in PHP; the for loop, the foreach loop, the while loop, and the do while loop. 

# The for loop.

So at what time is it appropriate to use the for loop? You should use the for loop when you know how many times you want the program to run. The following is an example of the for loop in PHP:

```
<?php
   for ($laps = 1; $laps <= 10; $laps = $laps++) {
      *code to be executed*
   }
?>
```

In this example let's say you are counting the number of laps in a pool that a swimmer does. We want her to only do 10 laps at which point she should stop. $laps = 1; is the initialization. We are starting at 1 lap, and counting upwards from there. $laps <= 10 is the condition. As long as $laps is less than or equal to 10, we want the program to keep running. $laps++ is the increment that we want to count up by. ++ is adding 1 to the initialized $laps number. 

# The foreach loop.

The foreach loop provides an easy way for your program to loop over an array. Actually the foreach loop only works on arrays and objects in PHP. The following is an example of using a foreach loop in PHP: 

```
<?php
   $fruits = array("Banana", "Apple", "Kiwi", "Orange");

   foreach ($fruits as $fruit) {
      echo <li>$fruit</li>
   }

   unset($fruit);
?>
```

First we are creating an array of fruits that we want our program to go over and print out in list form to our application. After that we are using the foreach syntax and telling our program to go over our fruits array and give each item in the array the value of $fruit after which the internal array value is incremented by one, meaning that the next time the program runs it will be looking at the next item in your array. Each run through prints out the item of the array in list. The unset($fruit) is breaking the reference with the last element, so that $fruit is now free to be assigned to the next element in the array on the second runthrough. 

# The while loop.

If you don't know how many times a loop should repeat, you should probably be using the while loop. As long as a certain condition is true, the while loop will keep repeating. Once the condition is no longer true the loop will break and stop. Here is an example of a while loop in PHP:

```
<?php

  $count = 1;
	
	while($count <= 10){
	   echo "I have $count dogs!";
	   $count ++;
	}

?>
```

First we are establishing our starting point for the while loop with declaring that $count is equal to 1. The second bit of code is the actual while loop. What we are saying with while($count <= 10), is while the variable $count is less than or equal to 10, we want our program to run. But once it gets to 10 we would like it to stop counting. After each time we run through we print out onto the screen "I have $count dogs!". The number that $count is at is the number that will be printed out. At the end we increment $count by one. It will keep incrementing until the statement $count <= 10 is no longer true, then the loop will break!

# The do while loop.

The do while loop is very similar to the while loop. What makes them different is when the truth of a statement is checked. In the while loop the truth expression is checked at beginning of the of the iteration, whereas the do while loop checks the truth expression at the end. Here is an example of a do while loop in PHP using the same dogs example as above:

```
<?php

  $count = 1;
	
	do {
	   echo "I have $count dogs!";
	} while ($count <= 10);

?>
```

Again we are establishing the starting point for our loop as being 1 when we declare $count. Then we ask the loop to run with do{ and are printing out "I have $count dogs!". After that is when we check the truth of the expression. While $count is less than or equal to 10, keep running the program. In a do while loop, the program will execute the code block echo at least one time and then check true or false, whereas in a while loop the statement will be checked first so the program may never actually run if the statement starts out as false. 



Look out for part 2 of this series next week when I get into PHP functions! 




