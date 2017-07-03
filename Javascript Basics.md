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
