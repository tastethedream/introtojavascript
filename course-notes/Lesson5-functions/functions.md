# Intro To JavaScript

## Lesson 5 Functions

### Section 3 Declaring Functions

**Functions** allow you to package up lines of code that you can use (and often reuse) in your programs.

Sometimes they take **parameters** like the pizza button from the beginning of this lesson. `reheatPizza()` had one parameter: the number of slices.
```
function reheatPizza(numSlices) {
  // code that figures out reheat settings!
}
```
The `reverseString(`) function that you saw also had one parameter: the string to be reversed.
```
function reverseString(reverseMe) {
  // code to reverse a string!
}
```
In both cases, the parameter is listed as a variable after the function name, inside the parentheses. And, if there were multiple parameters, you would just separate them with commas.
```
function doubleGreeting(name, otherName) {
  // code to greet two people!
}
```
But, you can also have functions that don't have any parameters. Instead, they just package up some code and perform some task. In this case, you would just leave the parentheses empty. Take this one for example. Here's a simple function that just prints out `"Hello!"`.

```
// accepts no parameters! parentheses are empty
function sayHello() {
  var message = "Hello!"
  console.log(message);
}
```
If you tried pasting any of the functions above into the JavaScript console, you probably didn't notice much happen. In fact, you probably saw undefined returned back to you. `undefined` is the default return value on the console when nothing is explicitly returned using the special `return` keyword.

#### Return statements

In the `sayHello()` function above, a value is printed to the console with `console.log`, but not explicitly returned with a **return statement.** You can write a return statement by using the `return` keyword followed by the expression or value that you want to return.
```
// declares the sayHello function
function sayHello() {
  var message = "Hello!"
  return message; // returns value instead of printing it
}
```
#### How to run a function


Now, to get your function to do something, you have to **invoke** or **call** the function using the function name, followed by parentheses with any **arguments** that are passed into it. Functions are like machines. You can build the machine, but it won't do anything unless you also turn it on. Here's how you would call the `sayHello()` function from before, and then use the return value to print to the console:
```
// declares the sayHello function
function sayHello() {
  var message = "Hello!"
  return message; // returns value instead of printing it
}

// function returns "Hello!" and console.log prints the return value
console.log(sayHello());
Prints: "Hello!"
```

#### Parameters vs. Arguments

At first, it can be a bit tricky to know when something is either a **parameter** or an **argument**. The key difference is in where they show up in the code. A **parameter** is always going to be a **variable name** and appears in the **function declaration**. On the other hand, an **argument** is always going to be a **value** (i.e. any of the JavaScript data types - a number, a string, a boolean, etc.) and will always appear in the **code** when the function is **called** or **invoked**.


### Section 5 Laugh It Off

```
/*
 * Programming Quiz: Laugh it Off 1 (5-1)
 */

/*
 * QUIZ REQUIREMENTS
 * - Your code should have a `laugh()` function
 * - Your `laugh()` function should return the correct output
 * - Your code should print `\"hahahahahahahahahaha!\"` by calling the `laugh()` function inside `console.log()`
 * - BE CAREFUL ABOUT THE PUNCTUATION AND THE EXACT WORDS TO BE PRINTED.
 */


// your code goes here
function laugh(){
    const noise =  "hahahahahahahahahaha!"
    return noise;
}

console.log(laugh());

```
### Section 6 Laugh it off 2

```
var sound = "" ; 
function laugh(num) {
    for (var x = 0 ; x < num ; x++) {
        sound = sound + "ha" ;  
    }
    sound = sound +"!"; 
    return sound; 
}

console.log(laugh(3)) ;
```
### Section 7 Return values

A function's return value can be stored in a variable or reused throughout your program as a function argument. Here, we have a function that adds two numbers together, and another function that divides a number by 2. We can find the average of 5 and 7 by using the add() function to add a pair of numbers together, and then by passing the sum of the two numbers add(5, 7) into the function divideByTwo() as an argument.

And finally, we can even store the final answer in a variable called `average` and use the variable to perform even more calculations in more places!

```
/ returns the sum of two numbers
function add(x, y) {
  return x + y;
}


// returns the value of a number divided by 2
function divideByTwo(num) {
  return num / 2;
}


var sum = add(5, 7); // call the "add" function and store the returned value in the "sum" variable
var average = divideByTwo(sum); // call the "divideByTwo" function and store the returned value in the "average" variable
```

















