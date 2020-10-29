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

 ___________________________________________________________________________________________________________________________
 
 # Activity 2 Unsolved
 
 Your company is having a deal on shirts so whenever a customer buys a shirt they get 3 free shirts per 1 purchased.
 
 Your job is to right code to handle the total shirts purchased and multiply that times the freeShirts variable.

### Bonus

Sadly this sale was just way to costly so your company asked you to reduce the sale to 2 shirts = for every one purchased

Without directly changing the initial freeShirts variable set on line 1 change the sale to be 2 times instead of 3 times

```
var freeShirts = 3;

function totalShirts() {
  // create a variable that represents how many shirts a costumer purchased
  //for now this can be hardcoded to any number you would like
  // then return the product of the freeShirts variable and your new variable using multiplication
}

console.dir(totalShirts());
```

 ___________________________________________________________________________________________________________________________
 
 # Activity 2 Solved

Technically any function where you use a variable declared outside of said function is a Closure.

This is an example of closure because it uses the freeShirts variable declared globally inside of the function. Since the sale is just 3 shirts = to the customers 1 shirt purchased that value never has to change.

But because all different customers can buy a different quantity of shirts that is a value discoverd in the function and then the math is done there.

```
var freeShirts = 3;

function totalShirts() {
  // create a variable that represents how many shirts a costumer purchased
  //for now this can be hardcoded to any number you would like
  // then return the sum of the freeShirts variable and your new variable
  var shirtsPurchased = 5
  return freeShirts * shirtsPurchased
}

// BONUS  var freeShirts = 2

console.dir(totalShirts());
```

 ___________________________________________________________________________________________________________________________
 
 # Activity 3 Unsolved

Using the given code write 2 new variables. 1 for Junior Developers base salary  & another for Senior Developers base salary.

using "console.log" pass the developers their bonuses.

```
var compensation = function (salary) {
  var totalCompensation = function (bonus) {
    return salary + bonus;
  };

  return totalCompensation;
};

// variables that gives juniors and senior their salaries

// HINT "new" keyword can be helpful here

// console logs that give the developers their bonuses

```

 ___________________________________________________________________________________________________________________________
 
 # Activity 3 Solved

Using the new keyword we can pass a new instance of compensation and then pass in a value for each developer type.

In our console.logs we can pass in our bonuses which later gets used in our totalCompensation function to replace "bonus"

Lastly we add both the salary and bonus which give us our "totalCompensation"

```
var compensation = function (salary) {
  var totalCompensation = function (bonus) {
    return salary + bonus;
  };

  return totalCompensation;
};

var juniorSalary = new compensation(70000);
var seniorSalary = new compensation(100000);

console.log(juniorSalary(15000));
console.log(seniorSalary(30000));
```

![Intro Image Edited](https://github.com/MichaelBaynon/Closures-in-JavaScript-Lesson-Plan/blob/main/example3Edited.png)

 ___________________________________________________________________________________________________________________________
 
 # Summary 

Again as described by Mozilla:

A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function’s scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time.

 ___________________________________________________________________________________________________________________________

# Resources

https://developer.mozilla.org/en-US/docs/Glossary/Scope

https://www.w3schools.com/js/js_scope.asp

https://www.w3schools.com/js/js_function_closures.asp#:~:text=This%20is%20called%20a%20JavaScript,the%20parent%20function%20has%20closed.

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures

https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-closure-b2f0d2152b36

https://www.freecodecamp.org/news/javascript-closure-tutorial-with-js-closure-example-code/
