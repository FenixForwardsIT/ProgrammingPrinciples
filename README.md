# ProgrammingPrinciples
Here users can share their favorite programming principles


|||
|---|---|
|![http://ramda.jcphillipps.com/logo/ramdaFilled_200x235.png](http://ramda.jcphillipps.com/logo/ramdaFilled_200x235.png)|![https://miro.medium.com/max/640/1*PFDFHEJZiETncPczyBVJOQ.jpeg](https://miro.medium.com/max/640/1*PFDFHEJZiETncPczyBVJOQ.jpeg)|
(RambdaJS is cool)

 DRY
--------
### as in Dont Repeat Yourself
To adhere to this principle means to avoid repetition by all means neccesary.

#### Why would you want to be DRY?
When you search for DRYness constantly you will have a compass that will guide you for better abstractions and composability.
You will end up with more functions that perform smaller tasks and at the end of the day you will have created a confortable bed to sleep on: A framework made by yourself, for yourself. That's the end goal.

Being _"all means neccesary"_:
- [Composability](https://fr.umio.us/the-philosophy-of-ramda/#composability)  (RamdaJS will help you achieve this!)
- Higher order functions

    To pass a function as a parameter means treating function as values. 
    Languages that support this are said to give function first class citizenry, because they treat them as values.
    Languages that support this are said to have first class functions.
  - Function as parameter
    To send a function as a parameter to another funtion allows you pivot easily.
    In Python this is called by the community as the Decorator Pattern, as it allows you to decorate a function. 

  - Function as return
    Now you have a function factory. 



Open-Close Principle
-----
### so you find revisiting a piece of code again and again uh?
That's bad.
Speccifically I am talking about revisiting a same file over the course of months, even.

If you do so, you will eventually end up loosing track of your codebase, you will indeed get to the stage that is called by many as the _"ball of mud"_, where a project development ralentizes to the point it can no longer be mantained, or at least it will _always_ be in constant bug fixing. I have seen it happen, and it can happen to you too, so this is how to avoid it.

#### Plugin architecture
So how come that when you are working happily in your computer you can install a program just like that?... BAM! it is installed in no time. No recompilation of the entire OS is required. How?! What is this black magic??!!

Well, maybe you are not that impressed, you have seen it happen, many times, over the course of your lifetime. Maybe you just installed a program today, even.

Well, think again. Wouldn't it be awesome to have this feature on _your_ codebase?

To be able to just, "plug in", a piece of code, and to have it absorb it with ease? 
Maybe you would have to recompile it, yes, no doubt about it. But still, you did not have to _revisit_ your code, did you?

To be able to extend your code in a strongly typed language like C++ or Java withour recompilation you would have to be a scientist like Martin Odersky or Philip Wadler, (see [https://en.wikipedia.org/wiki/Expression_problem](https://en.wikipedia.org/wiki/Expression_problem)). 

##### No revisiting of the project.
Yes, that is what we are after.
And to achieve this you could in JS have an index.js file that imports all the files in a module directory and exports them back to the project as an object.

You would then, inside the project have an import of all this exports from this index.js file as an JS object!

Oh, this is powerful. You could then iterate over this JS object and tell each function to just _work_.

These functions would have to have a _work_ function, sure. And yes, you would have to manually import them on the index.js file.
But other than that... done! Imagine the posibilities!!!

With this in hand you can have a piece of the project that performs a series of tasks over some data. Maybe they pipe each transformation to the following function. And you could add a transformation or take one by adding or removing a file on your project.
(And in the case we talked you would have to add/remove them from the index.js file of the module, but that's it).

