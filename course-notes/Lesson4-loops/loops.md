# Lesson 4 Loops

## Section 2 & 3 While loops

### Parts of a while loop

There are many different kinds of loops, but they all essentially do the same thing: they repeat an action some number of times.

Three main pieces of information that any loop should have are:

**When to start**: The code that sets up the loop — defining the starting value of a variable for instance.
****When to stop**: The logical condition to test whether the loop should continue.
**How to get to the next item**: The incrementing or decrementing step — for example, x = x * 3 or x = x - 1
Here's a basic while loop example that includes all three parts.
```
var start = 0; // when to start
while (start < 10) { // when to stop
  console.log(start);
  start = start + 2; // how to get to the next item
}
```
>Prints:
>0
>2
>4
>6
>8

If a loop is missing any of these three things, then you might find yourself in trouble. For instance, a missing stop condition can result in a loop that never ends!


### Section 4 JuliaJames/FizzBuzz

```

var x = 1;

// while loop with a stop condition
while (x <= 20) {
    if (x % 3 === 0 && x % 5 === 0) {
        console.log("JuliaJames");
    }else if (x % 5 === 0) {
        console.log("James");
    }else if (x % 3 === 0) {
        console.log("Julia");
    }
    else {
        console.log(x);
    }
    // increment x at the end of each loop
    x = x + 1 ; 
}
```

### Section 5 Bottle of Juice

```
while (num >=1) {
    // Last iteration. Note occurances of bottle, bottle, bottleS
    if (num === 1) {
        console.log(num + " bottle of juice on the wall! "
                    + num + " bottle of juice! Take one down, pass it around... "
                    + (num-1) + " bottles of juice on the wall!");
    }
    // Second-last iteration. Note occurances of bottleS, bottleS, bottle
    else if (num === 2){
        console.log(num + " bottles of juice on the wall! "
                    + num + " bottles of juice! Take one down, pass it around... "
                    + (num-1) + " bottle of juice on the wall!");
    }
    // All other iterations. Note occurances of bottleS, bottleS, bottleS
    else {
        console.log(num + " bottles of juice on the wall! "
                    + num + " bottles of juice! Take one down, pass it around... "
                    + (num-1) + " bottles of juice on the wall!");
    }
    num = num - 1;
}
```
### Section 6 Countdown

```
n = 60

// While loop with a stop condition
while (n >= 0) {
    if (n === 50) {
        console.log("Orbiter transfers from ground to internal power");
    }
    else if (n === 31) {
        console.log("Ground launch sequencer is go for auto sequence start");
    }
    else if (n === 16) {
        console.log("Activate launch pad sound suppression system");
    }
    else if (n === 10) {
        console.log("Activate main engine hydrogen burnoff system");
    }
    else if (n === 6) {
        console.log("Main engine start");
    }
    else if (n === 0) {
        console.log("Solid rocket booster ignition and liftoff!");
    }
    else{
        console.log("T-"+n+" seconds");
    }

    //Never forget to decrement/increment the iteration variable in a while loop
    // Otherwise, you loop will run infinite iterations
    n = n-1;
}
```

### Section 8 Parts of a For loop
```
for ( start; stop; step ) {
  // do this thing
}
```
Here's an example of a for loop that prints out the values from 0 to 5. Notice the semicolons separating the different statements of the for loop:` var i = 0; i < 6; i = i + 1`
```
for (var i = 0; i < 6; i = i + 1) {
  console.log("Printing out i = " + i);
}
```
>Prints:
>Printing out i = 0
>Printing out i = 1
>Printing out i = 2
>Printing out i = 3
>Printing out i = 4
>Printing out i = 5

### Section 8 Nested Loops

```
for (var x = 0; x < 5; x = x + 1) {
  for (var y = 0; y < 3; y = y + 1) {
    console.log(x + "," + y);
  }
}
```
```
Prints:
0, 0
0, 1
0, 2
1, 0
1, 1
1, 2
2, 0
2, 1
2, 2
3, 0
3, 1
3, 2
4, 0
4, 1
4, 2
```

Notice the order that the output is being displayed.

For each value of `x` in the outer loop, the inner for loop executes completely. The outer loop starts with `x = 0`, and then the inner loop completes its cycle with all values of `y`:

`x = 0 and y = 0, 1, 2 // corresponds to (0, 0), (0, 1), and (0, 2)`
Once the inner loop is done iterating over `y`, then the outer loop continues to the next value, `x = 1`, and the whole process begins again.
```
x = 0 and y = 0, 1, 2 // (0, 0) (0, 1) and (0, 2)
x = 1 and y = 0, 1, 2 // (1, 0) (1, 1) and (1, 2)
x = 2 and y = 0, 1, 2 // (2, 0) (2, 1) and (2, 2)
etc.
```
### Section 10 Increment and Decrement
```
x++ or ++x // same as x = x + 1 [x++ shows original value then increments by 1 ++x simply increments by 1 without returning the original value]
x-- or --x // same as x = x - 1
x += 3 // same as x = x + 3
x -= 6 // same as x = x - 6
x *= 2 // same as x = x * 2
x /= 5 // same as x = x / 5
```

### Section 11 Chnaging the loop

```
/*
 * Programming Quiz: Changing the Loop (4-4)
 */
/*
 * QUIZ REQUIREMENTS
 * - Your code should use a `for` loop
 * - Your `for` loop should specify a starting condition `x` with the value of `9`
 * - Your `for` loop should have a stop condition for the value of `x`
 * - Your `for` loop should decrement `x` each time it executes
 * - Your code should produce the expected output, as explained above
 * - Your code should not be empty
 * - BE CAREFUL ABOUT THE PUNCTUATION AND THE EXACT WORDS TO BE PRINTED.
 */
 
// rewrite the while loop as a for loop
//var x = 9;
//while (x >= 1) {
 //   console.log("hello " + x);
 //   x = x - 1;
//}

for (var x=9; x >=1; x=x-1){
    console.log("hello " + x);
}
```
#### More to Read - Scope and Variable Declaration

##### What is a "Scope"?
The scope is defined as a specific portion of the code. There are three types of scope in Javascript

**Global scope** - When a particular variable is visible (can be used) anywhere in the code. Such a variable is generally called as **Global variable**.
**Function scope** - When a particular variable is visible (can be used) within a particular function only. Such a variable is generally called as Local **variable**.
**Block scope** - When a particular variable is visible (can be used) within a pair of `{ . . . } `only.

```
/*
 * Global scope. 
 * This variable declared outside of any function is called Global variable. 
 * Hence, you can use this anywhere in the code
 */
var opinion = "This nanodegree is amazing";

// Function scope
function showMessage() {
    // Local variable, visible within the function `showMessage`
    var message = "I am an Udacian!"; 

    // Block scope
    {
          let greet = "How are you doing?";
        /*
         * We have used the keyword `let` to declare a variable `greet` because variables declared with the `var` keyword can not have Block Scope. 
         */
    } // block scope ends

    console.log( message ); // OK
    console.log( greet ); // ERROR. 
    // Variable greet can NOT be used outside the block

    console.log( opinion ); // OK    to use the gobal variable anywhere in the code

} // function scope ends
```
##### Variable Declaration
There are three ways to declare a variable:
`
`let` - It a new way to declare a variable in any scope - Global, Local, or Block. The value of this variable can be changed or reassigned anytime within its scope.
`const` - It is also a way to declare constants in any scope - Global, Local, or Block. Once you are assigned a value to a const variable, the value of this variable CANNOT be changed or reassigned throughout the code.
`var` - This is the old way of declaring variables in only two scope - Global, or Local. Variables declared with the var keyword can not have Block Scope. The value of this variable can be changed or reassigned anytime within its scope.

### Section 15 Find my seat

```

var row = 0;  // initial value of the row
var seat = 0; // initial value of the seat within a row

// One loop inside another is called Nested loop.
// Outer `for` loop, to iterate over the rows
for (row = 0; row <= 25; row++){

    // Inner `for` loop, to iterate over the seats within a row
    // In this loop, the value of `row` variable would change only after 100 iterations
    for(seat = 0; seat <= 99; seat++){
        console.log(row+"-"+seat);
    }
}
```
