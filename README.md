# Closures-in-JavaScript-Lesson-Plan

At first glance what do you think name will be when console.logged in the "one" function? What about the "five" function?

![Intro Image](https://github.com/MichaelBaynon/Closures-in-JavaScript-Lesson-Plan/blob/main/intro.png)

If you said "bob" and then "sam" you would be correct.

![Output Image](https://github.com/MichaelBaynon/Closures-in-JavaScript-Lesson-Plan/blob/main/output.png)

While this example looks complex its actually a very simple example of closures in Javascript.

When you think about closure you have to think about the relationship variables have with functions and "scope".

The Javascript documentation describes scope as: "The current context of execution. The context in which values and expressions are "visible" or can be referenced. If a variable or other expression is not "in the current scope," then it is unavailable for use. Scopes can also be layered in a hierarchy, so that child scopes have access to parent scopes, but not vice versa."

In this example on the first line, "name" is defined as "bob". In the "one" function we console log "name" and get exactly what we expect "bob".

Where closure comes in is later down the file we redefine name to equal "sam" and when we console.log there we receive back "sam".



____________________________________________________________________________________________________________________________________




If we had console logged on the outside of all the functions all the way at the bottom what do you think the response would be?

![Intro Image Edited](https://github.com/MichaelBaynon/Closures-in-JavaScript-Lesson-Plan/blob/main/introEdited.png)

If you got "bob" again you would be right because the name variable defined in the "five" function only applies to the scope of that specific function there it doesn't change "name" to "sam" globally just locally inside of that function.

________________________________________________________________________________________________________________________________


If you found that complicated that is ok because we have a couple simple examples of closures.

For our first example, this is the most simplistic form of closures.

![Intro Image Edited](https://github.com/MichaelBaynon/Closures-in-JavaScript-Lesson-Plan/blob/main/basicExample.png)

Due to the magic of closures we can access the "vehicle" variable inside of our function so when we call the vechicleType() function we don't have to pass in a value for "vehicle" it inherits it from the outside.

![Intro Image Edited](https://github.com/MichaelBaynon/Closures-in-JavaScript-Lesson-Plan/blob/main/basicOutput.png)

If we were to redefine vehicle outside the function but beneath the variable declaration we could actually change the value of the console.log as shown here:

![Intro Image Edited](https://github.com/MichaelBaynon/Closures-in-JavaScript-Lesson-Plan/blob/main/basicAdded.png)

![Intro Image Edited](https://github.com/MichaelBaynon/Closures-in-JavaScript-Lesson-Plan/blob/main/basicAddedOutput.png)

___________________________________________________________________________________________________________________________

