---
hide:
  - navigation
---
# Javascript
# Javascript for Beginners
- [Javascript for Begineers in 2 Hours](https://www.youtube.com/watch?v=e2fKYP_7B_Y) by Keerti Puruswani
- [Javascript Ebook](https://javascript.info/js) - A free ebook style guide for learning javascript.

## JS Basics
Execute any javascript code in browser by going to any webpage, right click -> Inspect -> Console. Every browser has its own implementation of javascript engine. Eg: In Google Chrome, its called V8 Engine.
```
console.log('hello');

//Variables and Data Types
//Primitive/Value Types
let x='hello world!'; //string
let y=1.2 //number
let z=true; //boolean
z=7 //type of variable can be dynamically changed with reassignmnet
let a; //undefined 
x=null //null (not to use undefined and instead use null)

console.log(x)
console.log(typeof(x))

//Reference Types - Objects, Arrays, Functions
//Arrays and functions are objects as well.
//Objects
let product = {
	name:'pixel 8',
	category:'mobile',
	rating:4.2
}
//Accessing items inside object
console.log(product.category)
console.log(product['category'])

//Arrays
let items = ['mobile', true, 8.0] //can contain different data types
console.log(items[0]) //logs mobile

//Functions
function createProduct(name) {
	console.log('Product name is '+name);
}
createProduct('iPhone 10');
```

Functions are first class citizen - we can pass functions as arguments to another functions. These are called 'Higher Order Functions'.
```
//Different ways in which a function can be defined
function sum_1(a,b){
	return a+b;
}

let sum_2 = function(a,b){
	return a+b;
}

let sum_3 = (a,b) => a+b;

//Functions can be defined within another function and returned

```

Execution Context - The environment where the javascript code is executed. Default is Global Execution Context (GEC)
Each function call creates a new execution context and gets added to the callstack
There are two phases in the execution context - memory phase and code phase.
- Memory phase - Variables are created
- Code phase - Code is executed

Hoisting - The concept where variables and functions be accessed before they are defined (due to memory phase before the execution of the 1st line)


### const vs let vs var
const and let are more strict and won't allow usage before initialization
const - Use when value should not be changed
let - Use when values can be changed
var - Avoid

Temporal Dead Zone - Getting reference error before variables are initialized when using const or let.

const and let are block scoped, while var is global scoped
{
	let a=10;
	const b=5;
	var c=6;
	console.log(a);
	console.log(b);
	console.log(c);
}
console.log(c); //c can be accessed outside the block as its var, but a or b cannot be accessed

Lexical scope - The concept where a variable is checked within the local scope and if not found, it will search in the outer scope.
Function + Lexical scope - Closure

### Function Callbacks, Event Queue and Event Loop

```
function callbackfn(){
	console.log("Callback function executed");
}

setTimeout(callbackfn, 500);

//Alternatively, as an anonymous function
setTimeout(function(){console.log("Alternate way")}, 500);
//Or
setTimeout(()=> console.log("Another Alternate way"),500);
```

### Promises
Object that represents the state of async. Has 3 states - Pending, fulfilled, rejected.

```
function getData() {
	return new Promise((resolve, reject)=> {
		setTimeout(() => {
			resolve('data fetched');
		},5000)
	})
}

getData()
	.then(result => { 
		console.log(result);
		})
	.catch(error => {
		console.error(error);
	})
```

#### Nested Promises
```
myPromise = new Promise((resolve, reject) =>{
	resolve('42');
})

myPromise.then((result)=> {console.log("1st result is ",result)}).then((result)=> {console.log("2nd result is ",result)}).then((result)=>{console.log("3rd result is "+result)}).catch(error => {console.error(error)})
```

### Async and Await
TBD

#### Callback Hell/Pyramid of Doom

asyncOperation1(arg1, (result1) => { 
	asyncOperation2(result1, (result2)=>{
		asyncOperation3(result2, (result3)=>{ //and so on})
	})})


## DOM Model
The HTML structure gets converted to a DOM tree, which can then be accessed/set using javascript. 

Some of the most commonly used DOM functions are:
```js
document.querySelector("h1") //Query using Tag Selector. Returns only the 1st match and ignores the rest.
document.querySelector(".title") //Query using ID Selector
document.querySelector("#my-class") //Query using Class Selector

document.querySelectorAll("h1") //Returns an array of all matched h1 elements

document.querySelector("#my-class h1") //Nested search. Searches for a h1 tag which is present inside the class "my-class"
``` 
PS: Above is the javascript way of querying. One of the most popular javascript libraries is jQuery, which is much more concise and easy to use.  To include jQuery, refer to [jQuery releases](https://releases.jquery.com/) section. Include the jQuery javascript above your javascript include statement in HTML:
```js
<script src="https://code.jquery.com/jquery-3.6.3.min.js" integrity="sha256-pvPw+upLPUjgMXY0G+8O0xUf+/Im1MZjXxxgOcBQBXU=" crossorigin="anonymous"></script>
```

## Event Listener
Add an event listener function to a HTML element and this would make the function to be executed when the event occurs.
```js
function myFunction(){
	alert("Function triggered");
}

document.querySelector("h1").addEventListener("click",myFunction); //Adds the function "myFunction" as a listener to the 1st h1 element's click event
```

The above example can also be done using anonymous function as below:
```js
document.querySelector("h1").addEventListener("click",function (){
	alert("Function triggered");
}
); 
```
You can associate multiple HTML elements to a common function. To know which HTML element triggered the function, we can get to know using "this", as below.
```js
document.querySelector("h1").addEventListener("click",function (){
	alert(this);
	console.log(this.innerHTML);
	this.style.color = "red";
}
); 
```
Although you can set an element's style property like color using "this.style.color", you may not always able to read the color property using this, unless the element style property is explicitly set. When the property is set using CSS styles, then you would not be able to read this value. For more details, please refer to [this stackover flow post](https://stackoverflow.com/a/37501154).

To add events for keyboard actions, these events can be attached to the document directly. Adding an argument to the event listener would provide details on what caused the event.
```js
document.addEventListener("keydown", function(event){console.log(event.key)};
```
## Adding and Removing CSS Classes from Javascript
To dynamically add/remove a CSS class from a HTML object, use querySelector to select the object and then use add/remove functions as shown below:
```js
document.querySelector("#myId").classList.add("css-class-name");
document.querySelector("#myId").classList.remove("css-class-name");
```
Instead, using jQuery,  the same can be done using:
```js
$("#myId").addClass("css-class-name");
$("#myId").removeClass("css-class-name");
```
To check if a HTML element has a class:
```js
$("#myId").hasClass("css-class-name");
```
## Updating Text of HTML Element
Using jQuery, we can update text of a HTML element as shown below.
```js
$("#myheading").text(); //Returns the text
$("#myheading").text("My New Heading"); //Updates the text

$("#myheading").html(); //Returns the inner HTML present which would include styles like <b>, <i>
$("#myheading").html("<b>My New</b> <i>Heading</i>"); //Updates the inner HTML with the styling provided
```

## Timeout Function
Here is the syntax for timeout function in javascript:
```js
setTimeout(<function>, timeout_value_ms);
```
Using anonymous function:
```js
setTimeout(function(){
document.querySelector("#myId").classList.add("css-class-name");
}, 100);
```

## Constructor Function
A constructor function in javascript is equivalent to a class in other programming languages. A constructor function would be similar to a normal function with the difference of constructor function names would be in Pascal case ("MyStudent" instead of "myStudent")
```js
function MyStudent(name, age, marks){
	//Properties
	this.name = name,
	this.age = age,
	this.marks = marks,
	
	//Methods
	this.calculateTotal = function (){
		var total = 0;
		for (var i=0;i<this.marks.length;i++){
			total += this.marks[i];
		}
		return total;
	}
}

s1 = new MyStudent("John", 14, [85,90,92]);
console.log(s1.calculateTotal());
```
## Map
Map function is used to traverse an array and apply a custom function over each element of the array. The output of Map function would also be an array of the same size as the input array.
```js
var myArray = [2,3,6,7,9,10]

function double(x){
return 2 * x;
}

myNewArray = myArray.map(double);
console.log(myNewArray);
```
Alternatively, using anonymous function:
```js
var myArray = [2,3,6,7,9,10]

myNewArray = myArray.map(function (x){
return 2 * x;
});
console.log(myNewArray);
```
## Filter
Filter function is used to traverse an array using a custom function which checks for a boolean condition and returns a subset of the array, when the condition is true.
```js
var myArray = [2,3,6,7,9,10]

myNewArray = myArray.filter(function (x){
return x > 6;
});
console.log(myNewArray);
```
## Reduce
Reduce function is used to traverse an array using a custom function and reduce the entire array to a single element.
```js
var myArray = [2,3,6,7,9,10]

myNewArray = myArray.reduce(function (aggregator, x){
return aggregator + x;
});
console.log(myNewArray);
```
## Find and FindIndex
Find the first element that matches the given condition. Use FindIndex to get the index of the first matched element.

Added in ES6.
```js
var myArray = [2,3,6,7,9,10]

Num = myArray.find(function (x){
return x>6;
});
console.log(Num);

NumIndex = myArray.findIndex(function (x){
return x>6;
});
console.log(NumIndex);
```
## Fat Arrow (=>)
```js
var myArray = [2,3,6,7,9,10]

myNewArray = myArray.map(function (x){
return 2 * x;
});

//Above anonymous function can still be reduced using fat arrow function as below.
myNewArray = myArray.map(x => 2 * x);
console.log(myNewArray);
```