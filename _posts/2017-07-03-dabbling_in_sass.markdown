---
layout: post
title:  "Dabbling in SASS"
date:   2017-07-03 20:25:09 +0000
---


This past weekend as I was looking through job postings, I noticed a pattern of companies looking for employee candidates that know Sass. I haven't used Sass before, so I decided it would be a beneficial thing for me to use. I wanted to create an easy set up blog post for those of you who may have not learned it yet - as far as I know Flatiron hasn't set up a section teaching it.

Sass is essentially an extension to CSS3 that adds features to it that will make your life easier! As a Flatiron student using a mac, I have Ruby already installed. Because of this it's a very simple install, you simply type 

```
gem install sass
```

And then to check and make sure that it installed correctly...you can type 

```
sass -v
```

In case you run into any errors installing sass, you may try:

```
sudo gem install sass
```

So what do we get with sass exactly? Sass provides you with variables, nesting, partials, imports, extend/inheritance, and operators.

Variables is one of my favorite things that Sass provides. In CSS you reuse a heck of a lot of things...but what if you decide you want to change that shade of blue that you set in so many different classes? You can set a variable at the beginning of your style sheet and just use that variable as the color instead of the hex code! Sass uses the $ sign to declare a variable. That way, if you change it, everything you have it set to is automatically changed. *Awesome*.

Sass provides nesting which creates an incredible easy way to organize your code. It makes your code that much more readable. 

Partials are snippits of code that you can import into various Sass files and reuse. Which brings us to import. Say you have a file named basics.sass. You can, in your main style sheet, call `@import basics`.

Lastly, one of the most useful things that Sass provides is extends/inheritance. Using extend allows you to share properties of other selectors. It allows you to keep your code especially DRY - which is what we aim for! 

Check out Sass's website for any further details and just start playing around with it. I am really enjoying it so far and am excited to go back and clean up some of my code in past projects. 

http://sass-lang.com/



