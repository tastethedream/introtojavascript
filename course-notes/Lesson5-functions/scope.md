# Intro to JavaScript

## Lesson 5 Functions

### Section 9 Scope

The part of a program where a variable or function is visable or accessible.

### Section 11 Shadowing

In computer programming, variable shadowing occurs when a variable declared within a certain scope (decision block, method, or inner class) has the same name as a variable declared in an outer scope. At the level of identifiers (names, rather than variables), this is known as name masking. This outer variable is said to be shadowed by the inner variable, while the inner identifier is said to mask the outer identifier. This can lead to confusion, as it may be unclear which variable subsequent uses of the shadowed variable name refer to, which depends on the name resolution rules of the language

#### What you've learned so far:
 * If an identifier is declared in global scope, it's available everywhere.
* If an identifier is declared in function scope, it's available in the function it was declared in (even in functions declared inside the function).
* When trying to access an identifier, the JavaScript Engine will first look in the current function. If it doesn't find anything, it will continue to the next outer function to see if it can find the identifier there. It will keep doing this until it reaches the global scope.
* Global identifiers are a bad idea. They can lead to bad variable names, conflicting variable names, and messy code.

### Section 14 Hoisting

Before any JS is executed, all function declarations are **hoisted** to the top of their current scope.

**Declare fuctions at the top of your script**

**Declare variables at the top of your functions**

#### What you've learned so far:

- JavaScript hoists function declarations and variable declarations to the top of the current scope.
- Variable assignments are not hoisted.
- Declare functions and variables at the top of your scripts, so the syntax and behavior are consistent with each other.

### Section 16 Build a triangle
```
// creates a line of * for a given length
function makeLine(length) {
    var line = "";
    for (var j = 1; j <= length; j++) {
        line += "* ";
    }
    return line + "\n";
}

// your code goes here.  Make sure you call makeLine() in your own code.

function buildTriangle(length){
    var triangle = "";
    var line = 1;
    
    for (line=1; line<=length; line++){
        triangle = triangle + makeLine(line);
    }
    return triangle;
}

console.log(buildTriangle(10))
```
prints
```
* 
* * 
* * * 
* * * * 
* * * * * 
* * * * * * 
* * * * * * * 
* * * * * * * * 
* * * * * * * * * 
* * * * * * * * * * 
```
### Section 17 Function Expessions

In JavaScript, you can also store functions in variables. When a function is stored inside a variable it's called a **function expression**.

```
var catSays = function(max) {
  var catMessage = "";
  for (var i = 0; i < max; i++) {
    catMessage += "meow ";
  }
  return catMessage;
};
```
Notice how the `function` keyword no longer has a name.

```
var catSays = function(max) { 
  // code here 
};
```
It's an **anonymous function**, a function with no name, and you've stored it in a variable called `catSays`.

And, if you try accessing the value of the variable `catSays`, you'll even see the function returned back to you.

`catSays;`
Returns:
```
function(max) {
  var catMessage = ""
  for (var i = 0; i < max; i++) {
    catMessage += "meow ";
  }
  return catMessage;
}
```
#### Function expressions amd hosting

Deciding when to use a function expression and when to use a function declaration can depend on a few things, and you will see some ways to use them in the next section. But, one thing you'll want to be careful of is hoisting.

All*function declarations* are hoisted and loaded before the script is actually run. Function expressions are **not** hoisted, since they involve variable assignment, and only variable declarations are hoisted. The function expression will not be loaded until the interpreter reaches it in the script.

### Section 18 Patterns with function expressions

#### Functions as parameters

Being able to store a function in a variable makes it really simple to pass the function into another function. A function that is passed into another function is called a **callback**. Let's say you had a `helloCat()` function, and you wanted it to return "Hello" followed by a string of "meows" like you had with `catSays`. Well, rather than redoing all of your hard work, you can make `helloCat()` accept a callback function, and pass in` catSays`.
```
// function expression catSays
var catSays = function(max) {
  var catMessage = "";
  for (var i = 0; i < max; i++) {
    catMessage += "meow ";
  }
  return catMessage;
};

// function declaration helloCat accepting a callback
function helloCat(callbackFunc) {
  return "Hello " + callbackFunc(3);
}

// pass in catSays as a callback function
helloCat(catSays);
```

**I do not understand what is happening here??? what is += not sure aht is happening with the call back function**

#### Inline function expressions

A function expression is when a function is assigned to a variable. And, in JavaScript, this can also happen when you pass a function *inline* as an argument to another function. Take the `favoriteMovie` example for instance:
```
// Function expression that assigns the function displayFavorite 
// to the variable favoriteMovie
var favoriteMovie = function displayFavorite(movieName) {
  console.log("My favorite movie is " + movieName);
};

// Function declaration that has two parameters: a function for displaying
// a message, along with a name of a movie
function movies(messageFunction, name) {
  messageFunction(name);
}

// Call the movies function, pass in the favoriteMovie function and name of movie
movies(favoriteMovie, "Finding Nemo");
```
>Returns: My favorite movie is Finding Nemo

But you could have bypassed the first assignment of the function, by passing the function to the `movies()` function inline.
```
/ Function declaration that takes in two arguments: a function for displaying
// a message, along with a name of a movie
function movies(messageFunction, name) {
  messageFunction(name);
}

// Call the movies function, pass in the function and name of movie
movies(function displayFavorite(movieName) {
  console.log("My favorite movie is " + movieName);
}, "Finding Nemo");
```
>Returns: My favorite movie is Finding Nemo

#### Why use anonymous inline function expressions?

Using an anonymous inline function expression might seem like a very not-useful thing at first. Why define a function that can only be used once and you can't even call it by name?

Anonymous inline function expressions are often used with function callbacks that are probably not going to be reused elsewhere. Yes, you could store the function in a variable, give it a name, and pass it in like you saw in the examples above. However, when you know the function is not going to be reused, it could save you many lines of code to just define it inline.

#### What you've learned so far:

**Function Expression**: When a function is assigned to a variable. The function can be named, or anonymous. Use the variable name to call a function defined in a function expression.
```
// anonymous function expression
var doSomething = function(y) {
  return y + 1;
};
```
```
// named function expression
var doSomething = function addOne(y) {
  return y + 1;
};

// for either of the definitions above, call the function like this:
doSomething(5);
```
>Returns: 6

You can even pass a function into another function inline. This pattern is commonly used in JavaScript, and can be helpful streamlining your code.
```
// function declaration that takes in two arguments: a function for displaying
// a message, along with a name of a movie
function movies(messageFunction, name) {
  messageFunction(name);
}

// call the movies function, pass in the function and name of movie
movies(function displayFavorite(movieName) {
  console.log("My favorite movie is " + movieName);
}, "Finding Nemo");
```
#### named function example
```
var cry = function cries(){
    var noise ="boohoo!"
    return noise;
};
console.log(cry());
```

#### inline function example

```
function emotions(myString, myFunc) {
    console.log("I am " + myString + ", " + myFunc(2));
}

// your code goes here
// Call the emotions() function with two arguments
// Argument 1 - "happy" string
// Argument 2 - an inline function expression
emotions ("happy", function(number){
    var noise = "";
    
    for (var i = 0; i< number; i++){
        noise = noise + "ha"
    }
    
    noise = noise +"!";
    return noise;
});
```
> returns I am happy, haha!