# Intro to JavaScript

## Lesson 7 Objects

### Section 5 Object Literals

#### Object-literal notation

```
var sister = {
  name: "Sarah", 
  age: 23,
  parents: [ "alice", "andy" ],
  siblings: ["julia"],
  favoriteColor: "purple",
  pets: true
};
```

The syntax you see above is called **object-literal notation**. There are some important things you need to remember when you're structuring an object literal:

- The "key" (representing a **property** or **method** name) and its "value" are separated from each other by a **colon**
- The `key: value` pairs are separated from each other by **commas**
- The entire object is wrapped inside curly braces `{ }`.

And, kind of like how you can look up a word in the dictionary to find its definition, the key in a `key:value` pair allows you to look up a piece of information about an object. Here's are a couple examples of how you can retrieve information about my sister's parents using the object you created.
```
// two equivalent ways to use the key to return its value
sister["parents"] // returns [ "alice", "andy" ]
sister.parents // also returns ["alice", "andy"]
```

Using `sister["parents"]` is called **bracket notation** (because of the brackets!) and using `sister.parents` is called **dot notation** (because of the dot!).

#### What about methods?

The sister object above contains a bunch of properties about my sister, but doesn't really say what my sister does. For instance, let's say my sister likes to paint. You might have a `paintPicture()` method that returns `"Sarah paints a picture!" `whenever you call it. The syntax for this is pretty much exactly the same as how you defined the properties of the object. The only difference is, the `value` in the `key:value` pair will be a **function**.
```
var sister = {
  name: "Sarah",
  age: 23,
  parents: [ "alice", "andy" ],
  siblings: ["julia"],
  favoriteColor: "purple",
  pets: true,
  paintPicture: function() { return "Sarah paints!"; }
};

sister.paintPicture();
```
>Returns: "Sarah paints!"

and you can access the name of my sister by accessing the `name` property:

`sister.name`
>Returns: "Sarah"

### Section 6 Naming Conventions

- Using "" around property(whilst not strictly necessary) names can mask problems when using dot notaion

- Don't use numbers as 1st charecters in property names

- avoid spaces and hypens

- use camelCasing instead


Objects are one of the most important data structures in JavaScript. Get ready to see them everywhere!

#### Summary

They have properties (information about the object) and methods (functions or capabilities the object has). Objects are an incredibly powerful data type and you will see them all over the place when working with JavaScript, or any other object-oriented programming language.

#### Object literals, methods, and properties
You can define objects using object-literal notation:
```
var myObj = { 
  color: "orange",
  shape: "sphere",
  type: "food",
  eat: function() { return "yummy" }
};

myObj.eat(); // method
myObj.color; // property
```
#### Naming conventions
Feel free to use upper and lowercase numbers and letters, but don't start your property name with a number. You don't need to wrap the string in quotes! If it's a multi-word property, use camel case. Don't use hyphens in your property names
```
var richard = {
  "1stSon": true;
  "loves-snow": true;
};

richard.1stSon // error
richard.loves-snow // error
```

### Section 8 Menu Items
```
/*
 * Programming Quiz: Menu Items (7-2)
 * Create an object named `breakfast`. 
 * The object should contain properties for the `name`, `price`, and `ingredients`.
 * Print the entire object on the console
 */

// your code goes here

var breakfast = {
    name : "The Lumberjack",
    price : 9.95,
    ingredients : ["eggs", "sausage", "toast", "hashbrowns", "pancakes"]
}

console.log(breakfast);
```

### Section 9 Bank accounts
```
/*
 * Programming Quiz: Bank Accounts 1 (7-3)
 */

/*
 * QUIZ REQUIREMENTS
 * - Your code should have an object `savingsAccount` 
 * - Your `savingsAccount` object should have the `balance` and `interestRatePercent` property
 * - Your `savingsAccount` object should have a `printAccountSummary()` method
 * - Your `printAccountSummary()` method should return the EXACT expected message
 * - BE CAREFUL ABOUT THE PUNCTUATION, SPACES, AND EXACT WORDS TO BE PRINTED.
 */


var savingsAccount = {
    balance: 1000,
    interestRatePercent: 1,
    deposit: function addMoney(amount) {
        if (amount > 0) {
            savingsAccount.balance += amount;
        }
    },
    withdraw: function removeMoney(amount) {
        var verifyBalance = savingsAccount.balance - amount;
        if (amount > 0 && verifyBalance >= 0) {
            savingsAccount.balance -= amount;
        }
    },
    // your code goes here
    
    printAccountSummary: function() {
        return "Welcome!\nYour balance is currently $" + savingsAccount.balance + " and your interest rate is " + savingsAccount.interestRatePercent + "%."
    }
};

console.log(savingsAccount.printAccountSummary());
```
### Section 11 Facebook friends
```
/*
 * Programming Quiz: Facebook Friends (7-5)
 */

/*
 * QUIZ REQUIREMENTS
 * - Your code should have an object `facebookProfile`
 * - The `facebookProfile` object should have the `name` (string), `friends` (number), and `messages` (array of strings) property
 * - Your `facebookProfile` object should have the `postMessage()`, `deleteMessage()`, `addFriend()` and `removeFriend()` method
 * - Carefully implement the desired functionality of each method, as decribed above
 */


// TIP - 
// In an array, 
// - addition at the end is done using push() method
// - addition at a specific index is done using splice() method
// - deletion from the beginning is done using pop() method
// - deletion from a specific index is done using splice() method

// your code goes here
var facebookProfile = {
    name: "Udacian",
    friends: 25,
    messages: ["Message 1", "Message 2", "Message 3", "Message 4"],
    postMessage: function(message){
        facebookProfile.messages.push(message);
    },
    deleteMessage: function(index){
        // In the following splice() method call,
        // - argument 1 = index from where the element has to be deleted
        // - argument 2 = count of elements to be deleted
        facebookProfile.messages.splice(index, 1);
    },
    addFriend: function(){
        facebookProfile.friends = facebookProfile.friends + 1;
        //friends += 1; // this statement is equivalent to the above
    },
    removeFriend: function(){
        if(facebookProfile.friends>0)
            facebookProfile.friends = facebookProfile.friends - 1;
    }
};


```

### Section 12 Donuts revisited

```
/*
 * Programming Quiz: Donuts Revisited (7-6)
 */

/*
 * QUIZ REQUIREMENTS
 * - Your code sshould have an array named `donuts`
 * - Your `donuts` array should call the `forEach()` method
 * - Your `forEach()` loop should output the donut summaries
 * - BE CAREFUL ABOUT THE PUNCTUATION, SPACES, AND EXACT WORDS TO BE PRINTED.
 */

// This is an array of objects. 
var donuts = [
    { type: "Jelly", cost: 1.22 },
    { type: "Chocolate", cost: 2.45 },
    { type: "Cider", cost: 1.59 },
    { type: "Boston Cream", cost: 5.99 }
];

donuts.forEach(function(donut){

console.log(donut.type + " donuts cost $" + donut.cost + " each")

});
```











