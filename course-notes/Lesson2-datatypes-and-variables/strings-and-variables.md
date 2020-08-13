# Lesson 2 Data Types & Variables

## Section 5 Strings

**TIP**: It is correct to either use double `"` or single `'` quotes with strings, as long as you're consistent. The JavaScript Udacity style guide for labs and projects suggests using single quotes to define string literals.

## Section 6 String Concatenation

Strings are a collection of characters enclosed inside double or single quotes. You can use strings to represent data like sentences, names, addresses, and more. Did you know you can even add strings together? In JavaScript, this is called **concatenating**. Concatenating two strings together is actually pretty simple!

`"Hello," + " New York City"`

> Returns: "Hello, New York City"

You will see other ways to concatenate and do even more with strings later in this course. But for now, practice using the addition `+` operator.

## Section 7 Variables

`var variableName = value;`

Storing the value of a string in a variable is like packing it away for later use

### Naming conventions

When you create a variable, you write the name of the variable using **camelCase** (the first word is lowercase, and all following words are uppercase). Also try to use a variable name that accurately, but succinctly describes what the data is about.

```
var totalAfterTax = 53.03; // uses camelCase if the variable name is multiple words
var tip = 8; // uses lowercase if the variable name is one word
```

Not using camelCase for your variables names is not going to necessarily break anything in JavaScript. But there are recommended style guides used in all programming languages that help keep code consistent, clean, and easy-to-read.


## Section 8 Temp conversion quiz

```
var celsius = 12;
var fahrenheit = (celsius * 1.8) + 32;

console.log(fahrenheit);
```

## Section 9 String Index

Did you know that you can access individual characters in a string? To access an individual character, you can use the character's location in the string, called its **index**. Just put the index of the character inside square brackets (starting with `[0] `as the first character) immediately after the string. For example:

`"James"[0];`
> Returns: "J"

or more commonly, you will see it like this, using a variable:

```
var name = "James";
name[0];
```
> Returns: "J"

**remember to count the spaces between words when indexing**

## Section 10 Escaping Strings

`"The man whispered, "please speak to me.""`
> Uncaught SyntaxError: Unexpected identifier

If you try to use quotes within a string, you will receive a `SyntaxError`.

Because you need to use quotes to denote the beginning and end of strings, the JavaScript engine misinterprets the meaning of your string by thinking `"The man whispered`, " is the string. Then, it sees the remaining `please speak to me.""` and returns a `SyntaxError`.

If you want to use quotes inside a string, and have JavaScript not misunderstand your intentions, you’ll need a different way to write quotes. Thankfully, JavaScript has a way to do this using the backslash character` ( \ )`.


### Escaping Characters

In JavaScript, you use the backslash to **escape** other characters.

Escaping a character tells JavaScript to ignore the character's special meaning and just use the literal value of the character. This is helpful for characters that have special meanings like in our previous example with quotes `"…"`.

Because quotes are used to signify the beginning and end of a string, you can use the backslash character to escape the quotes in order to access the literal quote character.

`"The man whispered, \"please speak to me.\""`
> Returns: The man whispered, "please speak to me."

This guarantees that the JavaScript engine doesn’t misinterpret the string and result in an error.

### Special Characters

Quotes aren’t the only special characters that need to be escaped, there’s actually quite a few. However, to keep it simple, here’s a list of some common special characters in JavaScript.

|Code|	Character|
|----|-----------|
|\\	 |\ (backslash)|
|\"	 |'' (double quote)|
|\'	'|(single quote)|
|\n	 |newline|
|\t	 |tab|

The last two characters listed in the table, newline `\n` and tab `\t`, are unique because they add additional whitespace to your Strings. A newline character will add a line break and a tab character will advance your line to the next tab stop.

`"Up up\n\tdown down"`
>Returns:
>Up up
 >down down

Select the string that returns the following output:

"The file located at "C:\\Desktop\My Documents\Roster\names.txt" contains the names on the roster."

```
"The file located at \"C:\\\\Desktop\\My Documents\\Roster\\names.txt\" contains the names on the roster."
```
## Section 11 Comparing Strings

`"Yes" == "yes"`
> Returns: false

### Case-sensitive

`'Y' != 'y'`
> Returns: true

### Internal working

In Javascript, strings are compared character-by-character in alphabetical order. Each character has a specific numeric value, coming from [ASCII value of Printable characters] . For example, the character 'A' has a value 65, and 'a' has a value 97. You can notice that a lowercase letter has a higher ASCII value than the uppercase character.

```
// Pick a string. Your string can have any number of characters.
var my_string = "a";

// Calculate the ASCII value of the first character, i.e. the character at the position 0. 
var ASCII_value = my_string.charCodeAt(0);

// Let us print
console.log(ASCII_value);
```

### Section 12 Favorite food

Create a string with the name of your favorite food. The first letter of the string should be capitalized.

```
/*
 * Programming Quiz: Favorite Food (2-3)
 */

/*
 * QUIZ REQUIREMENTS
 * 1. Your code should print a string with your favorite food
 * 2. Your code should have the first character capitalized
 * 3. Your code must have a `console.log()` function
 * 4. Your code should not be empty
 */
 var myString = ("Hello, my favorite food is Cheese")
 
console.log(myString);
```

### Section 13 String Equality for all

Fix the right side expression so it evaluates to true.

`"ALL Strings are CrEaTeD equal" == "All STRINGS are CrEaTED Equal"`

```
/*
 * Programming Quiz: String Equality for All (2-4)
 *
 * QUIZ REQUIREMENTS
 * 1. Your code should have a variable `answer`
 * 2. Your code should have "ALL Strings are CrEaTeD equal" on the left side
 * 3. Your code should use `==` comparison operator
 * 4. The comparison should evaluate to true
 * 5. The right side of your expression should match the left side
 */
 
// fix the right side of the expression
var answer = "ALL Strings are CrEaTeD equal" == "ALL Strings are CrEaTeD equal";
console.log(answer);
```

### Section 14 All tied up

Directions:
Build a single string that resembles the following joke.
```
Why couldn't the shoes go out and play?
They were all "tied" up!
```
Your joke should take the format of a question and answer. The first line should be a question and the second line should be an answer.

Hint: You will need to use special characters to produce the following output.

```
var joke = ("Why couldn't the shoes go out and play? \n They were all \"tied\" up!")
console.log(joke);
```
### Section 15 Yosa Buson

Build a string using concatenation by combining the lines from this famous haiku poem by Yosa Buson.
```
Blowing from the west
Fallen leaves gather
In the east.
```

```
var haiku = ("Blowing from the west" + "\nFallen leaves gather" + "\nIn the east.")
console.log(haiku);
```