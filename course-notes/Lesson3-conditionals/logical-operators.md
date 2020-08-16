# Lesson 3 Conditionals
## Section 10 Logical Operators

Here’s the logical expression used to represent Julia’s weekend plans:
```
var colt = "not `b`usy";
var weather = "nice";

if (colt === "not `b`usy" && weather === "nice") {
  console.log("go to the park");
}
```
> Prints: "go to the park"

The `&&` symbol is the logical AND operator, and it is used to combine *two* logical expressions into one larger logical expression. If *`both* smaller expressions are *``true``*, then the entire expression evaluates to *``true``*. If **either one** of the smaller expressions is *``false``*, then the whole logical expression is *``false``*.

Another way to think about it is when the `&&` operator is placed between the two statements, the code literally reads, "if Colt is not busy AND the weather is nice, then go to the park".

### Logical expressions

**Logical expressions** are similar to mathematical expressions, except logical expressions evaluate to either *``true``* or *``false``*.

`11 != 12`
> Returns: ``true``

Similar to mathematical expressions that use `+`, `-`, `*`, `/` and `%`, there are logical operators `&&`, `||` and `!` that you can use to create more complex logical expressions.

|Operator |	Meaning |	Example	How it works|
----------|---------|-----------------------|
|`&&` |	Logical AND	| `value1 && value2`|	Returns `true` if *both* `value1` and `value2` evaluate to ```true```.|
|`||` |	Logical OR |	`value1 || value2`|	Returns `true` if *either* `value1` or `value2` (*or even both*) evaluates to `true`.|
| `!` | Logical NOT	|`!value1`|	Returns the *opposite* of `value1`. If `value1` is `true`, then `!value1` is `false`.|

Logical expressions are evaluated from left to right. Similar to mathematical expressions, logical expressions can also use parentheses to signify parts of the expression that should be evaluated first.

### Truth Tables

*&& (AND)*
|A|	`B` |	`A `&& `B`|
|--|---|--------|
|``true``|	``true``|	``true``|
|``true``	|``false``|	``false``|
|``false``|	``true``|	``false``|
|``false``|	``false``|	``false``|

*|| (OR)
|A|	`B` |	`A `&& `B`|
|--|---|--------|
|``true``|	``true``|	``true``|
|``true``	|``false``|	``true``|
|``false``|	``true``|	``true``|
|``false``|	``false``|	``false``|

In some scenarios, the value of ``B`` in logical AND and OR doesn't matter.

In both tables, there are specific scenarios where regardless of the value of `B`, the value of `A `is enough to satisfy the condition.

For example, if you look at `A `AND `B`, if `A `is `false`, then regardless of the value `B`, the total expression will always evaluate to `false` because both `A `and `B` must be `true` in order for the entire expression to be `true`.

This behavior is called **short-circuiting** because it describes the event when later arguments in a logical expression are not considered because the first argument already satisfies the condition.

### Section 12 Check Your Balance

![Check your balance flow chart](https://github.com/tastethedream/introtojavascript/blob/master/images/balance.jpeg "check balance flow chart")

```
var balance = -1.00;
var checkBalance = true;
var isActive = true;

// your code goes here

if (checkBalance === true){
    if (balance > 0 && isActive === true){
        console.log("Your balance is $" + balance.toFixed(2) + "." );
    } else {
        if (isActive === false){
            console.log("Your account is no longer active.");
            
        } else {
            if(balance < 0){
                console.log("Your balance is negative. Please contact bank.");
            } else {
                console.log("Your account is empty.");
            }
        }
    }
} else{
    console.log("Thank you. Have a nice day!");
}
```

### Section 13 Icecream
```
var flavor = "vanilla";
var vessel = "bowl";
var toppings = "sprinkles";

// Add your code here

if ((flavor === "vanilla" || flavor === "chocolate") && (vessel === "cone" || vessel === "bowl") && (toppings === "sprinkles" || toppings === "peanuts")){
    
        console.log( "I'd like 2 scoops of " + flavor + "ice cream in a " + vessel + " with " + toppings + ".");
}    
```

### Section 14 What to wear?

```
var shirtWidth = 19;
var shirtLength = 28.5;
var shirtSleeve = 8.15;
var size ="NA"

/*
 * To gain confidence, check your code for the following combination of [shirtWidth, shirtLength, shirtSleeve, expectedSize]:
 * [18, 28, 8.13, 'S']
 * [19.99, 28.99, 8.379, 'S']
 * [20, 29, 8.38, 'M']
 * [22, 30, 8.63, 'L']
 * [24, 31, 8.88, 'XL']
 * [26, 33, 9.63, '2XL']
 * [27.99, 33.99, 10.129, '2XL']
 * [28, 34, 10.13, '3XL']
 * [18, 29, 8.47, 'NA']
*/

// WRITE YOUR CODE HERE

if ((shirtWidth>=18 && shirtWidth<20) && (shirtLength>=28 && shirtLength<29) && (shirtSleeve>=8.13 && shirtSleeve<8.38)) {
    size = "S";
}
 else if ((shirtWidth>=20 && shirtWidth<22) && (shirtLength>=29 && shirtLength<30) && (shirtSleeve>=8.38&& shirtSleeve<8.63) ) {
    size = "M";
 }   
else if ((shirtWidth>=22 && shirtWidth<24) && (shirtLength>=30 && shirtLength<31) && (shirtSleeve>=8.63 && shirtSleeve<8.88) ) {
    size = "L";
}
else if ((shirtWidth>=24 && shirtWidth<26) && (shirtLength>=31 && shirtLength<33) && (shirtSleeve>=8.88 && shirtSleeve<9.63) ) {
    size = "XL";
}
else if ((shirtWidth>=26 && shirtWidth<28) && (shirtLength>=33 && shirtLength<34) && (shirtSleeve>=9.63 && shirtSleeve<10.13) ) {
    size = "2XL";
}
else if ((shirtWidth>=28) && (shirtLength>=34) && (shirtSleeve>=10.13) ) {
    size = "3XL";
}
else {
    size = "NA";
}
console.log(size);
```
   