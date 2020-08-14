# Lesson 2 Data types and variables
## Section 16 Booleans

A boolean variable can take either of two values - `true `or `false`

```
var studentName = "John";
var haveEnrolledInCourse = true;
var haveCompletedTheCourse = false;
```
A boolean variable is mainly essential in evaluating the outcome of conditionals (comparisons). **The result of a comparison is always a boolean variable**

```
if (haveEnrolledInCourse){ 
    console.log("Welcome "+studentName+" to Udacity!"); // Will run only if haveEnrolledInCourse is true
}
```

```
var a = 10;
var b = 20;
// a comparison - we will study this in detail in upcoming lesson
if (a>b) // The outcome of a>b will be a boolean
    console.log("Variable `a` has higher value"); // if a>b is true
else 
    console.log("Variable `b` has higher value"); // if a>b is false
```
In general cases (regular equality check), a `true` corresponds to number 1, whereas `false` represents a number 0. For example:

```
if(1){
    console.log("This statement will always execute because conditional is set to 1 i.e., true");
}

if(0){
        console.log("This statement will NEVER execute because conditional is set to 0 i.e., false");
}
```

## Section 18 Null, Undefined and NaN

### What is NaN?

`NaN` stands for "Not-A-Number" and it's often returned indicating an error with number operations. For instance, if you wrote some code that performed a math calculation, and the calculation failed to produce a valid number, `NaN` might be returned.

```
// calculating the square root of a negative number will return NaN
Math.sqrt(-10)

// trying to divide a string by 5 will return NaN
"hello"/5`
```

## Section 19 Equality

So far, you’ve seen how you can use `==` and `!=` to compare numbers and strings for equality. However, if you use `==` and `!=` in situations where the values that you're comparing have different data-types, it can lead to some interesting results. 

`"1" == 1`
> Returns: true

and

`0 == false`
> Returns: true. The == operator is unable to differentiate 0 from false.

`' ' == false`
>Returns: true. Both the operands on either side of the == operator are first converted to zero, before comparison.

All of the above three evaluate to true. The reason for such interesting outcomes is *Type Conversion*. In the case of regular comparison, the operands on either side of the `== ` operator are first converted to numbers, before comparison. Therefore, a `' '`, `false`, and `0` are all considered equal. Similarly, a `'1'` and `1` are also considered equal. If we don't want to convert the operands, before comparison, we have to use a **strict comparison**  `===`

### Implicit Type coercion

JavaScript is known as a loosely typed language. This means that when you’re writing JavaScript code, you do not need to specify data types. Instead, when your code is interpreted by the JavaScript engine it will automatically be converted into the "appropriate" data type. This is called implicit type coercion and you’ve already seen examples like this before when you tried to concatenate strings with numbers.

`"julia" + 1`
> Returns: "julia1"`

In this example, JavaScript takes the string `"julia"` and adds the number `1` to it resulting in the string `"julia1"`. In other programming languages, this code probably would have returned an error, but in JavaScript the number `1` is converted into the string `"1"` and then is concatenated to the string `"julia"`.

It’s behavior like this which makes JavaScript unique from other programming languages, but it can lead to some quirky behavior when doing operations and comparisons on mixed data types

#### Example of strongly typed programming language code
```
int count = 1;
string name = "Julia";
double num = 1.2932;
float price = 2.99;
```

#### Equivalent code in JavaScript
```
// equivalent code in JavaScript
var count = 1; 
var name = "Julia";
var num = 1.2932;
var price = 2.99;
```
In the example below, JavaScript takes the string `"1"`, converts it to` true`, and compares it to the boolean `true`.

`"1" == true`
> Returns: true

When you use the `==` or `!=` operators, JavaScript first converts each value to the same type (if they’re not already the same type); this is why it's called "type coercion"! This is often not the behavior you want, and it’s actually considered bad practice to use the `==` and `!=` operators when comparing values for equality.

#### Stricy Equality

Instead, in JavaScript it’s better to use **strict equality** to see if numbers, strings, or booleans, etc. are identical in *type* and *value* without doing the type conversion first. 

`"1" === 1`
> Returns: false

This returns false because the string `"1"` is not the same type and value as the number` 1`.

`0 === false`
> Returns: false

This returns false because the number `0` is not the same type and value as the boolean false. Just like strict equality operator, there is also a strict non-equality operator `!==` that can be used instead of `!=` if you don't want a type-conversion, before comparison. For example,

`0 !== true`
> Returns: true

and

`'1' !== 1`
> Returns: true


### Section 22 Out to dinner

Directions:`
Create a variable called `bill` and assign it the result of `10.25 + 3.99 + 7.15` (don't perform the calculation yourself, let JavaScript do it!). Next, create a variable called `tip` and assign it the result of multiplying `bill` by a 15% tip rate. Finally, add the `bill` and `tip` together and store it into a variable called `total`.

Print the `total` to the JavaScript console.

```
var bill = (10.25 + 3.99 + 7.15);

var tip = (bill * 0.15);

var total = (bill + tip);

console.log("$" + total.toFixed(2));
```

> Returns $24.60

### Section 23 Mad libs

[Madlibs] is a word game where players have fun substituting words for blanks in a story. For this exercise, use the adjective variables below to fill in the blanks and complete the following message.
```
"The Intro to JavaScript course is __________. James and Julia are so __________. I cannot wait to work through the rest of this __________ content!"
```
```
var adjective1 = "amazing";
var adjective2 = "fun";
var adjective3 = "entertaining";
```
Assign the resulting string to a variable called `madLib`.

```
var adjective1 = "amazing";
var adjective2 = "fun";
var adjective3 = "entertaining";
var madLib = "The Intro to JavaScript course is "+ adjective1 +". James and Julia are so "+ adjective2 +". I cannot wait to work through the rest of this "+ adjective3 +" content!";
console.log(madLib);
```

### Section 24 One Awesome Message

Here are two awesome messages:
```
Hi, my name is Julia. I love cats. In my spare time, I like to play video games.
Hi, my name is James. I love baseball. In my spare time, I like to read.
```
Declare and assign values to three variables for each part of the sentence that changes (`firstName`, `interest`, and  `hobby`).

Use your variables and string concatenation to create your own awesome message and store it in an `awesomeMessage` variable. Finally, print your awesome message to the JavaScript console.

```
var firstName = "James";
var interest = "baseball";
var hobby = "read";

var awesomeMessage = "Hi, my name is " + firstName + ". I love " + interest + ". In my spare time, I like to " + hobby + ".";
console.log(awesomeMessage);
```


