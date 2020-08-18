## Lesson 6 Arrays

### Section 10 Length

#### Array.length

You can find the length of an array by using its `length` property.
```
var donuts = ["glazed", "powdered", "sprinkled"];
console.log(donuts.length);
```
>Prints: 3

To access the `length` property, type the name of the array, followed by a period . (you’ll also use the period to access other properties and methods), and the word `length`. The length property will then return the number of elements in the array.

TIP: Strings have a `length` property too! You can use it to get the length of any string. For example, `"supercalifragilisticexpialidocious"`.length returns `34`.

### Section 11 Push

So you can find length of an array, but what if you want to modify an array?

Thankfully, arrays have quite a few built-in methods for adding and removing elements from an array. The two most common methods for modifying an array are `push()` and `pop()`.

#### Push

You can use the `push()` method to **add** elements to the end of an array.
```
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled"];
```
Then, you can `push` donuts onto the end of the array using the `push()` method.

```
donuts.push("powdered"); // pushes "powdered" onto the end of the `donuts` array
```
>Returns: 7
>donuts array: ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon >sugar", "sprinkled", "powdered"]

Notice, with the `push()` method you need to pass the value of the element you want to add to the end of the array. Also, the `push()` method returns the length of the array after an element has been added.
```
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled"];
donuts.push("powdered"); // the `push()` method returns 7 because the `donuts` array now has 7 elements
```
>Returns: 7

### Section 12 Pop

Alternatively, you can use the `pop(`) method to **remove** elements from the **end** of an array.
```
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled", "powdered"];


donuts.pop(); // pops "powdered" off the end of the `donuts` array
donuts.pop(); // pops "sprinkled" off the end of the `donuts` array
donuts.pop(); // pops "cinnamon sugar" off the end of the `donuts` array
```
>Returns: "cinnamon sugar"
>donuts array: ["glazed", "chocolate frosted", "Boston creme", "glazed cruller"]

With the `pop()` method you don’t need to pass a value; instead, `pop()` will always remove the **last** element from the end of the array. Also, `pop()` returns the element that has been removed in case you need to use it.
```
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled", "powdered"];
donuts.pop(); // the `pop()` method returns "powdered" because "powdered" was the last element on the end of `donuts` array
```
>Returns: "powdered"

### Section 13 Splice

`splice()` is another handy method that allows you to **add and remove** elements from **anywhere** within an array.

While `push()` and `pop()` limit you to adding and removing elements from the end of an array, `splice()` lets you specify the index location to add new elements, as well as the number of elements you'd like to delete (if any).
```
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller"];
donuts.splice(1, 1, "chocolate cruller", "creme de leche"); // removes "chocolate frosted" at index 1 and adds "chocolate cruller" and "creme de leche" starting at index 1
```
>Returns: ["chocolate frosted"]

>donuts array after calling the splice() method: ["glazed", "chocolate cruller", "creme de leche", "Boston creme", "glazed cruller"]

Following is the syntax of `splice()` method: `arrayName.splice(arg1, arg2, item1, ....., itemX)`; where,

`arg1` = Mandatory argument. Specifies the starting index position to add/remove items. **You can use a negative value to specify the position from the end of the array** e.g., -1 specifies the last element.

`arg2` = Optional argument. Specifies the count of elements to be removed. If set to 0, no items will be removed.

`item1, ....., itemX` are the items to be added at index position arg1

`splice()` method returns the item(s) that were removed.

`splice()` is an incredibly powerful method that allows you to manipulate your arrays in a variety of ways. Any combination of adding or removing elements from an array can all be done in one simple line of code.

### Section 14 Rainbow

```
var rainbow = ['Red', 'Orange', 'Blackberry', 'Blue'];

// your code goes here

rainbow.splice(2,1, "Yellow", "Green");
rainbow.splice(5,0, "Purple");

console.log(rainbow);
```
### Section 16 Joining the crew

```
var captain = "Mal";
var second = "Zoe";
var pilot = "Wash";
var companion = "Inara";
var mercenary = "Jayne";
var mechanic = "Kaylee";

var crew = [captain, second, pilot, companion, mercenary, mechanic];

var doctor = "Simon";
var sister = "River";
var shepherd = "Book";

// your code goes here
crew.push (doctor);
crew.push (sister);
crew.push (shepherd);

console.log(crew);
```
