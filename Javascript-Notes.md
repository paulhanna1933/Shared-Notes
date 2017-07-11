
# JavaScript - The Weird Parts


Syntax Parser: A program that reads your code and determines what it does and if its grammar is valid.

Lexical Environment: Where something sits physically in the code you write.

Execution Context: A wrapper to help manage the code that is running.


Undefined: When a variable has been created but has not been set with a defined value.


Synchronous: One line of code being executed at a time (in order).


Invocation: Running a function / Calling a function


Variable Environment: Where the variables live that were created and how they relate to each other in memory.  

Name/Value Pair: A name which maps to a unique value.
Example: Address = "100 Main St."

Object: A collection of name value pairs | Example: 

```javascript
Address: 
    {
        Street: 'Main',
        Number: 100
        Apartment:
        {
            Floor: 3,
            Number: 301
        }
    }
```
![Image](https://content.screencast.com/users/paulhanna33/folders/Jing/media/6c8a2651-6c07-4296-b6c2-6370b956155f/00000010.png)
![Image](https://content.screencast.com/users/paulhanna33/folders/Jing/media/59dd2eae-31b9-428c-a68e-1dd149ab2ed3/00000011.png)



```javascript
function b() {
var myVar;
console.log(myVar);
}

function a() {
var myVar = 2;
console.log(myVar);
b();
}

var myVar = 1;
console.log(myVar);
a();
//console results: 
1
2
undefined
```
## The Scope Chain

```javascript
function b() {
console.log(myVar);
}
function a() {
var myVar = 2;
b();
}
var myVar = 1;
a();
```
# Scope: Where a variable is available in your code
And if it's truly the same variable, or a new copy


# Let: New method to declare variables in ES6

```javascript
if (a > b) {
let c = true;
}
```
# Asynchronous: More than one at a time
# Dynamic Typing: You don't tell the engine what type of data a variable holds, it figures it out while your code is running
Variables can hold different types of values because it's all figured out during execution. 

```javascript
Static Typing: 
bool isNew = 'hello'; // an error

Dynamic Typing: 
var isNew = true; // no errors
isNew = 'yup!';
isNew = 1;
```
# Primitive Type: A type of data that represents a single value that is, not an object (6 types)
Undefined: Represents lack of existence (you shouldn't set a variable to this) 
Null: Represents lack of existence (you can set a variable to this) 
Boolean: true or false
Number: Floating point number (there's always some decimals). Unlike other programming languages, there's only one number type...and it can make math weird.
String: A sequence of characters inside of quotation marks '' or ""
Symbol: Used in ES6 (the next version of Javascript) We won't talk about this here.


# Operators: A special function that is syntactically (written) differently. Generally, operators take two parameters and return one result. 

```javascript
var a = 3 + 4;
console.log(a);
+ | - | > | < | >= | <= | % 
```
# Operator Precedence: Which operator function gets called first - Functions are called in order of precedence (HIGHER precedence wins) 


# Associativity: What order operator functions get called in: left-to-right or right-to-left - When functions have the same precedence
# [PDF Javascript Operator Precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)
# Coercion: Converting a value from one type to another.
This happens quite often in Javascript because it's dynamically typed.

```javascript
var a = 'hello ' + 'world' ;
console.log(a); // Output: hello world
```
# [Comparison Operators](https://github.com/paulhanna1933/Javascript-Understanding-The-Weird-Parts/blob/master/Equalty-Comparison-And-Sameness.pdf)

```javascript
console.log(1 < 2 < 3); // True
console.log(3 < 2 < 1); // True? Because 3 < 2 is false which equals 0 and 0 < 1 which equals true
console.log(0 < 1) // Is the conversion of the above
// False converts to 0 & True converts to 1
3 == 3 // true
"3" == 3 // true
false == 0 // true
true == 1 // true
"" == 0 // true
"" == false // true 
var a = 0;
var b = false;
if (a === b) {
console.log('They are equal!');
} else {
console.log('Nope, not equal.');
}
```
# Default Values

```javascript
function greet(name) {
    console.log('Hello ' + name); 
}
greet('Tony'); // Output: Hello Tony
greet(); // // Output: Hello Undefined 
undefined || 'hello' // output: true
'hi' || 'hello' // output: hi (left to right) 
null || 'hello' // output: hello
'' || 'hello' // output: hello
```
# Framework Aside
Default values

```javascript

```


# JavaScript (FCC)


## Variables
***Data Types:***  undefined, null, boolean, string, symbol, number, and object.


***Variables*** allow computers to store and manipulate data in a dynamic fashion. They do this by using a "label" to point to the data rather than using the data itself. Any of the seven data types may be stored in a variable.


We tell JavaScript to create or declare a variable by putting the keyword var in front of it, like so:

```javascript
var ourName;
```
## Assignment Operator
In JavaScript, you can store a value in a variable with the assignment operator.

myVariable = 5;

Assigns the Number value 5 to myVariable.


Assignment always goes from right to left. Everything to the right of the = operator is resolved before the value is assigned to the variable to the left of the operator.

```javascript
myVar = 5;
myNum = myVar;
```
## Increment a Number with JavaScript 

```javascript
i++;
is the equivalent of
i = i + 1;
Note
The entire line becomes i++;, eliminating the need for the equal sign.
myVar++
```
## Decrement a Number with JavaScript 

```javascript
i--;
is the equivalent of
i = i - 1;
```
## Finding a Remainder in JavaScript 
The remainder operator % gives the remainder of the division of two numbers.
Example: 

```javascript
5 % 2 = 1 because
Math.floor(5 / 2) = 2 (Quotient)
2 * 2 = 4
5 - 4 = 1 (Remainder)
```
Usage
In mathematics, a number can be checked even or odd by checking the remainder of the division of the number by 2.

```javascript
17 % 2 = 1 (17 is Odd)
48 % 2 = 0 (48 is Even)
```
## Compound Assignment With Augmented Addition 

```javascript
+= -= *= /=
myVar += 5; will add 5 to myVar
Like the += operator, -= subtracts a number from a variable.
a = a - 6;
b = b - 15;
c = c - 1;
-------------
a -= 6;
b -= 15;
c -= 1;
```
## Convert Celsius to Fahrenheit 

```javascript
function convertToF(celsius) {
  var fahrenheit;
//SOLUTION//SOLUTION//SOLUTION//SOLUTION
  fahrenheit = celsius * 9/5 + 32; 
//SOLUTION//SOLUTION//SOLUTION//SOLUTION
  return fahrenheit;
}
// Change the inputs below to test your code
convertToF(30);
```
## Escape Sequences in Strings
Code	Output
\'	single quote
\"	double quote
\\	backslash
\n	newline
\r	carriage return
\t	tab
\b	backspace
\f	form feed
## Find the Length of a String 
You can find the length of a String value by writing .length after the string variable or string literal.

```javascript
"Alan Peter".length; // 10
```
## Use Bracket Notation to Find the First Character in a String
For example, the character at index 0 in the word "Charles" is "C". So if var firstName = "Charles", you can get the value of the first letter of the string by using firstName[0]

```javascript
// Example
var firstLetterOfFirstName = "";
var firstName = "Ada";

firstLetterOfFirstName = firstName[0];
```
## Use Bracket Notation to Find the  Character in a String 

```javascript
// Example
var firstName = "Ada";
var lastLetterOfFirstName = firstName[firstName.length - 1];

// Example
var firstName = "Ada";
var thirdToLastLetterOfFirstName = firstName[firstName.length - 3];

// Setup
var lastName = "Lovelace";

// Only change code below this line
var secondToLastLetterOfLastName = lastName[lastName.length -2];
```
## Word Blanks

```javascript
function wordBlanks(myNoun, myAdjective, myVerb, myAdverb) {
  var result = "";
  // Your code below this line
  result = (myAdjective + " " + myNoun + " " + myVerb + " " + myAdverb );
  // Your code above this line
  return result;
}
// Change the words here to test your function
wordBlanks("dog", "big", "ran", "quickly");
```
## Multiple Values in one Variable using JavaScript Arrays 
You start an array declaration with an opening square bracket, end it with a closing square bracket, and put a comma between each entry, like this:

```javascript
// Example
var ourArray = ["John", 23];

// Only change code below this line.
var myArray = ["Paul", 33];
```
## Nest one Array within Another Array

```javascript
// Example
var ourArray = [["the universe", 42], ["everything", 101010]];

// Only change code below this line.
var myArray = [["the earth", 34], ["the world", 101010]];
```
## Access Array Data with Indexes

```javascript
// Example
var ourArray = [1,2,3];
var ourData = ourArray[0]; // equals 1

// Setup
var myArray = [1,2,3];

// Only change code below this line.
var myData = myArray[0];
```
## Modify Array Data With Indexes 

```javascript
// Example
var ourArray = [1,2,3];
ourArray[1] = 3; // ourArray now equals [1,3,3].

// Setup
var myArray = [1,2,3];

// Only change code below this line.
myArray[0] = 3;
```
## Access MultiDimensional Arrays With Indexes
One way to think of a multi-dimensional array, is as an array of arrays. When you use brackets to access your array, the first set of brackets refers to the entries in the outer-most (the first level) array, and each additional pair of brackets refers to the next level of entries inside.


Example: 

```javascript
var arr = [
    [1,2,3],
    [4,5,6],
    [7,8,9],
    [[10,11,12], 13, 14]
];
arr[3]; // equals [[10,11,12], 13, 14]
arr[3][0]; // equals [10,11,12]
arr[3][0][1]; // equals 11
```



```javascript
// Setup
var myArray = [[1,2,3], [4,5,6], [7,8,9], [[10,11,12], 13, 14]];

// Only change code below this line.
var myData = myArray[2][1];
```
## Manipulate Arrays With push
An easy way to append data to the end of an array is via the push() function.
.push() takes one or more parameters and "pushes" them onto the end of the array.

```javascript
var arr = [1,2,3];
arr.push(4);
// arr is now [1,2,3,4]
```
## *Instruction*:
Push ["dog", 3] onto the end of the myArray variable.

```javascript
// Example
var ourArray = ["Stimpson", "J", "cat"];
ourArray.push(["happy", "joy"]); 
// ourArray now equals ["Stimpson", "J", "cat", ["happy", "joy"]]

// Setup
var myArray = [["John", 23], ["cat", 2]];

// Only change code below this line.
myArray.push(["dog", 3]);
```
## Manipulate Arrays With pop 
For example, for the code
var oneDown = [1, 4, 6].pop();
the variable oneDown now holds the value 6 and the array becomes [1, 4].

```javascript
// Example
var ourArray = [1,2,3];
var removedFromOurArray = ourArray.pop(); 
// removedFromOurArray now equals 3, and ourArray now equals [1,2]

// Setup
var myArray = [["John", 23], ["cat", 2]];

// Only change code below this line.
var removedFromMyArray = myArray.pop();
```
## Manipulate Arrays With shift 
pop() always removes the last element of an array. What if you want to remove the first?

That's where .shift() comes in. It works just like .pop(), except it removes the first element instead of the last.

```javascript
// Example
var ourArray = ["Stimpson", "J", ["cat"]];
removedFromOurArray = ourArray.shift();
// removedFromOurArray now equals "Stimpson" and ourArray now equals ["J", ["cat"]].

// Setup
var myArray = [["John", 23], ["dog", 3]];

// Only change code below this line.
var removedFromMyArray = myArray.shift();
```
## Manipulate Arrays With unshift
.unshift() works exactly like .push(), but instead of adding the element at the end of the array, unshift() adds the element at the beginning of the array.

```javascript
// Example
var ourArray = ["Stimpson", "J", "cat"];
ourArray.shift(); // ourArray now equals ["J", "cat"]
ourArray.unshift("Happy"); 
// ourArray now equals ["Happy", "J", "cat"]

// Setup
var myArray = [["John", 23], ["dog", 3]];
myArray.shift();

// Only change code below this line.
myArray.unshift(["Paul", 35]);
```
## Shopping List
Create a shopping list in the variable myList. The list should be a multi-dimensional array containing several sub-arrays.

The first element in each sub-array should contain a string with the name of the item. The second element should be a number representing the quantity i.e.

["Chocolate Bar", 15]

```javascript
var myList = [["Chocolate bar", 10],["Carrots", 50],["Chicken Breast", 10],["Hummus", 2],["Pinto Beans", 100]];
```
## Write Reusable JavaScript with Functions 
In JavaScript, we can divide up our code into reusable parts called functions.
Here's an example of a function:

```javascript
function functionName() {
  console.log("Hello World");
}
```
You can call or invoke this function by using its name followed by parentheses, like this:

functionName();

Each time the function is called it will print out the message "Hello World" on the dev console. All of the code between the curly braces will be executed every time the function is called.

```javascript
// Example
function ourReusableFunction() {
  console.log("Heyya, World");
}

ourReusableFunction();

// Only change code below this line
function reusableFunction() {
  console.log("Hi World");
}

reusableFunction();
```
## Passing Values to Functions with Arguments 
Parameters are variables that act as placeholders for the values that are to be input to a function when it is called. When a function is defined, it is typically defined along with one or more parameters. The actual values that are input (or "passed") into a function when it is called are known as arguments.

Here is a function with two parameters, param1 and param2:

```javascript
function testFun(param1, param2) {
  console.log(param1, param2);
}
```
Then we can call testFun:

testFun("Hello", "World");

We have passed two arguments, "Hello" and "World". Inside the function, param1 will equal "Hello" and param2 will equal "World". Note that you could call testFun again with different arguments and the parameters would take on the value of the new arguments.

```javascript
// Example
function ourFunctionWithArgs(a, b) {
  console.log(a - b);
}
ourFunctionWithArgs(10, 5); // Outputs 5

// Only change code below this line.
function functionWithArgs(x, y) {
  console.log(x + y);
}

functionWithArgs(5, 5);
```
## Global Scope and Functions
In JavaScript, scope refers to the visibility of variables. Variables which are defined outside of a function block have Global scope. This means, they can be seen everywhere in your JavaScript code.

Variables which are used without the var keyword are automatically created in the global scope. This can create unintended consequences elsewhere in your code or when running a function again. You should always declare your variables with var.

```javascript
var myGlobal = 10;// Declare your variable here

function fun1() {
  oopsGlobal = 5;// Assign 5 to oopsGlobal Here
  
}
```
## Local Scope and Functions 
Variables which are declared within a function, as well as the function parameters have local scope. That means, they are only visible within that function.

Here is a function myTest with a local variable called loc.

```javascript
function myTest() {
  var loc = "foo";
  console.log(loc);
}
myTest(); // "foo"
console.log(loc); // "undefined"
```
## Global vs Local Scope in Functions
It is possible to have both local and global variables with the same name. When you do this, the local variable takes precedence over the global variable.

In this example:
The function myFun will return "Head" because the local version of the variable is present.

```javascript
var someVar = "Hat";
function myFun() {
  var someVar = "Head";
  return someVar;
}
```
Add a local variable to myOutfit to override the value of outerWear with "sweater".

```javascript
// Setup
var outerWear = "T-Shirt";

function myOutfit() {
  // Only change code below this line
  var outerWear = "sweater";
  
  // Only change code above this line
  return outerWear;
}

myOutfit();
```
## Return a Value from a Function with Return
We can pass values into a function with arguments. You can use a return statement to send a value back out of a function.

Example:
plusThree takes an argument for num and returns a value equal to num + 3.

```javascript
function plusThree(num) {
  return num + 3;
}
var answer = plusThree(5); // 8
```
Instructions
Create a function timesFive that accepts one argument, multiplies it by 5, and returns the new value.

```javascript
// Example
function minusSeven(num) {
  return num - 7;
}

// Only change code below this line
function timesFive(num) {
  return num * 5; //ANSWER========================
}
```
## Assignment with a Returned Value 
If you'll recall from our discussion of Storing Values with the Assignment Operator, everything to the right of the equal sign is resolved before the value is assigned. This means we can take the return value of a function and assign it to a variable.
Assume we have pre-defined a function sum which adds two numbers together, then:
ourSum = sum(5, 12);
will call sum function, which returns a value of 17 and assigns it to ourSum variable.
======================================================
Instructions:
Call the processArg function with an argument of 7 and assign its return value to the variable processed.

```javascript
// Example
var changed = 0;
function change(num) {
  return (num + 5) / 3;
}
changed = change(10);
// Setup
var processed = 0;
function processArg(num) {
  return (num + 3) / 5;
}
// Only change code below this line
processed = processArg(7);
```
## Stand in Line 
In Computer Science a queue is an abstract Data Structure where items are kept in order. New items can be added at the back of the queue and old items are taken off from the front of the queue.

Write a function nextInLine which takes an array (arr) and a number (item) as arguments. Add the number to the end of the array, then remove the first element of array. The nextInLine function should then return the element that was removed.

```javascript
function nextInLine(arr, item) {
  // Your code here
  arr.push(item);
  var changed = arr.shift();
  return changed;  // Change this line
}

// Test Setup
var testArr = [1,2,3,4,5];

// Display Code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6)); // Modify this line to test
console.log("After: " + JSON.stringify(testArr));
```
## Understanding Boolean Values 
Another data type is the Boolean. Booleans may only be one of two values: true or false. They are basically little on-off switches, where true is "on" and false is "off." These two states are mutually exclusive.

Boolean values are never written with quotes. The strings "true" and "false" are not Boolean and have no special meaning in JavaScript.

```javascript
function welcomeToBooleans() {
return true; 
}
```
## Use Conditional Logic with If Statements 
If statements are used to make decisions in code. The keyword if tells JavaScript to execute the code in the curly braces under certain conditions, defined in the parentheses. These conditions are known as Boolean conditions because they may only be true or false.

When the condition evaluates to true, the program executes the statement inside the curly braces. When the Boolean condition evaluates to false, the statement inside the curly braces will not execute.

```javascript
if (condition is true) {
  statement is executed
}
```
When test is called with a value of true, the if statement evaluates myCondition to see if it is true or not. Since it is true, the function returns "It was true". When we call test with a value of false, myCondition is not true and the statement in the curly braces is not executed and the function returns "It was false".

```javascript
function test (myCondition) {
  if (myCondition) {
     return "It was true";
   }
     return "It was false";
   }
test(true);  // returns "It was true"
test(false); // returns "It was false"
```
Instructions:
Create an if statement inside the function to return "Yes, that was true" if the parameter wasThatTrue is true and return "No, that was false" otherwise

```javascript
// Example
function ourTrueOrFalse(isItTrue) {
  if(isItTrue) { 
    return "Yes, it's true";
  }
    return "No, it's false";
  }
// Setup
function trueOrFalse(wasThatTrue) {
  // Only change code below this line.
  if(wasThatTrue) {
    return "Yes, that was true";
  }
    return "No, that was false"; 
  // Only change code above this line.
  }
// Change this value to test
trueOrFalse(true);
```
## Comparison with the Equality Operator
If myVal is equal to 10, the equality operator returns true, so the code in the curly braces will execute, and the function will return "Equal". Otherwise, the function will return "Not Equal".

```javascript
function equalityTest(myVal) {
  if (myVal == 10) {
     return "Equal";
  }
  return "Not Equal";
}
```



```javascript
// Setup
function testEqual(val) {
  if (val == 12) { // Change this line
    return "Equal";
  }
  return "Not Equal";
}
// Change this value to test
testEqual(12);
```



```javascript
// Setup
function testStrict(val) {
  if (val === 7) { // Change this line
    return "Equal";
  }
  return "Not Equal";
}
// Change this value to test
testStrict(7);
```
## Comparison with the Inequality Operator 
Add the inequality operator != in the if statement so that the function will return "Not Equal" when val is not equivalent to 99

```javascript
// Setup
function testNotEqual(val) {
  if (val != 99) { // Change this line
    return "Not Equal";
  }
  return "Equal";
}
// Change this value to test
testNotEqual(10);
```
Add the strict inequality operator to the if statement so the function will return "Not Equal" when val is not strictly equal to 17

```javascript
// Setup
function testStrictNotEqual(val) {
  // Only Change Code Below this Line
  if (val !== 17) {
  // Only Change Code Above this Line
    return "Not Equal";
  }
    return "Equal";
  }
// Change this value to test
testStrictNotEqual(10);
```
## Comparison with greater/less Than Operators
Add the greater than operator to the indicated lines so that the return statements make sense.

```javascript
function testGreaterThan(val) {
  if (val > 100) {  // Change this line
    return "Over 100";
  }
  if (val > 10) {  // Change this line
    return "Over 10";
  }
    return "10 or Under";
  }
// Change this value to test
testGreaterThan(101);
```
Add the greater than or equal to operator to the indicated lines so that the return statements make sense.

```javascript
function testGreaterOrEqual(val) {
  if (val >= 20) {  // Change this line
      return "20 or Over";
  }
  if (val >= 10) {  // Change this line
      return "10 or Over";
  }
      return "9 or Under";
  }
// Change this value to test
testGreaterOrEqual(10);
```
Add the less than operator to the indicated lines so that the return statements make sense

```javascript
function testLessThan(val) {
  if (val < 25) {  // Change this line
    return "Under 25";
  }
  if (val < 55) {  // Change this line
    return "Under 55";
  }
    return "55 or Over";
  }
// Change this value to test
testLessThan(10);
```
Add the less than or equal to operator to the indicated lines so that the return statements make sense.

```javascript
function testLessOrEqual(val) {
  if (val <= 12) {  // Change this line
    return "Smaller Than or Equal to 12";
  }
  if (val <= 24) {  // Change this line
    return "Smaller Than or Equal to 24";
  }
    return "25 or More";
  }
// Change this value to test
testLessOrEqual(10);
```
Sometimes you will need to test more than one thing at a time. The logical and operator (&&) returns true if and only if the operands to the left and right of it are true.

The same effect could be achieved by nesting an if statement inside another if:

```javascript
if (num > 5) {
  if (num < 10) {
    return "Yes";
  }
}
return "No";
```
will only return "Yes" if num is between 6 and 9 (6 and 9 included). The same logic can be written as:

```javascript
if (num > 5 && num < 10) {
  return "Yes";
}
return "No";
```
Combine the two if statements into one statement which will return "Yes" if val is less than or equal to 50 and greater than or equal to 25. Otherwise, will return "No".

```javascript
function testLogicalAnd(val) {
  // Only change code below this line
  if (val >= 25 && val <=50 ) {
    return "Yes";
  }
    return "No";
  // Only change code above this line
  }
  // Change this value to test
testLogicalAnd(10);
```
## Comparisons with the Logical Or Operator
The logical or operator (||) returns true if either of the operands is true. Otherwise, it returns false.

The pattern below should look familiar from prior waypoints:

```javascript
if (num > 10) {
  return "No";
}
if (num < 5) {
  return "No";
}
return "Yes";
```
will return "Yes" only if num is between 5 and 10 (5 and 10 included). The same logic can be written as:

```javascript
if (num > 10 || num < 5) {
  return "No";
}
return "Yes";
```
Instructions
Combine the two if statements into one statement which returns "Outside" if val is not between 10 and 20, inclusive. Otherwise, return "Inside".

```javascript
function testLogicalOr(val) {
  // Only change code below this line
  if (val < 10 || val > 20 ) {
    return "Outside";
  }
    return "Inside";
// Only change code above this line
  }
// Change this value to test
testLogicalOr(15);
```
## Introducing Else Statements
When a condition for an if statement is true, the block of code following it is executed. What about when that condition is false? Normally nothing would happen. With an else statement, an alternate block of code can be executed.

```javascript
if (num > 10) {
  return "Bigger than 10";
} else {
  return "10 or Less";
}
```
Instructions:
Combine the if statements into a single if/else statement.

```javascript
function testElse(val) {
  var result = "";
  // Only change code below this line
  if (val > 5) {
    result = "Bigger than 5";
  } else {
    result = "5 or Smaller";  
  }
  // Only change code above this line
    return result;
  }
// Change this value to test
testElse(4);
```
## Introducing Else If Statements
If you have multiple conditions that need to be addressed, you can chain if statements together with else if statements.

```javascript
if (num > 15) {
  return "Bigger than 15";
} else if (num < 5) {
  return "Smaller than 5";
} else {
  return "Between 5 and 15";
}
```
Instructions:
Convert the logic to use else if statements.

```javascript
function testElseIf(val) {
  if (val > 10) {   
    return "Greater than 10"; 
  } else if (val < 5) { 
    return "Smaller than 5";
  } else {
    return "Between 5 and 10";
  }
}
// Change this value to test
testElseIf(7);
```
## Logical Order in If Else Statements
Order is important in if, else if statements.

The loop is executed from top to bottom so you will want to be careful of what statement comes first.

Take these two functions as an example.

Here's the first:

```javascript
function foo(x) {
  if (x < 1) {
    return "Less than one";
  } else if (x < 2) {
    return "Less than two";
  } else {
    return "Greater than or equal to two";
  }
}
```
And the second just switches the order of the statements:

```javascript
function bar(x) {
  if (x < 2) {
    return "Less than two";
  } else if (x < 1) {
    return "Less than one";
  } else {
    return "Greater than or equal to two";
  }
}
```
While these two functions look nearly identical if we pass a number to both we get different outputs.

```javascript
foo(0) // "Less than one"
bar(0) // "Less than two"
```
Instructions:
Change the order of logic in the function so that it will return the correct statements in all cases.

```javascript
function orderMyLogic(val) {
  if (val < 5) {
    return "Less than 5";
  } else if (val < 10) {
    return "Less than 10";
  } else {
    return "Greater than or equal to 10";
  }
}
// Change this value to test
orderMyLogic(7);
```
## Chaining If Else Statements 

if/else statements can be chained together for complex logic. Here is pseudocode of multiple chained if / else if statements:

```javascript
if (condition1) {
  statement1
} else if (condition2) {
  statement2
} else if (condition3) {
  statement3
. . .
} else {
  statementN
}
```
Instructions:
Write chained if/else if statements to fulfill the following conditions:
num < 5 - return "Tiny"
num < 10 - return "Small"
num < 15 - return "Medium"
num < 20 - return "Large"
num >= 20 - return "Huge"

```javascript
function testSize(num) {
  // Only change code below this line
  if (num < 5) {
    return "Tiny";
  } else if (num < 10) {
    return "Small";
  } else if (num < 15) {
    return "Medium";
  } else if (num < 20) {
    return "Large";
  } else if (num >= 20) {
    return "Huge";
  }
    return "Change Me";
  // Only change code above this line
}
  // Change this value to test
testSize(7);
```
## Golf Code 

Strokes	Return
1	"Hole-in-one!"
<= par - 2	"Eagle"
par - 1	"Birdie"
par	"Par"
par + 1	"Bogey"
par + 2	"Double Bogey"
>= par + 3	"Go Home!"


```javascript
function golfScore(par, strokes) {
  // Only change code below this line
  if (strokes == 1) {
    return "Hole-in-one!";
  } else if (strokes <= par - 2) {
    return "Eagle";
  } else if (strokes == par - 1) {
    return "Birdie";
  } else if (strokes == par) {
    return "Par";
  } else if (strokes == par + 1) {
    return "Bogey";
  } else if (strokes == par + 2) {
    return "Double Bogey";
  } else if (strokes >= par + 3) {
    return "Go Home!";
  } 
  return "Change Me";
  // Only change code above this line
}
  // Change these values to test
golfScore(5, 4);
```


## Selecting from many options with Switch Statements 
case values are tested with strict equality (===). The break tells JavaScript to stop executing statements. If the break is omitted, the next statement will be executed.


```javascript
switch (num) {
  case value1:
    statement1;
    break;
  case value2:
    statement2;
    break;
...
  case valueN:
    statementN;
    break;
}
```
Instructions:
Write a switch statement which tests val and sets answer for the following conditions:
1 - "alpha"
2 - "beta"
3 - "gamma"
4 - "delta"


```javascript
function caseInSwitch(val) {
  var answer = "";
  // Only change code below this line
  switch (val) {
      
    case 1: 
      answer = "alpha";
      break;
      
    case 2: 
      answer = "beta";
      break;
      
    case 3: 
      answer = "gamma";
      break;
      
    case 4:
      answer = "delta";
      break;
      
    default: 
      answer = "Invalid";
  }
  // Only change code above this line  
  return answer;  
}
  // Change this value to test
caseInSwitch(1);
```
A default statement should be the last case.

```javascript
switch (num) {
  case value1:
    statement1;
    break;
  case value2:
    statement2;
    break;
...
  default:
    defaultStatement;
}
```
Instructions
Write a switch statement to set answer for the following conditions:
"a" - "apple"
"b" - "bird"
"c" - "cat"
default - "stuff"

```javascript
function switchOfStuff(val) {
  var answer = "";
  // Only change code below this line
  switch(val) {
      
    case "a": 
      answer = "apple";
      break;
    case "b": 
      answer = "bird";
      break;
    case "c": 
      answer = "cat";
      break;
    default:
      answer = "stuff";
  }
  // Only change code above this line  
  return answer;  
}
// Change this value to test
switchOfStuff(1);
```
## Multiple Identical Options in Switch Statements 
Instructions
Write a switch statement to set answer for the following ranges:
1-3 - "Low"
4-6 - "Mid"
7-9 - "High"

Note
You will need to have a case statement for each number in the range.

```javascript
function sequentialSizes(val) {
  var answer = "";
  // Only change code below this line
  switch(val) {
    case 1:
    case 2: 
    case 3:
      answer = "Low";
      break;
    case 4:
    case 5:
    case 6:
      answer = "Mid";
      break;
    case 7: 
    case 8:
    case 9:
      answer = "High";
      break;
    default:
      answer = "Too High";    
  }
  // Only change code above this line  
  return answer;  
}
  // Change this value to test
sequentialSizes(1);
```
Instructions:
Change the chained if/else if statements into a switch statement.

```javascript
// CHANGE IF/ELSE // CHANGE IF/ELSE // CHANGE IF/ELSE

function chainToSwitch(val) {
  var answer = "";
  // Only change code below this line
  
  if (val === "bob") {
    answer = "Marley";
  } else if (val === 42) {
    answer = "The Answer";
  } else if (val === 1) {
    answer = "There is no #1";
  } else if (val === 99) {
    answer = "Missed me by this much!";
  } else if (val === 7) {
    answer = "Ate Nine";
  }
```



```javascript
  switch(val) {
      
    case "bob":
      answer = "Marley";
      break;
      
    case 42:
      answer = "The Answer";
      break;
      
    case 1: 
      answer = "There is no #1";
      break;
      
    case 99:
      answer = "Missed me by this much!";
      break;
      
    case 7:
      answer = "Ate Nine";
      break;
      
    default:
      answer = "Nothing Found";
  
  }
```
## Returning Boolean Values from Functions 
A common anti-pattern is to use an if/else statement to do a comparison and then return true/false:

```javascript
function isEqual(a,b) {
  if (a === b) {
    return true;
  } else {
    return false;
  }
}
```
Since === returns true or false, we can return the result of the comparison:

```javascript
function isEqual(a,b) {
  return a === b;
}
```



```javascript
function isLess(a, b) {
  // Fix this code
   return a < b;
}
  // Change these values to test
isLess(10, 15);
```
## Return Early Pattern for Functions 
When a return statement is reached, the execution of the current function stops and control returns to the calling location.

```javascript
function myFun() {
  console.log("Hello");
  return "World";
  console.log("byebye")
}
myFun();
```



```javascript
// Setup
function abTest(a, b) {
  // Only change code below this line
  if (a < 0 || b < 0) {
    return undefined;
  }
  // Only change code above this line
  return Math.round(Math.pow(Math.sqrt(a) + Math.sqrt(b), 2));
}
// Change values below to test your code
abTest(2,2);
```
## Counting Cards 
Count Change	Cards
+1	2, 3, 4, 5, 6
0	7, 8, 9
-1	10, 'J', 'Q', 'K', 'A'
You will write a card counting function. It will receive a card parameter and increment or decrement the global count variable according to the card's value (see table). The function will then return a string with the current count and the string "Bet" if the count is positive, or "Hold" if the count is zero or negative. The current count and the player's decision ("Bet" or "Hold") should be separated by a single space.

Example Output
"-3 Hold"
"5 Bet"

Hint
Do NOT reset count to 0 when value is 7, 8, or 9.

```javascript
var count = 0;

function cc(card) {
  // Only change code below this line
  switch(card) {
      
    case 2:
    case 3: 
    case 4: 
    case 5: 
    case 6:
      count++;
      break;
      
      
    case 10:
    case 'J':
    case 'Q':
    case 'K':
    case 'A':
      count--;
      break;
  
  }
  
 if (count > 0){
    return count + " Bet";
  } else {
    return count + " Hold";
  }
  // Only change code above this line
}

// Add/remove calls to test your function.
// Note: Only the last will display
cc(2); cc(3); cc(7); cc('K'); cc('A');
```
## Build JavaScript Objects
Objects are similar to arrays, except that instead of using indexes to access and modify their data, you access the data in objects through what are called properties.
Objects are useful for storing data in a structured way, and can represent real world objects, like a cat.

```javascript
var cat = {
  "name": "Whiskers",
  "legs": 4,
  "tails": 1,
  "enemies": ["Water", "Dogs"]
};
```
Instructions
Make an object that represents a dog called myDog which contains the properties "name" (a string), "legs", "tails" and "friends".

You can set these object properties to whatever values you want, as long "name" is a string, "legs" and "tails" are numbers, and "friends" is an array.

```javascript
// Example
var ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};
// Only change code below this line.
var myDog = {
  "name": "Kujo",
  "legs": 4,
  "tails": 1,
  "friends": ["Jojo", "Skruffy", "Tater"]
};
```
## Accessing Objects Properties with the Dot Operator
There are two ways to access the properties of an object: the dot operator (.) and bracket notation ([]), similar to an array.

The dot operator is what you use when you know the name of the property you're trying to access ahead of time.

Here is a sample of using the dot operator (.) to read an object property:

```javascript
var myObj = {
  prop1: "val1",
  prop2: "val2"
};
var prop1val = myObj.prop1; // val1
var prop2val = myObj.prop2; // val2
```
Instructions:
Read in the property values of testObj using dot notation. Set the variable hatValue equal to the object property hat and set the variable shirtValue equal to the object property shirt.

```javascript
// Setup
var testObj = {
  "hat": "ballcap",
  "shirt": "jersey",
  "shoes": "cleats"
};
// Only change code below this line
var hatValue = testObj.hat;      // Change this line
var shirtValue = testObj.shirt;    // Change this line
```
## Accessing Objects Properties with Bracket Notation 
The second way to access the properties of an object is bracket notation ([]). If the property of the object you are trying to access has a space in it, you will need to use bracket notation.

Here is a sample of using bracket notation to read an object property:

```javascript
var myObj = {
  "Space Name": "Kirk",
  "More Space": "Spock"
};
myObj["Space Name"]; // Kirk
myObj['More Space']; // Spock
//Note that property names with spaces in them must be in quotes (single or double).
```
Instructions:
Read the values of the properties "an entree" and "the drink" of testObj using bracket notation and assign them to entreeValue and drinkValue respectively.

```javascript
// Setup
var testObj = {
  "an entree": "hamburger",
  "my side": "veggies",
  "the drink": "water"
};
// Only change code below this line
var entreeValue = testObj["an entree"];   // Change this line
var drinkValue = testObj["the drink"];    // Change this line
```
## Accessing Objects Properties with Variables 
Another use of bracket notation on objects is to use a variable to access a property. This can be very useful for iterating through lists of the object properties or for doing the lookup.

Here is an example of using a variable to access a property:

```javascript
var someProp = "propName";
var myObj = {
  propName: "Some Value"
}
myObj[someProp]; // "Some Value"
```
Here is one more:

```javascript
var myDog = "Hunter";
var dogs = {
  Fido: "Mutt",
  Hunter: "Doberman",
  Snoopie: "Beagle"
}
var breed = dogs[myDog];
console.log(breed);// "Doberman"
//Note that we do not use quotes around the variable name when using it to access the property because we are using the value of the variable, not the name
```
Instructions:
Use the playerNumber variable to lookup player 16 in testObj using bracket notation.

```javascript
// Setup
var testObj = {
  12: "Namath",
  16: "Montana",
  19: "Unitas"
};
// Only change code below this line;
var playerNumber = 16;       // Change this Line
var player = testObj[playerNumber];   // Change this Line
```
## Updating Object Properties 
After you've created a JavaScript object, you can update its properties at any time just like you would update any other variable. You can use either dot or bracket notation to update.

For example, let's look at ourDog:



```javascript
var ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};
// Since he's a particularly happy dog, let's change his name to "Happy Camper". Here's how we update his object's name property:
ourDog.name = "Happy Camper"; or
ourDog["name"] = "Happy Camper";
// Now when we evaluate ourDog.name, instead of getting "Camper", we'll get his new name, "Happy Camper".
```
Instructions:
Update the myDog object's name property. Let's change her name from "Coder" to "Happy Coder". You can use either dot or bracket notation.

```javascript
// Example
var ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};
ourDog.name = "Happy Camper";
// Setup
var myDog = {
  "name": "Coder",
  "legs": 4,
  "tails": 1,
  "friends": ["Free Code Camp Campers"]
};
// Only change code below this line.
myDog.name = "Happy Coder";
```
## Add New Properties to a JavaScript Object
You can add new properties to existing JavaScript objects the same way you would modify them.
Here's how we would add a "bark" property to ourDog:
ourDog.bark = "bow-wow"; or ourDog["bark"] = "bow-wow";
Now when we evaluate ourDog.bark, we'll get his bark, "bow-wow".
====================================
Instructions:
Add a "bark" property to myDog and set it to a dog sound, such as "woof". You may use either dot or bracket notation.

```javascript
// Example
var ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};
ourDog.bark = "bow-wow";
// Setup
var myDog = {
  "name": "Happy Coder",
  "legs": 4,
  "tails": 1,
  "friends": ["Free Code Camp Campers"]
};
// Only change code below this line.
myDog.bark = "woof";
```
## Delete Properties from a JavaScript Object 
We can also delete properties from objects like this:

delete ourDog.bark;

Instructions:
Delete the "tails" property from myDog. You may use either dot or bracket notation.



```javascript
// Setup
var myDog = {
  "name": "Happy Coder",
  "legs": 4,
  "tails": 1,
  "friends": ["Free Code Camp Campers"],
  "bark": "woof"
};

// Only change code below this line.
delete myDog.tails;
```



```javascript
  switch(val) {
    case "alpha": 
      result = "Adams";
      break;
    case "bravo": 
      result = "Boston";
      break;
    case "charlie": 
      result = "Chicago";
      break;
    case "delta": 
      result = "Denver";
      break;
    case "echo": 
      result = "Easy";
      break;
    case "foxtrot": 
      result = "Frank";
  }
```
## Using Objects for Lookups
Objects can be thought of as a key/value storage, like a dictionary. If you have tabular data, you can use an object to "lookup" values rather than a switch statement or an if/else chain. This is most useful when you know that your input data is limited to a certain range.

Here is an example of a simple reverse alphabet lookup:

```javascript
var alpha = {
  1:"Z",
  2:"Y",
  3:"X",
  4:"W",
  ...
  24:"C",
  25:"B",
  26:"A"
};
alpha[2]; // "Y"
alpha[24]; // "C"

var value = 2;
alpha[value]; // "Y"
```
Instructions:
Convert the switch statement into a lookup table called lookup. Use it to lookup val and assign the associated string to the result variable.

```javascript
  // Setup
function phoneticLookup(val) {
  var result = "";
  // Only change code below this line
  var lookup = {
    "alpha"   : "Adams",
    "bravo"   :  "Boston", 
    "charlie" : "Chicago",
    "delta"   : "Denver",
    "echo"    : "Easy",
    "foxtrot" : "Frank" 
  };
    result = lookup[val];
  // Only change code above this line
  return result;
}
// Change this value to test
phoneticLookup("charlie");
```
## Testing Objects for Properties 
Sometimes it is useful to check if the property of a given object exists or not. We can use the .hasOwnProperty(propname) method of objects to determine if that object has the given property name. .hasOwnProperty() returns true or false if the property is found or not.

```javascript
var myObj = {
  top: "hat",
  bottom: "pants"
};
myObj.hasOwnProperty("top");    // true
myObj.hasOwnProperty("middle"); // false
```
Instructions
Modify the function checkObj to test myObj for checkProp. If the property is found, return that property's value. If not, return "Not Found".

```javascript
// Setup
var myObj = {
  gift: "pony",
  pet: "kitten",
  bed: "sleigh"
};
function checkObj(checkProp) {
  // Your Code Here
  if (myObj.hasOwnProperty(checkProp) === true) {
    return myObj[checkProp];
  } else {
    return "Not Found";
  }
}
// Test your code by modifying these values
checkObj("gift");
```
## Manipulating Complex Objects
Sometimes you may want to store data in a flexible Data Structure. A JavaScript object is one way to handle flexible data. They allow for arbitrary combinations of strings, numbers, booleans, arrays, functions, and objects.

Here's an example of a complex data structure:

```javascript
var ourMusic = [
  {
    "artist": "Daft Punk",
    "title": "Homework",
    "release_year": 1997,
    "formats": [ 
      "CD", 
      "Cassette", 
      "LP" ],
    "gold": true
  }
];
```
This is an array which contains one object inside. The object has various pieces of metadata about an album. It also has a nested "formats" array. If you want to add more album records, you can do this by adding records to the top level array.

Objects hold data in a property, which has a key-value format. In the example above, "artist": "Daft Punk" is a property that has a key of "artist" and a value of "Daft Punk".

JavaScript Object Notation or JSON is a related data interchange format used to store data.

```javascript
{
  "artist": "Daft Punk",
  "title": "Homework",
  "release_year": 1997,
  "formats": [ 
    "CD",
    "Cassette",
    "LP"
  ],
  "gold": true
}
// You will need to place a comma after every object in the array, unless it is the last object in the array.
```
Instructions
Add a new album to the myMusic array. Add artist and title strings, release_year number, and a formats array of strings.

```javascript
var myMusic = [
  {
    "artist": "Billy Joel",
    "title": "Piano Man",
    "release_year": 1973,
    "formats": [ 
      "CS", 
      "8T", 
      "LP" ],
    "gold": true
  },
  
  {
    "artist": "Bulos Beats",
    "title": "4:44",
    "release_year": 2018,
    "formats": 
    [
      "CD",
      "Cassette",
      "LP"
    ] 
  }
];
```
## Accessing Nested Objects 
Here is a nested object:

```javascript
var ourStorage = {
  "desk": {
    "drawer": "stapler"
  },
  "cabinet": {
    "top drawer": { 
      "folder1": "a file",
      "folder2": "secrets"
    },
    "bottom drawer": "soda"
  }
};
ourStorage.cabinet["top drawer"].folder2;  // "secrets"
ourStorage.desk.drawer; // "stapler"
```
Instructions
Access the myStorage object and assign the contents of the glove box property to the gloveBoxContents variable. Use bracket notation for properties with a space in their name.

```javascript
// Setup
var myStorage = {
  "car": {
    "inside": {
      "glove box": "maps",
      "passenger seat": "crumbs"
     },
    "outside": {
      "trunk": "jack"
    }
  }
};
var gloveBoxContents = myStorage.car.inside["glove box"]; // Change this line
```
## Accessing Nested Arrays 
As we have seen in earlier examples, objects can contain both nested objects and nested arrays. Similar to accessing nested objects, Array bracket notation can be chained to access nested arrays.

Here is an example of how to access a nested array:

```javascript
var ourPets = [
  {
    animalType: "cat",
    names: [
      "Meowzer",
      "Fluffy",
      "Kit-Cat"
    ]
  },
  {
    animalType: "dog",
    names: [
      "Spot",
      "Bowser",
      "Frankie"
    ]
  }
];
ourPets[0].names[1]; // "Fluffy"
ourPets[1].names[0]; // "Spot"
```
Instructions
Retrieve the second tree from the variable myPlants using object dot and array bracket notation.

```javascript
// Setup
var myPlants = [
  { 
    type: "flowers",
    list: [
      "rose",
      "tulip",
      "dandelion"
    ]
  },
  {
    type: "trees",
    list: [
      "fir",
      "pine",
      "birch"
    ]
  }  
];
var secondTree = myPlants[1].list[1]; // Change this line
```
## Iterate with JavaScript For Loops 
You can run the same code multiple times by using a loop.
The most common type of JavaScript loop is called a "for loop" because it runs "for" a specific number of times.
For loops are declared with three optional expressions separated by semicolons:
for ([initialization]; [condition]; [final-expression])
The initialization statement is executed one time only before the loop starts. It is typically used to define and setup your loop variable.
The condition statement is evaluated at the beginning of every loop iteration and will continue as long as it evaluates to true. When condition is false at the start of the iteration, the loop will stop executing. This means if condition starts as false, your loop will never execute.
The final-expression is executed at the end of each loop iteration, prior to the next condition check and is usually used to increment or decrement your loop counter.
In the following example we initialize with i = 0 and iterate while our condition i < 5 is true. We'll increment i by 1 in each loop iteration with i++ as our final-expression.

```javascript
var ourArray = [];
for (var i = 0; i < 5; i++) {
  ourArray.push(i);
}
//ourArray will now contain [0,1,2,3,4].
```
Use a for loop to work to push the values 1 through 5 onto myArray.

```javascript
// Example
var ourArray = [];
for (var i = 0; i < 5; i++) {
  ourArray.push(i);
}
// Setup
var myArray = [];
for (var i = 1; i < 6; i++) {
  myArray.push(i);
}
// Only change code below this line.
```
## Iterate Odd Numbers With a For Loop

```javascript
// Example
var ourArray = [];

for (var i = 0; i < 10; i += 2) {
  ourArray.push(i);
}

// Setup
var myArray = [];

// Only change code below this line.
for (var i = 1; i < 10; i += 2) {
  myArray.push(i);
}
```
## Count Backwards With a For Loop 
A for loop can also count backwards, so long as we can define the right conditions.

In order to count backwards by twos, we'll need to change our initialization, condition, and final-expression.

We'll start at i = 10 and loop while i > 0. We'll decrement i by 2 each loop with i -= 2.

```javascript
var ourArray = [];
for (var i=10; i > 0; i-=2) {
  ourArray.push(i);
}
  // ourArray will now contain [10,8,6,4,2].
```
Instructions
Push the odd numbers from 9 through 1 to myArray using a for loop.

```javascript
// Example
var ourArray = [];
for (var i = 10; i > 0; i -= 2) {
  ourArray.push(i);
}
// Setup
var myArray = [];
// Only change code below this line.
for (var i = 9; i > 0; i -= 2){
  myArray.push(i);
}
```
## Iterate Through an Array with a For Loop 
A common task in JavaScript is to iterate through the contents of an array. One way to do that is with a for loop. This code will output each element of the array arr to the console:

```javascript
var arr = [10,9,8,7,6];
for (var i=0; i < arr.length; i++) {
   console.log(arr[i]);
}
```
Remember that Arrays have zero-based numbering, which means the last index of the array is length - 1. Our condition for this loop is i < arr.length, which stops when i is at length - 1.
Instructions
Declare and initialize a variable total to 0. Use a for loop to add the value of each element of the myArr array to total.

```javascript
// Example
var ourArr = [ 9, 10, 11, 12];
var ourTotal = 0;

for (var i = 0; i < ourArr.length; i++) {
  ourTotal += ourArr[i];
}

// Setup
var myArr = [ 2, 3, 4, 5, 6];
var total = 0;

// Only change code below this line
for (var i = 0; i < myArr.length; i++){
  total += myArr[i];
}
```
## Nesting For Loops 
If you have a multi-dimensional array, you can use the same logic as the prior waypoint to loop through both the array and any sub-arrays. Here is an example:

```javascript
var arr = [
  [1,2], [3,4], [5,6]
];
for (var i=0; i < arr.length; i++) {
  for (var j=0; j < arr[i].length; j++) {
    console.log(arr[i][j]);
  }
}
// This outputs each sub-element in arr one at a time. Note that for the inner loop, we are checking the .length of arr[i],since arr[i] is itself an array.
```
Instructions:
Modify function multiplyAll so that it multiplies the product variable by each number in the sub-arrays of arr

```javascript
function multiplyAll(arr) {
  var product = 1;
  // Only change code below this line
  for(var i = 0; i < arr.length; i++){
    for(var j= 0; j < arr[i].length; j++){
      product *= arr[i][j];
    }
  }
  // Only change code above this line
  return product;
}
// Modify values below to test your code
multiplyAll([[1,2],[3,4],[5,6,7]]);
```
## Iterate with JavaScript While Loops
You can run the same code multiple times by using a loop.

Another type of JavaScript loop is called a "while loop", because it runs "while" a specified condition is true and stops once that condition is no longer true.

```javascript
var ourArray = [];
var i = 0;
while(i < 5) {
  ourArray.push(i);
  i++;
}
```
Instructions:
Push the numbers 0 through 4 to myArray using a while loop.

```javascript
// Setup
var myArray = [];
// Only change code below this line.
var i = 0;
while(i < 5) {
  myArray.push(i);
  i++;
}
```







```javascript
for (var x = 0; x < contacts.length; x++){
    if (contacts[x].firstName === firstName) {
        if (contacts[x].hasOwnProperty(prop)) {
            return contacts[x][prop];
        } else {
            return "No such property";
        }
    }
}
return "No such contact";
```
## Profile Lookup
We have an array of objects representing different people in our contacts lists.
A lookUpProfile function that takes firstName and a property (prop) as arguments has been pre-written for you.
The function should check if firstName is an actual contact's firstName and the given property (prop) is a property of that contact.
If both are true, then return the "value" of that property.
If firstName does not correspond to any contacts then return "No such contact"
If prop does not correspond to any valid properties then return "No such property"

```javascript
//Setup
var contacts = [
    {
        "firstName": "Akira",
        "lastName": "Laine",
        "number": "0543236543",
        "likes": ["Pizza", "Coding", "Brownie Points"]
    },
    {
        "firstName": "Harry",
        "lastName": "Potter",
        "number": "0994372684",
        "likes": ["Hogwarts", "Magic", "Hagrid"]
    },
    {
        "firstName": "Sherlock",
        "lastName": "Holmes",
        "number": "0487345643",
        "likes": ["Intriguing Cases", "Violin"]
    },
    {
        "firstName": "Kristian",
        "lastName": "Vos",
        "number": "unknown",
        "likes": ["Javascript", "Gaming", "Foxes"]
    }
];
function lookUpProfile(firstName, prop){
// Only change code below this line
for (var i = 0; i < contacts.length; i++) {
  if (contacts[i].firstName === firstName) {
    if (contacts[i].hasOwnProperty(prop)) {
      return contacts[i][prop];
    } else {
      return "No such property";
    }
  }
}
return "No such contact";
}
// Change these values to test your function
lookUpProfile("Akira", "likes");
```
## Generate Random Fractions with JavaScript
JavaScript has a Math.random() function that generates a random decimal number between 0 (inclusive) and not quite up to 1 (exclusive). Thus Math.random() can return a 0 but never quite return a 1

```javascript
function randomFraction() {
  return Math.random();
}
```
## Generate Random Whole Numbers with JavaScript 
Use Math.random() to generate a random decimal.
Multiply that random decimal by 20.
Use another function, Math.floor() to round the number down to its nearest whole number.
Remember that Math.random() can never quite return a 1 and, because we're rounding down, it's impossible to actually get 20. This technique will give us a whole number between 0 and 19.
Putting everything together, this is what our code looks like:
Math.floor(Math.random() * 20);
We are calling Math.random(), multiplying the result by 20, then passing the value to Math.floor() function to round the value down to the nearest whole number.


Instructions:
Use this technique to generate and return a random whole number between 0 and 9.

```javascript
var randomNumberBetween0and19 = Math.floor(Math.random() * 20);
function randomWholeNum() {
  return Math.floor(Math.random() * 10);
}
```
## Generate Random Whole Numbers within a Range 
Instead of generating a random number between zero and a given number like we did before, we can generate a random number that falls within a range of two specific numbers.
To do this, we'll define a minimum number min and a maximum number max.
Here's the formula we'll use. Take a moment to read it and try to understand what this code is doing:
Math.floor(Math.random() * (max - min + 1)) + min


Instructions:
Create a function called randomRange that takes a range myMin and myMax and returns a random number that's greater than or equal to myMin, and is less than or equal to myMax, inclusive.

```javascript
// Example
function ourRandomRange(ourMin, ourMax) {
  return Math.floor(Math.random() * (ourMax - ourMin + 1)) + ourMin;
}
ourRandomRange(1, 9);
function randomRange(myMin, myMax) {
  return Math.floor(Math.random() * (myMax - myMin + 1)) + myMin; 
}
var myRandom = randomRange(5, 15);
```
## Sift through Text with Regular Expressions 
Regular expressions are used to find certain words or patterns inside of strings.
For example, if we wanted to find the word the in the string The dog chased the cat, we could use the following regular expression: /the/gi
Let's break this down a bit:
/ is the start of the regular expression.
the is the pattern we want to match.
/ is the end of the regular expression.
g means global, which causes the pattern to return all matches in the string, not just the first one.
i means that we want to ignore the case (uppercase or lowercase) when searching for the pattern.


Instructions:
Select all the occurrences of the word and in testString.
You can do this by replacing the . part of the regular expression with the word and.

```javascript
// Setup
var testString = "Ada Lovelace and Charles Babbage designed the first computer and the software that would have run on it.";
// Example
var expressionToGetSoftware = /software/gi;
var softwareCount = testString.match(expressionToGetSoftware).length;
var expression = /and/gi;  // Change this Line
var andCount = testString.match(expression).length;
```
## Find Numbers with Regular Expressions 
We can use special selectors in Regular Expressions to select a particular type of value.
One such selector is the digit selector \d which is used to retrieve one digit (e.g. numbers 0 to 9) in a string.
In JavaScript, it is used like this: /\d/g.
Appending a plus sign (+) after the selector, e.g. /\d+/g, allows this regular expression to match one or more digits.
The trailing g is short for 'global', which allows this regular expression to find all matches rather than stop at the first match.

Instructions:
Use the \d selector to select the number of numbers in the string, allowing for the possibility of one or more digit.

```javascript
var testString = "There are 3 cats but 4 dogs.";
var expression = /\d+/g;  // Change this line
var digitCount = testString.match(expression).length;
```
## Find Whitespace with Regular Expressions 
We can also use regular expression selectors like \s to find whitespace in a string.
The whitespace characters are " " (space), \r (the carriage return), \n (newline), \t (tab), and \f (the form feed).
The whitespace regular expression looks like this:
/\s+/g

Instructions:
Use \s to select all the whitespace characters in the sentence string.

```javascript
var testString = "How many spaces are there in this sentence?";
var expression = /\s+/g;  // Change this line
var spaceCount = testString.match(expression).length;
```
## Invert Regular Expression Matches with JavaScript 
You can invert any match by using the uppercase version of the regular expression selector.
For example, \s will match any whitespace, and \S will match anything that isn't whitespace.

Instructions:
Use /\S/g to count the number of non-whitespace characters in testString.

```javascript
var testString = "How many non-space characters are there in this sentence?";

var expression = /\S/g;  // Change this line
var nonSpaceCount = testString.match(expression).length;
```






## 








# JavaScript Control Flow

```javascript
Assign value: =
Less than: <
Greater than: >
Less than or equal to: <=
Greater than or equal to: >=
Exactly eqal to: ===
Check not equal to: !==
Both must be "true": &&
Either can be "true": ||
Must be the opposite: !
```
## if/else Statements

```javascript
let needsCoffee = true;
if (needsCoffee === true) {
    console.log('Finding coffee');
} else {
    console.log('Keep on keeping on!');
}
```
1. Code between curly braces are blocks
1. if/else have two code blocks. If variable needsCoffee is true, program will run first block, otherweise will run the other block
1. needsCoffee is the condition

```javascript
var isSoccerFan = false;

if (isSoccerFan === true) {
  console.log("Goal!");
} else {
  console.log("No Goal!");
}
```
In JavaScript, all variables and conditions have a truthy or falsy value.

```javascript
let variableOne = 'I Exist!';
if (variableOne) {
// This code will run because variableOne contains a truthy value.
} else {
// This code will not run because the first block ran.
}
```
All variables that have been created and set are truthy (and will evaluate to true if they are the condition of a control flow statement) unless they contain one of the seven values listed below:

false
0 and -0
"" and '' (empty strings)
null
undefined
NaN (Not a Number)
document.all (something you will rarely encounter)


JavaScript provides an operator for swapping the truthiness and falsiness of values - the exclamation point (!)

```javascript
 let isPhoneCharged = true; 
if (!isPhoneCharged) {
  console.log('Plug in your phone!');
} else {
  console.log('No need to charge!');
}
```
## else if

```javascript
let stopLight = 'green';

if (stopLight === 'red') {
  console.log('Stop');
} else if (stopLight === 'yellow') {
  console.log('Slow down');
} else if (stopLight === 'green') {
  console.log('Go!');
} else {
  console.log('Caution, unknown!');
}
```


## Logical Operators

To say "both must be true," we use &&.
To say "either can be true," we use ||.

Example: 

```javascript
if (stopLight === 'green' && pedestrians === false) {
  console.log('Go!');
} else {
  console.log('Stop');
}
```


## Switch Statements

```javascript
let groceryItem = 'papaya';

switch (groceryItem) {
  case 'tomato':
    console.log('Tomatoes are $0.49');
    break;
  case 'lime':
    console.log('Limes are $1.49');
    break;
  case 'papaya':
    console.log('Papayas are $1.29');
    break;
  default:
    console.log('Invalid item');
    break;
}
```


## Ternary Operator

```javascript
let isNightTime = true;

if (isNightTime) {
  console.log('Turn on the lights!');
} else {
  console.log('Turn off the lights!');
}
```
or

```javascript
isNightTime ? console.log('Turn on the lights!') : console.log('Turn off the lights!');
```
isNightTime ? — the conditional statement followed by a question mark. This checks if isNightTime is truthy.
console.log ('Turn on the lights!') — this code will be executed if the condition is truthy.
: — a colon separates the two different blocks of code that can be executed.
console.log('Turn off the lights!'); — this code will be executed if the condition is falsy

```javascript
age >= 16 ? console.log('You are old enough to drive in the United States!') : console.log('You are not old enough to drive in the United States!');
```




# JavaScript Basics


## Comparisons
Comparisons need two things to compare and they will always return a boolean (true or false).

```javascript
Assign value: =
Less than: <
Greater than: >
Less than or equal to: <=
Greater than or equal to: >=
Exactly eqal to: ===
Check not equal to: !==
Both must be "true": &&
Either can be "true": ||
Must be the opposite: !
```


## Math
Generates random number between 0 and 1

```javascript
Math.random();
```
Generate a random number between 0 and 50 (likely be decimal)

```javascript
Math.random() * 50;
```
Math.floor rounds decimal down to whole number

```javascript
Math.floor(Math.random() * 50);
```


## Else If

If/else example:

```javascript
var needCoffee = true;
if (needCoffee) {
    console.log('Finding coffee');
} else {
    console.log('Keep on keeping on!');
}
```
if/else example: 

```javascript
var harryPotterFan = false;

if(harryPotterFan){
  console.log("Mischief Managed.");
} else {
  console.log("I lead a muggle\'s life.");
}
```
Code between curly braces are called blocks. if/else statements have two code blocks
Add more conditions to if/else with else if

```javascript
var stopLight = 'green';

if (stopLight === 'red') {
  console.log('Stop');
} else if (stopLight === 'yellow') {
  console.log('Slow down');
} else if (stopLight === 'green') {
  console.log('Go!');
} else {
  console.log('Caution, unknown!');
}
```
Example: 

```javascript
if (stopLight === 'green' && pedestrians === false) {
  console.log('Go!');
} else {
  console.log('Stop');
}
```


## Switch Statement
Switch statements when dealing with multiple else if conditions

```javascript
var groceryItem = 'papaya';

switch (groceryItem) {
  case 'tomato':
    console.log('Tomatoes are $0.49');
    break;
  case 'lime':
    console.log('Limes are $1.49');
    break;
  case 'papaya':
    console.log('Papayas are $1.29');
    break;
  default:
    console.log('Invalid item');
    break;
}
```
else/if compared to switch: 

```javascript
var moonPhase = 'full';

if (moonPhase === "full" || foggyNight){
  console.log("Howwwwlll!!");
} else if (moonPhase === "mostly full"){
  console.log("Arms and legs are getting hairier");
} else if (moonPhase === "mostly new"){
  console.log("Back on two feet");
} else {
  console.log("Invalid moon phase");
}
```
Switch:

```javascript
var moonPhase = 'full';

switch (moonPhase) {
 case 'full':
    console.log('Howwwwlll!!');
    break;
 case 'mostly full':
    console.log('Arms and legs are getting harrier');
    break;
 case 'mostly new':
    console.log('Back on two feet');
    break;
  default:
    console.log('Invalid moon phase');
    break;
}
```


## Functions
Functions are like recipes. They take data or variables, perform a set of tasks on them, 
and then return the result. 


Calculator Function:

```javascript
var calculatorOn = false;

function pressPowerButton() {
  if (calculatorOn) {
    console.log('Calculator turning off.');
    calculatorOn = false;
  } else {
    console.log('Calculator turning on.');
    calculatorOn = true;
  }
}

pressPowerButton();
// Output: Calculator turning on.

pressPowerButton();
// Output: Calculator turning off.

//Parameters are variables that we can set when we call the function: 
function multiplyByThirteen(inputNumber) {
  console.log(inputNumber * 13);
}
multiplyByThirteen(9);
// Output: 117
//inputNumber is a parameter, 9 would be the argument, therefore, arguments are provided
//when you call a function, and parameters receive arguments as their value.
```
Pizza Order Function:

```javascript
function takeOrder(topping){
  console.log(topping);
}
takeOrder(bacon);

//Set multiple parameters to function by separating with commas within functions parentheses 
function getRemainder(numberOne, numberTwo) {
  console.log(numberOne % numberTwo);
}

getRemainder(365, 27);
// Output: 14

//Same as above except return within function
function getRemainder(numberOne, numberTwo) {
  return numberOne % numberTwo;
}

console.log(getRemainder(365, 27));
// Output: 14

//take order function
function takeOrder(topping, crustType) {
  console.log('Order: ' + crustType + ' crust topped with ' + topping);
}

//Calling the function 3 times
takeOrder('bacon', 'thin'); 
takeOrder('pepperoni', 'regular');
takeOrder('pesto', 'thin');
```
## Scope



```javascript
//Scope: where within variable can be accessed. (global scope/function scope)

//If write variable OUTSIDE of function, it's in the global scope
//If write variable INSIDE of function, it's in the functional scope

//Example of global scope:
var laundryRoom = "Basement";
var mailRoom = "Room 1A"; 

console.log("Laundry: " + laundryRoom + ", Mail: " + mailRoom);
```


## Arrays

```javascript
myArray[] //access indexed item in array
.length // check how many items in array
.push() // add to end of array
.pop() // remove from end of array

// Bucket List:
// 0. Rappel into a cave
// 1. Take a falconry class
// 2. Learn to juggle
var bucketList = ['Rappel into a cave', 'Take a falconry class', 'Learn to juggle'];

//Arrays are lists. These lists can store different data types. Each position within list
//is numbered by javascript starting from 0 because javascript is 0 indexed.
var bucketList = ["Just", "Do", "It"];

console.log(bucketList); //Just = 0, Do = 1, It = 2

//We can select the first item in an array like this:

var bucketList = ['Rappel into a cave', 'Take a falconry class', 'Learn to juggle'];
var listItem = bucketList[0];
console.log(listItem);
// Output: 'Rappel into a cave'

//find number of items inside array: 
.length
//attach to any variable holding an array and will return number of items inside
//example: 
var bucketList = ['Rappel into a cave', 'Take a falconry class'];

console.log(bucketList.length);
// Output: 2

//.length also property for strings. Example: 'Hello World'.length output to 11 (num charcters in "Hello World")

.push() // allows us to add to end of array. Example: 
var bucketList = ['item 0', 'item 1', 'item 2'];
bucketList.push('item 3', 'item 4');
['item 0', 'item 1', 'item 2', 'item 3', 'item 4']; // result

.pop() // removes last item of an array
var bucketList = ['item 0', 'item 1', 'item 2'];
bucketList.pop();
console.log(bucketList); 
// Output: [ 'item 0', 'item 1' ]
```
## Loops

```javascript
// for loops, which let us loop a block of code a known amount of times.

// while loops, which let us loop a block of code an unknown amount of times.
var vacationSpots = ["Dubai", "China", "India"];

console.log(vacationSpots[0]);
console.log(vacationSpots[1]);
console.log(vacationSpots[2]);
//Above example would be life without a forloop. Would have to manually log each item in array

var animals = ["Grizzly Bear", "Sloth", "Sea Lion"];

for (var i = 0; i < animals.length; i++) {
  console.log(animals[i]);
}

// Output:
// Grizzly Bear
// Sloth
// Sea Lion

var vacationSpots = ["Dubai", "China", "India"];

for(var i=0; i < vacationSpots.length; i++){
  console.log(vacationSpots[i]);
}
//This would be the proper way of listing all items within array.


//BACKWARD ARRAY
var vacationSpots = ["Dubai", "China", "India"];

for(var i = vacationSpots.length - 1; i >= 0; i--){
  console.log("I would love to visit " + vacationSpots[i]);
}

//WHILE LOOPS
while (condition) {
  // code block that loops until condition is false
}
//Inside the parentheses, we can insert a condition. 
//As long as the variable evaluates to true the block of code will loop.
```


## Dom & jQuery

```javascript
$('.skillset'); // selects html/css class
$('#skillset'); // selects html/css ID
$('.my-selector').hide(); // hide elements
$('.example-class').fadeIn(400); // fade in over milliseconds. 
on('click'). // event listener - on click
$('.example-class').on('click', function() {
  // execute the code here when .example-class is clicked.
});
$('.example-class').show();
$('example-class').toggle(); // Display or hide the matched elements.
$('.example-class').toggleClass('active') // toggle CSS class on the jQuery selector
$(this) // selects the clicked element if multiples within class
$('.example-class').on('click', function() {
$(this).toggleClass('active');
});

```















































































