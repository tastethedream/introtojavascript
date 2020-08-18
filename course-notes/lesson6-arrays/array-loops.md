## Lesson 6 Arrays

### Section 18 Array Loops

Once the data is in the array, you want to be able to efficiently access and manipulate each element in the array without writing repetitive code for each element.

For instance, if this was our original donuts array:

`var donuts = ["jelly donut", "chocolate donut", "glazed donut"];`

and we decided to make all the same donut types, but only sell them as donut holes instead, we could write the following code:
```
donuts[0] += " hole";
donuts[1] += " hole";
donuts[2] += " hole";
```
>donuts array: ["jelly donut hole", "chocolate donut hole", "glazed donut hole"]

To loop through an array, you can use a variable to represent the index in the array, and then loop over that index to perform whatever manipulations your heart desires.
```
var donuts = ["jelly donut", "chocolate donut", "glazed donut"];

// the variable `i` is used to step through each element in the array
for (var i = 0; i < donuts.length; i++) {
    donuts[i] += " hole";
    donuts[i] = donuts[i].toUpperCase();
}
```
>donuts array: ["JELLY DONUT HOLE", "CHOCOLATE DONUT HOLE", "GLAZED DONUT HOLE"]

In this example, the variable `i` is being used to represent the index of the array. As `i `is incremented, you are stepping over each element in the array starting from` 0` until `donuts.length - 1` (`donuts.length` is out of bounds).

### Section 19 The forEach loop

Arrays have a set of special methods to help you iterate over and perform operations on collections of data. You can view the MDN Documentation list of Array methods here, but a couple big ones to know are the` forEach()` and `map()` methods.

The `forEach()` method gives you an alternative way to iterate over an array, and manipulate each element in the array with an inline function expression.

var donuts = ["jelly donut", "chocolate donut", "glazed donut"];
```
donuts.forEach(function(donut) {
  donut += " hole";
  donut = donut.toUpperCase();
  console.log(donut);
});
```
>Prints:
>JELLY DONUT HOLE
>CHOCOLATE DONUT HOLE
>GLAZED DONUT HOLE

Notice that the `forEach(`) method iterates over the array without the need of an explicitly defined index. In the example above, `donut` corresponds to the element in the array itself. This is different from a `for` or `while` loop where an index is used to access each element in the array:
```
for (var i = 0; i < donuts.length; i++) {
  donuts[i] += " hole";
  donuts[i] = donuts[i].toUpperCase();
  console.log(donuts[i]);
}
```

#### Parameters

The function that you pass to the `forEach()` method can take up to three parameters. In the video, these are called `element`, `index`, and `array`, but you can call them whatever you like.

The` forEach()` method will call this function once for each element in the array (hence the name forEach.) Each time, it will call the function with different arguments. The `element` parameter will get the **value** of the array element. The `index` parameter will get the **index** of the element (starting with zero). The `array `parameter will get a **reference** to the whole array, which is handy if you want to modify the elements.

Here's another example:
```
words = ["cat", "in", "hat"];
words.forEach(function(word, num, all) {
  console.log("Word " + num + " in " + all.toString() + " is " + word);
});
```
>Prints:
>Word 0 in cat,in,hat is cat
>Word 1 in cat,in,hat is in
>Word 2 in cat,in,hat is hat

```
/*
 * Programming Quiz: Another Type of Loop (6-8)
 * QUIZ REQUIREMENTS
 * Use the existing `test` variable and write a `forEach` loop
 * that adds 100 to each number that is divisible by 3.
 *
 * Things to note:
 *  - Inside the loop, you must use an `if` statement to verify code is divisible by 3
 *  - Inside the loop, you can updade an element ONLY by using the arrayName[index]
 *  - Outside the loop, you can use `console.log` to verify the `test` variable 
 */

var test = [12, 929, 11, 3, 199, 1000, 7, 1, 24, 37, 4,
    19, 300, 3775, 299, 36, 209, 148, 169, 299,
    6, 109, 20, 58, 139, 59, 3, 1, 139
];

// Write your code here

test.forEach(function(item, index){
  if (item % 3 === 0){
     test[index]=test[index]+100; 
  } 
      
  
});

console.log(test);
```

### Section 21 Map()

Using `forEach()` will not be useful if you want to permanently modify the original array. `forEach()` always returns undefined. However, creating a new array from an existing array is simple with the powerful `map()` method.

With the` map()` method, you can take an array, perform some operation on each element of the array, and **return a new array**.
```
var donuts = ["jelly donut", "chocolate donut", "glazed donut"];

var improvedDonuts = donuts.map(function(donut) {
  donut += " hole";
  donut = donut.toUpperCase();
  return donut;
});
```
>donuts array: ["jelly donut", "chocolate donut", "glazed donut"]
>improvedDonuts array: ["JELLY DONUT HOLE", "CHOCOLATE DONUT HOLE", "GLAZED DONUT HOLE"]

` The map(`) method accepts **one** argument, a function that will be used to manipulate each element in the array. In the above example, we used a function expression to pass that function into `map()`. This function is taking in one argument, donut which corresponds to each element in the donuts array. You no longer need to iterate over the indices anymore. `map()` does all that work for you.

```
/*
 * Programming Quiz: I Got Bills (6-9)
 *
 * Use the .map() method to take the bills array below and create a second array
 * of numbers called totals. The totals array should contains each amount from the
 * bills array but with a 15% tip added. Log the totals array to the console.
 *
 * For example, the first two entries in the totals array would be:
 *
 * [57.76, 21.99, ... ]
 *
 * Things to note:
 *  - each entry in the totals array must be a number
 *  - each number must have an accuracy of two decimal points
 */
 
 /*
 * QUIZ REQUIREMENTS
 * - Your code should have the variables `bills` and `totals`
 * - Your `bills` array should call the `map()` method and store the return of `map()` in the `totals` array
 * - Your `totals` array should be an array of numbers
 * - Your code should print the `totals` array to the console
 * - The output must be as described above. 
 */

var bills = [50.23, 19.12, 34.01,
    100.11, 12.15, 9.90, 29.11, 12.99,
    10.00, 99.22, 102.20, 100.10, 6.77, 2.22
];

var totals = bills.map(function (bill){
    bill *= 1.15;
    bill = bill.toFixed(2);
    bill = Number(bill);
    
    return bill;
    
});

console.log(totals);
```

### Section 23 Array in arrays

You could use an array of arrays that has the name of each donut associated with its position in the box.

Here's an example:
```
var donutBox = [
  ["glazed", "chocolate glazed", "cinnamon"],
  ["powdered", "sprinkled", "glazed cruller"],
  ["chocolate cruller", "Boston creme", "creme de leche"]
];
```
If you wanted to loop over the donut box and display each donut (along with its position in the box!) you would start with writing a for loop to loop over each row of the box of donuts:
```
var donutBox = [
  ["glazed", "chocolate glazed", "cinnamon"],
  ["powdered", "sprinkled", "glazed cruller"],
  ["chocolate cruller", "Boston creme", "creme de leche"]
];
```
```
// here, donutBox.length refers to the number of rows of donuts
for (var row = 0; row < donutBox.length; row++) {
  console.log(donutBox[row]);
}
```
>Prints:
>["glazed", "chocolate glazed", "cinnamon"]
>["powdered", "sprinkled", "glazed cruller"]
>["chocolate cruller", "Boston creme", "creme de leche"]

Since each row is an array of donuts, you next need to set up an inner-loop to loop over each cell in the arrays.
```
for (var row = 0; row < donutBox.length; row++) {
  // here, donutBox[row].length refers to the length of the donut array currently being looped over
  for (var column = 0; column < donutBox[row].length; column++) {
    console.log(donutBox[row][column]);
  }
}
```
```
Prints:
"glazed"
"chocolate glazed"
"cinnamon"
"powdered"
"sprinkled"
"glazed cruller"
"chocolate cruller"
"Boston creme"
"creme de leche"
```

```
// Let i represents a sub-array
for(var i=0; i<numbers.length; i++){

    // Let j represents the length of a sub-array 
    for(var j=0; j<numbers[i].length; j++){
        if(numbers[i][j]%2===0)
            numbers[i][j]="even";
        else
            numbers[i][j]="odd";
    }
}

// Print the final array
console.log(numbers);
```
