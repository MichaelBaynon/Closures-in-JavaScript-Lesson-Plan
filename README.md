### Closures-in-JavaScript-Lesson-Plan

# Introduction

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

# Basic Example

If you found that complicated that is ok because we have a couple simple examples of closures.

For our first example, this is the most simplistic form of closures.

![Intro Image Edited](https://github.com/MichaelBaynon/Closures-in-JavaScript-Lesson-Plan/blob/main/basicExample.png)

Due to the magic of closures we can access the "vehicle" variable inside of our function so when we call the vechicleType() function we don't have to pass in a value for "vehicle" it inherits it from the outside.

![Intro Image Edited](https://github.com/MichaelBaynon/Closures-in-JavaScript-Lesson-Plan/blob/main/basicOutput.png)

___________________________________________________________________________________________________________________________


If we were to redefine vehicle outside the function but beneath the variable declaration we could actually change the value of the console.log as shown here:

![Intro Image Edited](https://github.com/MichaelBaynon/Closures-in-JavaScript-Lesson-Plan/blob/main/basicAdded.png)

![Intro Image Edited](https://github.com/MichaelBaynon/Closures-in-JavaScript-Lesson-Plan/blob/main/basicAddedOutput.png)

___________________________________________________________________________________________________________________________

# Practical Example

Suppose were using jquery and we were going to make an ajax request as seen here.

![Intro Image Edited](https://github.com/MichaelBaynon/Closures-in-JavaScript-Lesson-Plan/blob/main/practicalExample.png)

Since Javascript reads top to bottom and only reads what is immediatly called we could in theory have our ajax request be made on click.

So the time line of our Javascript file in practice is as follows:

  * request function is created but not ran 
  
  * user clicks button which initiates ajax request 
  
  * ajax request can then go access the "key" variable declared before it 
  
  ___________________________________________________________________________________________________________________________
  
  # Activity 1 Example
  
  For this example we are creating a directory for our company.
  
  ![Intro Image Edited](https://github.com/MichaelBaynon/Closures-in-JavaScript-Lesson-Plan/blob/main/directory.png)
  
  We want our "name" variable passed along as a closure which we are actually doing succesfully as seen here:

![Intro Image Edited](https://github.com/MichaelBaynon/Closures-in-JavaScript-Lesson-Plan/blob/main/directoryOutput2.png)

 ___________________________________________________________________________________________________________________________

# Activity 1 Unsolved
Your boss came up to you and told you that for some reason she is not able to find the "Closure" for name, job, or salary for any of the employees in the directory even worse now the console.dir() is returning undefined.

In your groups using the example above as your guide figure out why your boss can't find any Closures and then solve the issue.

```
function bio() {
  let name = "Amy";
  let job = "accountant";
  let salary = "100,000";
 // add code that will bring these variables into Closure
}

console.dir(bio());
```

Open up the response in the console and locate the "Closure" portion if you believe you have finished. If you see the "name", "job" and "salary" you are done :)

 ___________________________________________________________________________________________________________________________

# Activity 1 Solved

Since your boss had not console.logged or used the variables anywhere Javascript had no need to pass those variables along as closure.

Therefore the solution is as simple as console.logging the variable in a return function as follows:

```
function bio() {
  let name = "Amy";
  let job = "accountant";
  let salary = "100,000";
  return function response() {
    console.log(name, job, salary);
  };
}

console.dir(bio());
```
