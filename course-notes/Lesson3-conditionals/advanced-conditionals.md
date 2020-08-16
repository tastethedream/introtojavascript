# Lesson 3 Conditionals
## Section 16 Truthy snd falsy

Every value in JavaScript has an inherent boolean value. When that value is evaluated in the context of a boolean expression, the value will be transformed into that inherent boolean value.

### Falsy values
A value is **falsy** if it converts to` false` when evaluated in a boolean context. For example, an empty String` ""` is falsy because, `""` evaluates to `false`. You already know if...else statements, so let's use them to test the truthy-ness of `""`.
```
if ("") {
    console.log("the value is truthy");
} else {
    console.log("the value is falsy");
}
```
> Returns: "the value is falsy"

#### Here’s the list of all of the falsy values:

the Boolean value `false`
the `null` type
the `undefined` type
the number `0`
the empty string `""`
the odd value `NaN` (stands for "not a number", check out the NaN MDN article)

### Truthy values

A value is **truthy** if it converts to `true `when evaluated in a boolean context. For example, the number` 1 `is truthy because,` 1` evaluates to true.

```
if (1) {
    console.log("the value is truthy");
} else {
    console.log("the value is falsy");
}
```
> Returns "the value is truthy"

Here are some other examples of truthy values:
```
true
42
"pizza"
"0"
"null"
"undefined"
{}
[]
```
**Essentially, if it's not in the list of falsy values, then it's truthy!**


## Section 17 Ternary Operator

Sometimes, you might find yourself with the following type of conditional.
```
var isGoing = true;
var color;

if (isGoing) {
  color = "green";
} else {
  color = "red";
}

console.log(color);
```
> Prints: "green"

 the variable` color` is being assigned to either` "green"` or `"red"` based on the value of `isGoing`. This code works, but it’s a rather lengthy way for assigning a value to a variable. Thankfully, in JavaScript there’s another way.

TIP: Using `if(isGoing)` is the same as using `if(isGoing === true)`. Alternatively, using `if(!isGoing)` is the same as using `if(isGoing === false)`.


### Ternary operator
The **ternary operator** provides you with a shortcut alternative for writing lengthy if...else statements.

`conditional `?` (if condition is true) : (if condition is false)`

To use the ternary operator, first provide a conditional statement on the left-side of the `?`. Then, between the `?` and `:` write the code that would run if the condition is true and on the right-hand side of the `:` write the code that would run if the condition is false. For example, you can rewrite the example code above as:

```
var isGoing = true;
var color = isGoing ? "green" : "red";
console.log(color);
```
> Prints: "green"
This code not only replaces the conditional, but it also handles the variable assignment for `color`.

If you breakdown the code, the condition` isGoing` is placed on the left side of the `?`. Then, the first expression, after the `?`, is what will be run if the condition is true and the second expression after the, `:`, is what will be run if the condition is false.

## Section 18 the food chain

```
var eatsPlants = false;
var eatsAnimals = true;

var category = eatsPlants ? (eatsAnimals ? "omnivore" : "herbivore") : (eatsAnimals ? "carnivore" : "undefined");


console.log(category);
```

## Section 18 Switch Statements

A **switch statement** is an another way to chain multiple` else if` statements that are based on the same value without using conditional statements. Instead, you just *switch *which piece of code is executed based on a value.
```
switch (option) {
  case 1:
    console.log("You selected option 1.");
  case 2:
    console.log("You selected option 2.");
  case 3:
    console.log("You selected option 3.");
  case 4:
    console.log("You selected option 4.");
  case 5:
    console.log("You selected option 5.");
  case 6:
    console.log("You selected option 6.");
}
```

Here, each` else if` statement `(option === [value])` has been replaced with a` case` clause `(case [value]:)` and those clauses have been wrapped inside the switch statement.

When the switch statement first evaluates, it looks for the first `case `clause whose expression evaluates to the same value as the result of the expression passed to the switch statement. Then, it transfers control to that `case` clause, executing the associated statements.

So, if you set `option` equal to` 3`...
```
var option = 3;

switch (option) {
  ...
}
```
>Prints:
>You selected option 3.
>You selected option 4.
>You selected option 5.
>You selected option 6.

...then the switch statement prints out options 3, 4, 5, and 6.

But that’s not exactly like the original `if...else `code at the top? So what’s missing?

### Break statement

The **break statement** can be used to terminate a switch statement and transfer control to the code following the terminated statement. By adding a `break` to each `case` clause, you fix the issue of the switch statement falling-through to other case clauses.
```
var option = 3;

switch (option) {
  case 1:
    console.log("You selected option 1.");
    break;
  case 2:
    console.log("You selected option 2.");
    break;
  case 3:
    console.log("You selected option 3.");
    break;
  case 4:
    console.log("You selected option 4.");
    break;
  case 5:
    console.log("You selected option 5.");
    break;
  case 6:
    console.log("You selected option 6.");
    break; // technically, not needed
}
```
>Prints: You selected option 3.

## Section 20 Falling Through

In some situations, you might want to leverage the "falling-through" behavior of switch statements to your advantage.

For example, when your code follows a hierarchical-type structure.
```
var tier = "nsfw deck";
var output = "You’ll receive "

switch (tier) {
  case "deck of legends":
    output += "a custom card, ";
  case "collector's deck":
    output += "a signed version of the Exploding Kittens deck, ";
  case "nsfw deck":
    output += "one copy of the NSFW (Not Safe for Work) Exploding Kittens card game and ";
  default:
    output += "one copy of the Exploding Kittens card game.";
}

console.log(output);
```
>Prints: You’ll receive one copy of the NSFW (Not Safe for Work) Exploding Kittens card game and one copy of the Exploding Kittens card game.

In this example, based on the successful Exploding Kittens Kickstarter campaign (a hilarious card game created by Elan Lee), each successive tier builds on the next by adding more to the output. Without any break statements in the code, after the switch statement jumps to the `"nsfw deck`", it continues to fall-through until reaching the end of the switch statement.

Also, notice the default case.
```
var tier = "none";
var output = "You’ll receive ";

switch (tier) {
  ... 
  default:
    output += "one copy of the Exploding Kittens card game.";
}

console.log(output);
```
>Prints: You’ll receive one copy of the Exploding Kittens card game.

You can add a `default` case to a switch statement and it will be executed when none of the values match the value of the switch expression.

### Section 21 Back to school

```
switch (education) {
    case "no high school diploma":
        salary = 25636;
        break;
    case "a high school diploma":
        salary = 35256;
        break;
    case "an Associate's degree":
        salary = 41496;
        break;
    case "a Bachelor's degree":
        salary = 59124;
        break;
    case "a Master's degree":
        salary = 69732;
        break;
    case "a Professional degree":
        salary = 89960;
        break;
    case "a Doctoral degree":
        salary = 84396;
        break;
}


console.log("In 2015, a person with "+education+" earned an average of $"+salary.toLocaleString("en-US")+"/year.");
```