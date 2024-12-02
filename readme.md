# JavaScript Interview Questions

## 1. What is Scope & Scope Chain in JavaScript?
 - **Scope:** Scope determines where variables are defined and where they can be accessed.
 - **Scope Chaining:** Scope chain in Javascript is looking for variables.If variable not found in current scope javascript looks that variable for its next outer scope. and keeps looking the outward until it reaches the Global Scope.

## 2. What is the type of variable in JS when it is defined without using the `var`, `let`, or `const` keywords?
```javascript
if (true) {
    variable = 10;
}
console.log(variable);
// output => 10
```
* Explanation: `var` is the implicit type of variable when a variable is declared without `var`, `let`, or `const` keywords.

## 3. What is Hoisting in JavaScript?
Hoisting is a JavaScript behavior where functions and variable declarations are moved to the top of their respective scopes during the compilation phase.

### Example: Function Hoisting
```javascript
myFunction();

function myFunction() {
    console.log("Hello!");
}
// output => Hello
```

### Example: Variable Hoisting
```javascript
x = 10;
console.log(x);
// output => 10
var x;
// Note: This method will not work for `let` & `const` keywords
```

## 4. What is JSON?
* JSON (JavaScript Object Notation) is a lightweight data interchange format.
* JSON consists of **key-value** pairs.

```json
{
    "name": "John Doe",
    "age": 30,
    "isStudent": false
}
```

## 5. What are `variables`? What is the difference between `var,let,and const`
* Variables are used to **store** data
  
```javascript
var count = 10
```
* `var` is function scope 
* `let & const` is block scope


* **var** creates a **function-scoped** varible.

```javascript
// using var 
function example(){
    if(true){
        var count = 10
        console.log(count)
        // output 10
    }

    console.log(count);
    // output: 10
}
```

* let creates a **block-scoped** variable
```javascript
// using let 
function example(){
    if(true){
        let count = 10;
        console.log(count);
        // output: 10
    }
    console.log(count)
    // output:Uncaught
    // Reference Error:
    // count is not defined
}
```
* const can be assigned only once, and its value **cannot be changed** afterwards
```javascript
// using constant
const z  = 10;
z=20;
// This will result in an error
console.log(z);
```
## 6. What are data types in JS?
* A data type determines the **type of a variable**
* We have two data types in JavaScript
  - Primitive Data Types
  - Non-Primitive Data Types
* Primitive Data Types:
  - Primitive Data Types can hold only **single** values
  - Primitive Data Types are **immutable**,meaning their values,once assigned cannot be changed
  - Primitive Data Types are **simple** data types
```javascript
// Number
let age = 25;

// string
let message = 'Hello';

// Boolean
let isTrue = true;

// undefined
let x;
console.log(x);
// Output: undefined 

// Null
let y = null
console.log(y)
// output:null
```
* Non-Primitive Data Types:
  - Non-Primitive Data Types can hold multiple values & methods
  - They are mutable and their values can be changed
  - Non-primitive data types are **complex** data types
```Javascript
// Non-Primitive Data Types

//  1.Object
 let person = {
    "name": "John Doe",
    "age": 30,
    console.log(this.name)
 }

//  2.Array
let oddNumbers = [1,3,5]

//  3.Function
 4.Date
 5.RegExp
```
## 7. What is the difference between null and undefined in JS?
```javascript
let value1 = 0;
let value2 = '';
```
* (A stand on the wall with also a paper holder) Means there is a **valid variable** with also a value of **data type number**
```javascript
let value3 = null
```
* (There is just a stand on the wall)  Means there is a **valid variable** with a value of **no data type**.
```javascript
let value4
// undefined
```
* (There is nothing on the wall) Means variable **incomplete variable** and not assigned anything
```javascript
// Undefined 
let undefinedVariable : // no value assigned 
console.log(undefinedVariable);
// Output:undefined
```
 * Undefined
    - undefined: When a variable is declared but has **not been assigned a value**, it is automatically initialized with undefined
```javascript
// Null
let nullVariable = null;//null assigned 
console.log(nullVariable);
// Output:null
```
*Null
  - Null:null variable are intentionally assigned a **null value**

## 8. Where you will use null & where you will use undefined?
 * **Undefined** 
      - undefined can be used when you don`t have the value right now, but you will get it after some logic operation.
 * **Null** 
      - Null can be used, when you are sure you do not have any value for the particular variable

## 9. What is the use of typeof operator
 * **typeof** operator is used to determine the **type** of each variable.
 * Real application use -> typeof operator can be used to **validate the data** received from external sources(api)

## 10. What is type coercion in JS?
 * Type coercion is the automatic conversion of values from  one data type to another during certain operations of comparisions
```javascript
let string  = '42';
let number = 42;
let boolean  = true;
let nullValue = null;

// Type coercion  - automatic conversion 
console.log(string + number)  //output:"4242"
console.log(number + boolean) //Output:43  because boolean have 1 value
console.log(number == string) //output:true
console.log(boolean == 1 )//output:true because boolean have 1 value
console.log(boolean  + nullValue) // output: 1 because null have 0 value

```

## 11. What are use of type coercion in real life?
 * Uses of type coercion:
     - Type coercion can be used during **String and Number concatenation**
     - Type coercion can be used while using **Comaparion operators**

## Chapter 3:Operators & Conditions

## 12. What is Operator precedence 
  * As per operator precendence,operators with higher precedence are **evaluated first**
    -  Ex:**BODMAS** Rule
       - B = Brackets
       - O = Order
       - D = Division
       - M = Multliplication
       - A = Addition
       - S = Subtraction
```javascript
let a = 6;
let b = 3;
let c = 2;

// BracketOf-Division-Multiplication-Add-Sub
let result = a + b * c + (a-b);

console.log(result);
// Output:15
```

## 13. What is the difference between unary,binary & ternary operators?
 * **Unary Operator**
```javascript
let a  = 5;
// Unary operator

// Single operand
let b = -a;
console.log(b)
// Output: -5
console.log(++a)
//Output: 6
```
* **Binary Operator**
```Javascript
let x  = 10;
let y  = 3;

// Binary operator
// Two operands
let z = x + y;
console.log(z);
// Output:13
```
* **Ternary Operator**
```javascript
// Ternary operator
// Three operands
let result = condition ? 'Yes' : 'No';

console.log(result);
// Output: 'Yes'
```

## 14. What is Short-circuit evalation in JS?
 * Short-circuit evaluation stops the execution as soon as the **result can be determined** without **evaluating** the remaining sub-expressions
```javascript
// Short-circuit evaluation with logical AND
let result1 = false && someFunction()
console.log(result1)
// Output:false

// Short-circuit evaluation with logical OR 
let result2 = true || someFunction();
console.log(result2);
// Output:true
```
## 15. What are the types of conditions statements in JS?
* Types of condition statements
   - If/else statement
   - Ternary operator 
   - Switch statement
* **If/else statement** 
```javascript
// IF/Else Statement
let x= 5;
if(x>10){
    console.log("1")
}else if(x < 5){
    console.log("2")
}else{
    console.log("3")
}
// Output: '3'
```
*  **Ternary operator**
```javascript
let  y = 20;
let  z = y > 10 ? "1" : "0";
console.log(z)
// Output: '1'
```
* **Switch Statement**
```javascript
let a = 5;
switch(a){
    case 1:
    console.log("1");
    break;
    case 5:
    console.log("2");
    break;
    default:
    console.log("3")
}
// Output:'2'
```
## 16. What is the difference between == and ===?
 * **Loose Equality:**
   - Loose Equality(==) operator compares two values for equality after performing **type coercion**
```javascript
// Loose Equality
console.log(1 == '1');
console.log(true == 1);
//Output: true
```
* **Strict Equality:**
   - Strict Equality(===) operator compares two values for equality **without** performing type coercion
```javascript
//Strict Equality 
console.log(1=== '1');
console.log(true == 1);
//Output: false
```
## 17. What is the difference between Spread and Rest operator in JS?
 * **Spread operator:**
    - The spread operator(...)is used to expand or spread elements from an iterable (such as an array,string, or object)into individual elements.
```javascript
// Spread operator Examples 
const array = [1,2,3]
console.log(...array);
//Output:1,2,3
```
## Used of Spread Operator
 * **Copying an Array :**
```Javascript
// Copying an array
const originalArray = [1,2,3]
const copiedArray  = [...originalArray]
console.log(copiedArray)
// Output:[1,2,3] 
```
 * **Merging Arrays** 
```javascript
const Array1 = [1,2,3]
const Array2  = [4,5]
const mergedArray = [...Array1, ...Array2]
console.log(mergedArray)
// Output:[1,2,3,4,5]
```
 * **Passing Multilple Arguments to a Function**
```javascript
// passing multiple arguments to a function 
const numbers = [1,2,3,4,5]
function sum(a,b,c,d,e){
    console.log(a+b+c+d+e) //Output:15
}
sum(...numbers)
```
* **Rest Operator:**
    - The rest operator is used in function parameters to collect all **remaining arguements** into an array
```javascript
// Rest Operator Example
function display(first, second, ...restArguements){
    console.log(first); //Output:1
    console.log(second); //Output:2

    console.log(remaining); //Output: [3,4,5]
}
```
## 18. What are Array in JS? How to get,add & remove elements from arrays?
 * An array is a data type that allows you t **store multiple values** in a single variable
```javascript
// Array 
let fruits = ['apple','banana','orange']
```
 * **Get:** 
   - indexof()
   - find()
   - filter()
   - slice()
* **Add:**
   - push()
   - concat
*  **Remove:**
   -  pop()
   -  shift()
   -  splice()
* **Modification & Iteration:**
   - map()
   - forEach()
* **others**
   - join()
   - length()
   - sort()
   - reverse()
   - reduce()
   - some()
   - every()
## 19. What is indexOf() method in Array?
 * IndexOf() method **gets the index** of a specified element in the array
```javascript
//Example Array
const array = [1,2,3,4,5];
let a = array.indexOf(3)
console.log(a)
// Output:2
```
## 20. What is the difference between find() and filter() methods an Array?
 * **Find()**
     - find() method get the **first element** that sattisfies a condition.
```Javascript 
//Example Array 
const array = [1,2,3,4,5];
let c = array.find((num)=> num % 2 === 0);
console.log(c)
//Output:2
```
 * **Filter()**
     - filter()  method **get an array of elements** that satisfies a condition
```javascript
//Example array 
const array = [1,2,3,4,5];
let c = array.filter((num)=> num % 2 === 0);
console.log(c)
//Output:[2,4]
// result will be return an array in filter method 
```
 * **Silce()**
    - Silce() method get a **subset of the array** from start index to end index (end not included)
```javascript
const array  = ["a","b","c","d","e"]
let e = array.slice(1,4)
//output:['b','c','d']
```
## 21. What is the difference between push() and concat() methods an array 
 * **push()**
      - Push() will **modify the original array** itself
``` javascript
let array1  = [1,2]
// using push
array1.push(3,4)
console.log(array1)
//output:[1,2,3,4]
```
 * **Concat** 
      - concat() method will create the new array and not modify the original array
```javascript
let array2 =  [5,6]
//using concat()
let array3 = array2.concat(7,8);
console.log(array3)
//output:[5,6,7,8]
console.log(array2)
//orginal array is not modified 
// output:[5,6]
```

## 22. What is difference between pop() and shift() methods of an array?
 * **pop()**
     - pop() will remove the **last element** of the array
```javascript
//using pop()
let arr1 = [1,2,3,4]
let popped  = arr1.pop()
console.log(popped)
// Output:4
console.log(arr1)
//output:[1,2,3]
```
 * shift()
    -  shift() will remove the **first element** of the array
```javascript
let arr1 = [1,2,3,4]
let shifted  = arr1.shift()
console.log(shifted)
// Output:1
console.log(arr1),3
//output:[2,3,4]
```
## 23. What is the splice() method of an array?
 * The splice() method is used to **add**,**remove**, or **replace** elements in an array
```javascript
array.splice(startIndex,deleteCount,...itemsToAdd);

let letters  = ['a','b','c']

//Add 'x' and 'y' at index 1
letters.splice(1,0,'x','y')
console.log(letters);
//output:['a','x','y','b','c']

// Removes 1 element starting from index 1
letters.splice(1,1)
console.log(letters);
//Output:['a','y','b','c']

//Replaces the element at index 2 with 'q'
letters.splice(2,1,'q')
console.log(letters)
//output:['a','y','q','c']
```


## 24. What is the difference between the slice() and splice() methods of an array?
  * The **slice()** method is used get a subset of the array from start index to the end index (end not included)
  * The **splice()** method is used to**add , remove or replace** elements in an array

## 25. What is the difference map() and forEach() array methods of an Array?
  
  * **map():**
      - The **map()** method is used when you want to modify each element of an array and create a **new array** with the modified values.
```javascript
//using map()
let arr1  = [1,2,3]
let mapArray = arr1.map((e)=> e * 2 );
console.log(mapArray)
//map return a new array
// output:[2,4,6]
```
  * **forEach():** 
     - The **forEach()** method is used when you want to perform some operaton on each element of an array **without creating a new array**.
```javascript
//using forEach()
let arr2  = [1,2,3];
arr2.forEach((e)=>{
    console.log(e * 2 )
});
//Does not return anything 
//output:2 4 6 
console.log(arr2)
//output:[1,2,3]
```
## 

## 27. What is Array Destructuring in JS?
 * Array destructuring allows you to extract elements from an array and assign them to **individual variables** in a single elements
 * Array destructuring is introduced in **ECMAScript 6 (ES6)**
```javascript
// Example Array 
const fruits = ['apple','banana','orange']

// Array destructuring 
const [firstFruit,secondFruit,thirdFruit] = fruits

console.log(firstFruit) //output :apple
console.log(secondFruit) //output :banana
console.log(thirdFruit)//output :orange
``` 
## 28. What are array-like objects in JS?
 * Array-like objects are objects that have indexed elements and a length property, **similar to arrays,** but they may not have all the methods of arrays like push() ,pop() & others
```javascript
sum(1,2,3)
//Arguments Object
function sum(){
    console.log(arguements) //output:[1,2,3]
    console.log(arguements.length) //output:3
    console.log(arguements[0]) //output:1
}
//String 
const str = 'hello'
console.log(str); //Output:hello
console.log(str.length); //output:5
console.log(str[0])

//Accessing HTML Collection
var boxes = document.getElementsByClassName('box')
//Accessing elements in HTML Collection using index
console.log(boxes[0])
//Accessing length property of html collection
console.log(boxes.length)
```

## How to convert an array like object into an array?
```Javascript
// Example array-like object 
var arraylike = {0:'a',1:'b',2:'c',length:3} //This is not an array this is a key-Value pairs

// Using Array.from()
var array1 = Array.from(arraylike)
console.log(array1)
// Output:['a','b','c']
// It will be the array of only values from the original obj not the keys just only only values

//Using Spread syntax(...)
var array2 = [...arrayLike];
console.log(array2);
// output:['a','b','c']

// Using Array.prototype.slice.call()
var array3 = Array.prototype.slice.call(arrayLike);
console.log(array3);
// Output:['a','b','c']
```
## What is a **loop?** What are the **types** of loops in JS?
 * A Loop is a programming way to run a piece of **code repeatedly** until a certain condition is met
 * In JavaScript we have four types of loop 
    - JavaScript Loops
        * for
        * while
        * do-while
        * for..of
        * for..in
```Javascript
// for-loop
for(let i = 0; i < 5;  i++){
    console.log(i)
}
// Output:0 1 2 3 4
```
## What is the difference between **while** & **for** loops?
 *  for loop allows to iterate a block of code a **specific number** of times
 *  for loop is better for condition with initialization and with increment because all can be set in just **one line of code**
```javascript
// for-loop
for(let i = 0; i < 5;  i++){
    console.log(i)
}
// Output:0 1 2 3 4
```
**While**
  - While loop execute a block of code while a **certain condition** is true
  - while loop is better when there is **only condition**, no initialization, no increment
```javascript
// While loop
let j =0;

while(j<5){
    console.log(j);
    j++
}
// Output:0 1 2 3 4

// condition only While loop 
while("a"=="a"){
    console.log("print")
}
// output:Happy(infinity)
// note this log will print infinity because we make the condition always true in real world we use break statement to break the loop
```

## What is the difference between **while** and **do-while** loops?
**While loop**
   - While loop execute a block of code while a certain **condtion** is true
```javascript
// While loop
let j =0;

while(j<5){
    console.log(j);
    j++
}
// Output:0 1 2 3 4

```
**Do While Loop**
   - The do-While loop is similar to the while loop,except that the block of code is **excuted at least once,** even if the condition is false
```JAVASCRIPT
// do-while loop
let k = 0;

do{
    console.log(k);
    k++
} while(k > 1)
//output :0
```

## What is the difference between **break** and **continue** statement?
 - The **Break** statement is used to terminate the loop.
```javascript
// Break Statement
for(let i = 0; i<=5; i++){
    if(i===3){
        break;
    }
    console.log(i)
}
// Output: 1 2
```
 - The **Continue** statement is used to **skip the current iteration** of the loop and move on the next iteration
```javascript
for (let i = 1; i<=5; i++){
    if(i===3){
        continue;
    }
    console.log(i)
}
// output:1 2 4 5
```
## What is the difference between **for** and **for of** loop in JS?
 - for loop is slightl more complex having more lines of code whereas **for ..of is much simpler and beter for iterating arrays**
```Javascript
let arr = [1,2,3];

// for loop has more code
for (let i = 0; i <arr.length; i++){
    console.log(arr[i])
}
// output:1 2 3

// for of is much simpler
for(let val of arr){
    console.log(val)
}
// output:1 2 3
```
## 35. What is the difference between **for...of & for..in loop?**
 - for ..of loop is used to loop through the **values** of an object like arrays,strings.
 - it allows you to access each value **directly,** without having to use an index.
```javascript
// for of is much simpler
let arr = [1,2,3];
for(let val of arr){
    console.log(val)
}
// output:1 2 3
```
**for..in loop**
- for ..in loop is used to loop throgh the **properties** of an object.
- it allows you to iterate **over the keys of an object** and access the values associated by using keys as the index.
```javascript
// for-in loop
const person = {
    name:'Happy',
    role:'Developer'
};

for (let key in person){
    console.log(person[key])
}
// Output:Happy Developer
```
## what is forEach method? compare it for..of and for..in loop?
 - forEach() is a method available on arrays or object that allows you to **iterate over each element** of the array and perform some action on each element.
```Javascript
consr array = [1,2,3]

// for...of loop
for (let item of array){
    console.log(item)
}
// Output: 1 2 3

// forEach method 
array.forEach(function (item){
    console.log(item)
})
// Output: 1 2 3

const person = {
    name:'Happy',
    role:'Developer'
};

for (let key in person){
    console.log(person[key])
}
// Output:Happy Developer

// forEach method
Object.values(person).forEach(value=>{
    console.log(value)
})
// Output: Happy Developer
```
## When to use **for ..of loop** and when to use **forEach method** in applications?
**for-of-loop**
 -  for-of loop is suitable when you need **more control over the loop**,such as using break statement or continue statement inside.
```Javascript
const array = [ 1,2,3 ]

// for-of-loop
for(let item of array){
    console.log(item);

    if(item===2){
        break;
    }
}
// output: 1 2
```
**forEach()**
   -  forEach() is a method **iterate over each element** of the array and perform some action on each element.
```javascript
// forEach method 
array.forEach(function(item){
    console.log(item);
    if(item === 2){
        break;
    }
});
// Error:Illegal break statement
```
## CHAPTER-6 FUNCTION

## What are **FUNCTION** in JS? What are the types of funtion?
  - A function is a **reusable block of code** that performs a specific task
  - Types of function
      - Named Function
      - Anonymous Function
      - Function Expression
      - Arrow Function
      - Arrow Function
      - IIFE
      - Callback Function
      - Higher-Order Function

## What is the difference between **named** and **anonymous** functions?When to **use** what in applications?
**Named Functions**
 -  Named functions have a **name identifier**
```javascript
// Named Function
// Funtion Declaration

function sum(a,b){
    return a+b
};

console.log(add(5,3))
// output:8
```
   - use named functions for **big and complex** logics
   - use when you want to **reuse** one function at multiple places.
**Anonymous Function**
  - Anonymous functions **do not have a name identifier** and cannot be referenced directly by name
```javascript
// Anonymous Function

console.log(function(a,b){
    return a * b
}(4,5));
// Output:20
```
  - use Anonymous functions for **small logics.**
  - use when want to use a function in a **single place**
## What is function expression in JS?
  - A function expression is a way to define a function by **assigning it to a variable**
```javascript
// Anonymous Function Expression

const add  = function (a,b){
    return a + b 
};

console.log(add(5,3))
// Output:8

// Named Function Expression

const add  = function sum(a,b){
    return a + b;
};

console.log(add(5,3))
// Output:8
```


## What are Arrow Functions in JS? What is it use?
  - Arrow Function, also known as fat arrow functions, is a **simpler and shorter** way to defining functions in javascript

## What are **Callback Functions**? What is it use?
  - A callback function is a function that  is **passed as an arguement** to another function
```javascript
function add(x,y){
    return x + y
}

let a  = 3, b = 5;
let result  = add(a,b)
console.log(result)
// Output:8

function display (x, y , operation){
    var result   = operation(x + y)
    console.log(result)
}
display(10,5,add)
```
## What is Highe-order-function in JS
  - A Function which accepts one or more callback function is a **Higher Order Function**
  - when Function return a fucntion as a result is also a higher order function 
-  Higher Order Function
    1.  Take one or more functions as **arguements** (callback function) OR
    2.  **return** a function as a result
**1st Type**
```javascript
// Take one or more functions as arguments
function hof(func){
    func()
}
hof(sayHello)
function sayHello(){
    console.log('Hello!')
}
//Output:hello
```
**2nd Type**
```javascript
// Retrun a function as a result
fucntion createAdder(number){
    return function (value){
        return value + number
    };
}
const addFive = createAdder(5)

console.log(addFive(2))

// Output:7
```
## What is the difference between **arguements** and **parameters**?
  - Parameters are the **placeholders** defined in the function declaration
```javascript
// a and b are parameters
function add(a,b){
    console.log(a+b)
}
```
  - Arguements are the **actual values passed** to a function when it is  called or invoked
```javascript
add(3,4)
// 3 and 4 are arguements
```
## In how many ways can you **pass arguements** to a function?
  - Positional Arguements
  - Named Arguements
  - Arguements Object
**Positional Arguements**
```javascript
// positional Arguements 
function add(a,b){
    console.log(a+b)
}
add(3,4);
// output:7
```
**Named Arguements**
```javascript            
var person ={
    name:"Happy",
    role:"Developer"
};

function greet(person){
    console.log(person.name+""+person.role)
}
greet(person);
// output:Happy Developer
```
**Arguements Object**
```javascript
sum(1,2,3)

// Arguements object
fucntion sum(){
    console.log(arguements[0])
    // Output:1
    console.log(arguements[1])
    // Output:2
    console.log(arguements[2])
    // Output:3
    console.log(arguements.length)
    // Output:3
}
```
## How do you use **default parameters** in a function?
 - In javascript, default parameters allow you to specify **default values** for function paramters.
```javascript
// Function with default parameter value
function greet(name = 'yusrin'){
    console.log('hello,' + name + '!')
}
greet()
// Output:hello,yusrin!
greet('Misfer')
// Output:hello,Misfer!
```
## What is the use of **event handling** in JS?
  - Event handling is the process of **responding to user actions** in a web page
  - The **addEventListener** method of javascript allows to attach an **event name** and with the **function** you want to perform on that event.
```javascript
<button id = 'myButton'>Click me</button>
// Get a reference to the button element
const button = document.getElementById('myButton');

// Add an event listener for the 'click' event
button.addEventListener('click',function(){
      alert('Button clicked!')
})
```
## What are **First-Class** fucntions in JS?
 - A programming language is said to have First-Class-functions in that language are treated like **Other Variables**
**Functions trated like variables**
-  Assignable
-  Passable as Arguements
-  Retrunable as Values
```Javascript
// 1. Assigning functions like a variable
const myFunction  = function (){
    console.log('Interview,Happy')
};
myFunction(); //Output:"Interview,Happy"


function double(number){
    return number * 2;
}
// 2. Passing function as an arguement like a variable
function performOperation(double,value){
    return double(value)
}
console.log(performOperation(double,5))  //Output:10


// 3. A function that returns another function 
function createSimpleFunction(){
    return function(){
        console.log('I am Return function')
    }
}
const simpleFunction  = createSimpleFunction()
simpleFunction()  //Output:I am Return function
```    
## What are **Pure** and **Impure** fucntions in JS?
  - **Pure Function**
     - A pure function is a function that always produces the **same output for the same input**
     - Pure functions cannot modify the **state**
     - Pure functions cannot have **side Effects**
```Javascript

// Pure function
function add(a,b){
    return a + b;
}
console.log(add(3,5));
// output: 8

// If we call multiple times with the same arguements we get the same output 
console.log(add(3,5));
// same output:8
```
 - **Impure Function**
   -   An impure function,can produce **different outputs for the same input**
   -   Impure functions can modify the state
   -   Impure functions can have **side effects**
```javascript
// Impure function
let total = 0;

function addToTotal = (value){
    total += value
    return total
}
console.log(addToTotal(5))
// Output:5

// If I change total = 5
console.log(addToTotal(5))
// Not same output:10
```
## What is function currying?
  - Currying in the javascript transforms a function with multiple arguments into a **nested series of functions,** each taking a single arguement.
  - Advantage: **Reusability,modularity,and specilization,** Big, complex functions with multiple arguements can be broken down into small,reusable functions with fewer arguements.
```javascript
// Regular function that takes two arguements and return thei product

function multiply (a,b){
    return a * b 
}

// Curried version of the multiply function 
function curriedMultiply(a){
    return function (b){
        return a * b
    }
}

// Create a specialized function for doubling a number 
const double  = curriedMulitply(2){
    console.log(double(5))
    // Output:10 (2 * 5)
}

// create a specilized function for tripling a number 
const triple  = curriedMultiply(3)
console.log(triple(5))
// Output:15 (3 * 5)
```
## What is Closure in JavaScript?
 - In Javascript **Closure** is created when a function remembers and accesses variables from its outer function,even after the function outer function has already finished executing.
```Javascript
function outerFunction(){
    let message = 'Hello from the outer function!'

    function innerFunction(){
        console.log(message)
    }

    return innerFunction
}

const inner  = outerFunction()
inner() //Output:"Hello from the outer function!"
```
## What are **call**,**apply** and **bind** methods in JS?
 - call,apply,and bind are three methods in javascript that are used to work with functions and **control how they are invkoked** and what context they operate in.
 - THese method provide a way to manipulate the **this value** and pass arguements to fucntions. 
```Javascript
// Defining a fucntion that uses the 'this' context and an arguement 
function sayHello(message){
    console.log(`${message},${this.name}`)
}
const person = {name:"Happy"}

// 1.Call  - Using the 'call' method to invoke the function 
// with a specific context and arguement
sayHello.call(person,'Hello');
// Output:"Hello,Happy"

// 2.Apply  - using the 'Apply' method to invoke the function 
// with a specific context and an array of arguments 
sayHello.apply(person,['Hi'])
// output:'Hi,Happy'

// 3.Bind  - Using the 'Bind' method to create a new function 
// with a specific context (mot invoking it immediately)
const greetPerson = sayHello.bind(person)
greetPerson('greetings')
// Output:'greetings,Happy'
```

## CHAPTER-7:STRING

## What is a **String**? 
 - A String is a **data type** used to **store and manipulate data**

```javascript
// Single Quotes ('')
var str1 = 'Hello';
```

## What are **template literal** and **string interpolation** in strings?
 - A template literal, also known as a template string, is a feature introduces in ECMAScript 2015(ES6) for **string interpolation** and **multiline strings** in javascript.
```Javascript
// Backticks(``)
// Template lierals with string interpolation
var myName  = 'Happy'
var str3 = `Hello ${myname}`
console.log(str3)
// output: Hello Happy

// Template literals for multiline strings
var multilineStr = `
This is a multiline string
`
```
## What is difference between **single quotes('')**,**double quotes('')** & **backticks(``) **?
```Javascript

// Single Quotes ('')
var str1 = 'Hello';

// Double Quotes ("")
var str1 = "Hello";

// Backticks(``)
// Template lierals with string interpolation
var myName  = 'Happy'
var str3 = `Hello ${myname}`
console.log(str3)
// output: Hello Happy

// Template literals for multiline strings
var multilineStr = `
This is a multiline string
`
```
## What are some important **string operations** in JS?
```Javascript
// Add multiple string
let str1 = 'Hello'
let str2 = 'World'

let result = str1 + " " + str2
console.log(result);
// Output : Hello World

// Using concat() method 
let result2 = str1.concat(" ",+str2);
console.log(result2)
// Output : Hello World

// Extract a portion of a string
let subString = result.substring(6,11)
console.log(6,11) // start Index to end Index
// Output : World

// Retrieve the length of a string 
console.log(result.length)
// Output:11

// Convert a string to uppercase or lowercase 
console.log(result.toUpperCase())
// Output :HELLO WORLD 
console.log(result.tolowerCase())
// Output:hello world

// Split a string into an array of substrings
// based on a delimeter
let arr = result.split(' ')
console.log(arr)
// Output:["Hello","World"]

// Replace occurances of a substring within a string 
console.log(result.replace('World','Javascript'))
// output:Hello Javascript

// Remove leading and trailing whitespace
let str = '     Hello World     '
let trimmedStr  = str.trim()
console.log(trimmedStr);
// Output:Hello World
```
## What is string immutability?
 - Strings in Javascript are considered **immutable** because you **cannot modify** the contents of an existring string directly
```javascript

var str  ='javascript'

// creates a new string 
str = str  + ' Happy'
```
## In how many ways you can **concatenate strings?**
 - +Operator
 - Concat() method 
 - Template literals
 - Join() method

## Chapter 8:DOM

## What is DOM? What is the difference between HTML and DOM?
 - The DOM (Document Object Model) represents the web page as a **tree-like structure** that allows javascript to dynamically access and manipulate the content and structure of a web page.

## Chapter 9:Error Handling

## What is Error Handling in JS?
 - 

## 62. Placeholder question 62

## 63. Placeholder question 63

## 64. Placeholder question 64

## 65. Placeholder question 65

## 66. Placeholder question 66

## 67. Placeholder question 67

## 68. Placeholder question 68

## 69. Placeholder question 69

## 70. Placeholder question 70

## 71. Placeholder question 71

## 72. Placeholder question 72

## 73. Placeholder question 73

## 74. Placeholder question 74

## 75. Placeholder question 75

## 76. Placeholder question 76

## 77. Placeholder question 77

## 78. Placeholder question 78

## 79. Placeholder question 79

## 80. Placeholder question 80

## 81. Placeholder question 81

## 82. Placeholder question 82

## 83. Placeholder question 83

## 84. Placeholder question 84

## 85. Placeholder question 85

## 86. Placeholder question 86

## 87. Placeholder question 87

## 88. Placeholder question 88

## 89. Placeholder question 89

## 90. Placeholder question 90

## 91. Placeholder question 91

## 92. Placeholder question 92

## 93. Placeholder question 93

## 94. Placeholder question 94

## 95. Placeholder question 95

## 96. Placeholder question 96

## 97. Placeholder question 97

## 98. Placeholder question 98

## 99. Placeholder question 99

## 100. Placeholder question 100
