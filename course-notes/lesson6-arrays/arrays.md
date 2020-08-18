# Intro to JavaScript

## Lesson 6 Arrays

### Section 3 Creating an array

- Array = An array is a data structure that you can use to store **multiple values**
- Array =  Arrays are **organised**

#### Arrays
An **array** is useful because it stores multiple values into a single, organized data structure. You can define a new array by listing values separated with commas between square brackets `[]`.
```
// creates a `donuts` array with three strings
var donuts = ["glazed", "powdered", "jelly"];
```

But strings aren’t the only type of data you can store in an array. You can also store numbers, booleans… and really anything!
```
// creates a `mixedData` array with mixed data types
var mixedData = ["abcd", 1, true, undefined, null, "all the things"];
```

You can even store an array in an array to create a **nested array**!
```
// creates a `arraysInArrays` array with three arrays
var arraysInArrays = [[1, 2, 3], ["Julia", "James"], [true, false, true, false]];
```
Nested arrays can be particularly hard to read, so it's common to write them on one line, using a newline after each comma:
```
var arraysInArrays = [
  [1, 2, 3], 
  ["Julia", "James"], 
  [true, false, true, false]
];
```
### Section 5 Array Index

#### Indexing

Remember that elements in an array are indexed starting at the position `0`. To access an element in an array, use the name of the array immediately followed by **square brackets** containing the index of the value you want to access.

```
var donuts = ["glazed", "powdered", "sprinkled"];
console.log(donuts[0]); // "glazed" is the first element in the `donuts` array
```
>Prints: "glazed"

One thing to be aware of is if you try to access an element at an index that does not exist, a value of undefined will be returned back.

`console.log(donuts[3]); // the fourth element in `donuts` array does not exist!`
>Prints: undefined

Finally, if you want to change the value of an element in array, you can do so by setting it equal to a new value.
```
donuts[1] = "glazed cruller"; // changes the second element in the `donuts` array to "glazed cruller"
console.log(donuts[1]); 
```
>Prints: "glazed cruller"
```
var prices = [1.23, 48.11, 90.11, 8.50, 9.99, 1.00, 1.10, 67.00];

// your code goes here

prices[1] = 10.21;
prices[3] = 6.60;
prices[7] = 20.68

console.log(prices);
```
