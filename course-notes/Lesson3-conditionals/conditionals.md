# Lesson 3 Conditionals

## Section 4 If....else statements

**If...else statements** allow you to execute certain pieces of code based on a condition, 
```
if (/* this expression is true */) {
  // run this code
} else {
  // run this code
}
```
This is extremely helpful because it allows you to choose which piece of code you want to run based on the result of an expression. For example,
```
var a = 1;
var b = 2;

if (a > b) {
  console.log("a is greater than b");
} else {
  console.log("a is less than or equal to b");
}
```

A couple of important things to notice about `if...else` statements.
`
The value inside the `if` statement is always converted to true or false. Depending on the value, the code inside the `if` statement is run or the code inside the `else` statement is run, but not both. The code inside the `if` and `else` statements are surrounded by curly braces `{...}` to separate the conditions and indicate which code should be run.

**TIP**: When coding, sometimes you may only want to use an `if` statement. However, `if` you try to use only an `else` statement, then you will receive the error` SyntaxError: Unexpected token else`. You’ll see this error because `else` statements need an `if` statement in order to work. You can’t have an `else `statement without first having an `if `statement.

### Directions

Write an if...else statement that:

prints `"even"` if the number is an even number
prints `"odd"` if the number is an odd number
**Hint**: Use the` %` (modulo) operator to determine if a number is even or odd. The modulo operater takes two numbers and returns the remainder when the first number is divided by the second one:
```
console.log(12 % 3);
console.log(10 % 4);
```
>Result:
>0
>2

The answer for `12 % 3` is `0` because twelve divided by three has no remainder. `10 % 4` is `2` because ten divided by 4 has a remainder of two.

```
var number = 7;


if (number % 2 !== 0) {
    console.log("odd");
    
} else {
    console.log("even");
};
```
> Displays "odd"

### Section 7 Musical groups

Directions:
Write a series of conditional statements that:

Prints "not a group" if musicians is less than or equal to 0
Prints "solo" if musicians is equal to 1
Prints "duet" if musicians is equal to 2
Prints "trio" if musicians is equal to 3
Prints "quartet" if musicians is equal to 4
Prints "this is a large group" if musicians is greater than 4

```
var musicians = 2;


if (musicians <= 0) {
    console.log("not a group");
    
} 
if (musicians === 1) {
    console.log("solo");
    
} 
if (musicians === 2) {
    console.log("duet");
    
} 
if (musicians === 3) {
    console.log("trio");
    
} 
if (musicians === 4) {
    console.log("quartet");
    
} 
if(musicians > 4) {
    console.log("this is a large group");
};
```

> returns duet

### Section 8 Murder Mystery

#### Directions:

For this quiz, you're going to help solve a fictitious murder mystery that happened here at Udacity! A murder mystery is a game typically played at parties wherein one of the partygoers is secretly, and unknowingly, playing a murderer, and the other attendees must determine who among them is the criminal. It's a classic case of whodunnit.

Since this might be your first time playing a murder mystery, we've simplified things quite a bit to make it easier. Here's what we know! In this murder mystery there are:

**four rooms**: the ballroom, gallery, billiards room, and dining room,
**four weapon**s: poison, a trophy, a pool stick, and a knife,
and **four suspects**: Mr. Parkes, Ms. Van Cleve, Mrs. Sparr, and Mr. Kalehoff.
We also know that each weapon corresponds to a particular room, so...

the` poison` belongs to the `ballroom`,
the `trophy` belongs to the `gallery`,
the `pool stick` belongs to the `billiards room`,
and the` knife` belongs to the `dining room`.
And we know that each suspect was located in a specific room at the time of the murder.

`Mr. Parkes` was located in the` dining room`.
`Ms. Van Cleve` was located in the `gallery`.
`Mrs. Sparr` was located in the `billiards room`.
`Mr. Kalehoff` was located in the `ballroom`.
To help solve this mystery, write a combination of conditional statements that:

sets the value of `weapon` based on the `room` and
sets the value of `solved` to `true` if the value of `room` matches the `suspect's` room
Afterwards, use this template to print a message to the console if the mystery was solved:

`__________ did it in the __________ with the __________!`

What goes into the three blank spaces? You can fill in the blanks with the name of the suspect, the room, and the weapon! For example, an output string may look like:

`Mr. Parkes did it in the dining room with the knife!`

Be sure to watch out for any extra or missing characters (including spaces and punctuation marks) in your output string as well!

**TIP**: Test your code with different values. For example,

If  `room` equals `gallery` and suspect equals `Ms. Van Cleve`, then `Ms. Van Cleve did it in the gallery with the trophy!` should be printed to the console.