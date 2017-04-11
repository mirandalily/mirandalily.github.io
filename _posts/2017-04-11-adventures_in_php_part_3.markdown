---
layout: post
title:  "Adventures in PHP (Part 3)"
date:   2017-04-11 00:14:20 +0000
---


Much like Ruby, PHP is an Object Oriented Language (OO Language). As a refresher, objects have properties which are sometimes called attributes, and the object's functions are called methods. Almost everything is an object in PHP, and an object is an easy way to keep our functions (or methods) and data on one place. To create objects we need classes which are also called object constructors. When we construct an object via a class, we refer to is as an instance. Here is an example of a class that we would use to create an instance of an object.

```
class Student {
   public $firstname;
	 public $lastname;
	 public $teacher;
	 
	 public function __construct($firstname, $lastname, $teacher)
	    $this->firstname = $firstname;
			$this->lastname = $lastname;
			$this->teacher = $teacher;
		}
	}
```

So each time we created a student, that student's instance would contain data that includes their first name, last name, and teacher. To assign that data we have a constructor where we input the first name, last name, and teacher. Take note that the construct method is written how constructor functions must be written. 

Here is an example of the creation of a student.

```
$student1 = new Student( "Jane", "Doe", "Ms. Anderson")
```

We are creating a new instance of the Student class called $student1 and assigning the data that we want stored in that instance within the parenthesis. 

Let's say we had a function "Greet" within the Student class. 

```
public function greet() {
   echo "Hello, " . $this->firstname . ". Your teacher this year is " . $this->teacher "!";
}
```

When we call the method greet on $student one, we should get the output "Hello, Jane. Your teacher this year is Ms. Anderson!"

Here is the call that we would make to have that funciton show up on a webpage:

```
echo $student1->greet();
```

Note that we don't use the $ sign in front of the method after the arrow ->. 

I'm pleasantly surprised by how similar PHP is to other object oriented languages that I've learned and I feel as if I'm picking it up quickly at this point. Learning a similar language to one you've already learned is a good refresher for the language you already know. You think back how objects are constructed in say, JavaScript, while learning object construction in PHP, and it's a great brain exercise.
