# JavaScript Documentation

Welcome to the JavaScript section of Web Development Made Easy!

## Table of Contents

### Part 1: Fundamentals
- [Introduction to JavaScript](#introduction-to-javascript)
- [Setting Up Your Environment](#setting-up-your-environment)
  - [Browser Console](#browser-console)
  - [Code Editors](#code-editors)
  - [Running JavaScript](#running-javascript)
- [JavaScript Basics](#javascript-basics)
  - [Variables (var, let, const)](#variables)
  - [Data Types](#data-types)
  - [Operators](#operators)
  - [Type Coercion and Conversion](#type-coercion-and-conversion)
- [Control Flow](#control-flow)
  - [If/Else Statements](#if-else-statements)
  - [Switch Statements](#switch-statements)
  - [Ternary Operator](#ternary-operator)
- [Loops](#loops)
  - [For Loop](#for-loop)
  - [While Loop](#while-loop)
  - [Do-While Loop](#do-while-loop)
  - [For...of and For...in](#for-of-and-for-in)
- [Functions](#functions)
  - [Function Declaration](#function-declaration)
  - [Function Expression](#function-expression)
  - [Arrow Functions](#arrow-functions)
  - [Parameters and Arguments](#parameters-and-arguments)
  - [Return Values](#return-values)
  - [Scope](#scope)
- [Arrays](#arrays)
  - [Creating Arrays](#creating-arrays)
  - [Array Methods](#array-methods)
  - [Iterating Arrays](#iterating-arrays)
- [Objects](#objects-detailed)
  - [Creating Objects](#creating-objects)
  - [Object Properties and Methods](#object-properties-and-methods)
  - [Object Destructuring](#object-destructuring)
- [Strings](#strings)
  - [String Methods](#string-methods)
  - [Template Literals](#template-literals)

### Part 2: Advanced Topics
- [DOM Manipulation](#dom-manipulation)
- [Events](#events)
- [Asynchronous JavaScript](#asynchronous-javascript)
- [Fetch API and AJAX](#fetch-api-and-ajax)
- [ES6+ Features](#es6-features)
- [Advanced Functions](#advanced-functions)
- [Object-Oriented Programming](#object-oriented-programming)
- [Advanced Array Methods](#advanced-array-methods)
- [Error Handling](#error-handling-detailed)
- [Local Storage and Session Storage](#local-storage-and-session-storage)
- [Regular Expressions](#regular-expressions)

### Part 3: Best Practices & Tips
- [Code Organization](#code-organization)
- [Performance Optimization](#performance-optimization)
- [Debugging](#debugging)
- [Security Best Practices](#security-best-practices)
- [Modern JavaScript Tooling](#modern-javascript-tooling)
- [Testing JavaScript](#testing-javascript)
- [Common Mistakes to Avoid](#common-mistakes-to-avoid)
- [Resources and Further Learning](#resources-and-further-learning)

---

## Part 1: Fundamentals

### Introduction to JavaScript

JavaScript is the programming language of the web. It's what makes websites interactive and dynamic, allowing you to create everything from simple form validations to complex web applications.

**What JavaScript Does:**
- Makes web pages interactive (clicks, hovers, form submissions)
- Manipulates HTML and CSS dynamically
- Communicates with servers (fetching/sending data)
- Stores data locally in the browser
- Creates animations and visual effects
- Powers full-stack applications (Node.js)

**Key Characteristics:**
- **Interpreted** - Runs directly in the browser, no compilation needed
- **Dynamically typed** - Variables can hold any type of data
- **Single-threaded** - Executes one operation at a time (but handles async well)
- **Multi-paradigm** - Supports functional, object-oriented, and event-driven programming

```javascript
// Your first JavaScript
console.log("Hello, World!");

// Variables and simple operations
let name = "Alice";
let age = 25;
console.log(`${name} is ${age} years old.`);
```

### Setting Up Your Environment

#### Browser Console

Every modern browser has a built-in JavaScript console. It's the quickest way to test code.

**Opening the Console:**
- **Chrome/Edge**: `F12` or `Ctrl+Shift+J` (Windows) / `Cmd+Option+J` (Mac)
- **Firefox**: `F12` or `Ctrl+Shift+K`
- **Safari**: Enable Developer menu in Preferences, then `Cmd+Option+C`

**Using the Console:**
```javascript
// Type directly in console
2 + 2                          // Returns: 4
"Hello".toUpperCase()          // Returns: "HELLO"
document.title                 // Returns the page title

// Multi-line code: Shift+Enter for new line
let x = 10;
let y = 20;
console.log(x + y);            // 30

// Clear console
console.clear();
```

#### Code Editors

For serious development, use a proper code editor:

**VS Code (Recommended)**
- Free, powerful, huge extension ecosystem
- Built-in terminal and debugger
- IntelliSense (code completion)
- Extensions: ESLint, Prettier, Live Server

**Other Options:**
- **WebStorm** - Full IDE, paid but powerful
- **Sublime Text** - Fast and lightweight
- **Atom** - Customizable, open-source

**Essential VS Code Extensions:**
- **Live Server** - Auto-refresh browser on save
- **ESLint** - Find and fix problems
- **Prettier** - Code formatting
- **JavaScript (ES6) code snippets** - Quick snippets

#### Running JavaScript

**1. In HTML file:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>My Page</title>
</head>
<body>
    <h1>Hello!</h1>
    
    <!-- Inline script -->
    <script>
        console.log("Script loaded!");
    </script>
    
    <!-- External script (recommended) -->
    <script src="app.js"></script>
</body>
</html>
```

**2. Script placement:**
```html
<!-- At end of body (traditional - ensures DOM is loaded) -->
<body>
    <!-- content -->
    <script src="app.js"></script>
</body>

<!-- In head with defer (modern - loads async, runs after DOM) -->
<head>
    <script src="app.js" defer></script>
</head>

<!-- In head with async (loads and runs immediately when ready) -->
<head>
    <script src="app.js" async></script>
</head>
```

**3. In Node.js:**
```bash
# Install Node.js from nodejs.org
node app.js
```

### JavaScript Basics

#### Variables

Variables store data. JavaScript has three ways to declare them:

```javascript
// var - old way, function-scoped, avoid using
var oldWay = "I'm function scoped";

// let - block-scoped, can be reassigned
let score = 0;
score = 10;              // OK
score = "hello";         // OK (dynamic typing)

// const - block-scoped, cannot be reassigned
const PI = 3.14159;
// PI = 3;               // ERROR!

const user = { name: "Alice" };
user.name = "Bob";       // OK! Object contents can change
// user = {};            // ERROR! Can't reassign the variable
```

**Naming Rules:**
```javascript
// Valid names
let userName = "Alice";        // camelCase (preferred)
let user_name = "Bob";         // snake_case
let $element = document.body;  // can start with $
let _private = "secret";       // can start with _

// Invalid names
// let 2fast = "error";        // Can't start with number
// let my-var = "error";       // No hyphens
// let let = "error";          // No reserved keywords
```

**Best Practices:**
- Use `const` by default
- Use `let` only when you need to reassign
- Never use `var` in modern JavaScript
- Use descriptive, camelCase names

#### Data Types

JavaScript has 8 data types: 7 primitives + Object.

**Primitive Types:**
```javascript
// String - text
let name = "Alice";
let greeting = 'Hello';
let template = `Hello, ${name}!`;    // Template literal

// Number - integers and decimals
let age = 25;
let price = 19.99;
let negative = -10;
let infinity = Infinity;
let notANumber = NaN;

// BigInt - very large integers
let bigNumber = 9007199254740991n;
let anotherBig = BigInt("123456789012345678901234567890");

// Boolean - true or false
let isActive = true;
let isLoggedIn = false;

// Undefined - declared but not assigned
let something;
console.log(something);    // undefined

// Null - intentional absence of value
let empty = null;

// Symbol - unique identifier
let id = Symbol("id");
let id2 = Symbol("id");
console.log(id === id2);   // false (always unique)
```

**Object Type:**
```javascript
// Object - collection of key-value pairs
let person = {
    name: "Alice",
    age: 25,
    isStudent: true
};

// Array - ordered list (technically an object)
let colors = ["red", "green", "blue"];

// Function - callable object
let greet = function(name) {
    return `Hello, ${name}!`;
};

// Checking types
typeof "hello"      // "string"
typeof 42           // "number"
typeof true         // "boolean"
typeof undefined    // "undefined"
typeof null         // "object" (historic bug)
typeof {}           // "object"
typeof []           // "object"
typeof function(){} // "function"
```

#### Operators

**Arithmetic Operators:**
```javascript
let a = 10, b = 3;

a + b       // 13 (addition)
a - b       // 7 (subtraction)
a * b       // 30 (multiplication)
a / b       // 3.333... (division)
a % b       // 1 (modulo/remainder)
a ** b      // 1000 (exponentiation, 10³)

// Increment/Decrement
let x = 5;
x++         // Returns 5, then x becomes 6
++x         // x becomes 7, then returns 7
x--         // Returns 7, then x becomes 6
--x         // x becomes 5, then returns 5

// Assignment operators
let n = 10;
n += 5      // n = n + 5 → 15
n -= 3      // n = n - 3 → 12
n *= 2      // n = n * 2 → 24
n /= 4      // n = n / 4 → 6
n %= 4      // n = n % 4 → 2
n **= 3     // n = n ** 3 → 8
```

**Comparison Operators:**
```javascript
// Equality
5 == "5"       // true (loose equality, converts types)
5 === "5"      // false (strict equality, no conversion)
5 != "5"       // false
5 !== "5"      // true

// Always use === and !== to avoid surprises!

// Relational
5 > 3          // true
5 < 3          // false
5 >= 5         // true
5 <= 4         // false

// Comparing strings (alphabetical)
"apple" < "banana"    // true
"a" < "b"             // true
```

**Logical Operators:**
```javascript
// AND (&&) - both must be true
true && true      // true
true && false     // false
false && true     // false

// OR (||) - at least one must be true
true || false     // true
false || true     // true
false || false    // false

// NOT (!) - inverts the value
!true             // false
!false            // true
!!value           // Convert to boolean

// Short-circuit evaluation
let result = false && expensiveFunction();  // Function never runs
let value = null || "default";              // Returns "default"

// Nullish coalescing (??) - only null/undefined
let name = null ?? "Anonymous";             // "Anonymous"
let count = 0 ?? 10;                        // 0 (not null/undefined)
let count2 = 0 || 10;                       // 10 (0 is falsy)
```

#### Type Coercion and Conversion

**Automatic Coercion (implicit):**
```javascript
// String concatenation with +
"5" + 3           // "53" (number → string)
"Hello" + 5       // "Hello5"

// Math operations convert to numbers
"5" - 3           // 2
"5" * "2"         // 10
"10" / 2          // 5

// Boolean context
if ("hello") {}   // true (non-empty string is truthy)
if (0) {}         // false (0 is falsy)

// Falsy values: false, 0, -0, "", null, undefined, NaN
// Everything else is truthy
```

**Explicit Conversion:**
```javascript
// To String
String(123)           // "123"
(123).toString()      // "123"
123 + ""              // "123"

// To Number
Number("123")         // 123
Number("abc")         // NaN
Number(true)          // 1
Number(false)         // 0
Number(null)          // 0
Number(undefined)     // NaN
parseInt("42px")      // 42
parseFloat("3.14")    // 3.14
+"123"                // 123 (unary plus)

// To Boolean
Boolean(1)            // true
Boolean(0)            // false
Boolean("hello")      // true
Boolean("")           // false
!!value               // Convert any value to boolean
```

### Control Flow

#### If/Else Statements

```javascript
let age = 18;

// Simple if
if (age >= 18) {
    console.log("You can vote!");
}

// If-else
if (age >= 18) {
    console.log("Adult");
} else {
    console.log("Minor");
}

// If-else if-else
if (age < 13) {
    console.log("Child");
} else if (age < 20) {
    console.log("Teenager");
} else if (age < 60) {
    console.log("Adult");
} else {
    console.log("Senior");
}

// Multiple conditions
let hasTicket = true;
let hasID = true;

if (age >= 18 && hasTicket && hasID) {
    console.log("Welcome to the show!");
}

if (age < 18 || !hasID) {
    console.log("Sorry, you can't enter.");
}

// Nested if
if (age >= 18) {
    if (hasTicket) {
        console.log("Enjoy the show!");
    } else {
        console.log("Please buy a ticket.");
    }
}
```

#### Switch Statements

```javascript
let day = "Monday";

switch (day) {
    case "Monday":
        console.log("Start of work week");
        break;
    case "Tuesday":
    case "Wednesday":
    case "Thursday":
        console.log("Midweek");
        break;
    case "Friday":
        console.log("TGIF!");
        break;
    case "Saturday":
    case "Sunday":
        console.log("Weekend!");
        break;
    default:
        console.log("Invalid day");
}

// Without break (fall-through)
let month = 2;
let days;

switch (month) {
    case 1: case 3: case 5: case 7: case 8: case 10: case 12:
        days = 31;
        break;
    case 4: case 6: case 9: case 11:
        days = 30;
        break;
    case 2:
        days = 28; // Simplified
        break;
}
```

#### Ternary Operator

A concise way to write simple if-else statements:

```javascript
// Syntax: condition ? valueIfTrue : valueIfFalse

let age = 20;
let status = age >= 18 ? "Adult" : "Minor";
console.log(status);  // "Adult"

// Equivalent to:
let status2;
if (age >= 18) {
    status2 = "Adult";
} else {
    status2 = "Minor";
}

// Nested ternary (use sparingly)
let score = 85;
let grade = score >= 90 ? "A" 
          : score >= 80 ? "B" 
          : score >= 70 ? "C" 
          : score >= 60 ? "D" 
          : "F";

// In template literals
console.log(`You are ${age >= 18 ? "an adult" : "a minor"}`);

// With function calls
function greet(isMorning) {
    return isMorning ? "Good morning!" : "Hello!";
}
```

### Loops

#### For Loop

```javascript
// Basic for loop
for (let i = 0; i < 5; i++) {
    console.log(i);  // 0, 1, 2, 3, 4
}

// Counting backwards
for (let i = 5; i > 0; i--) {
    console.log(i);  // 5, 4, 3, 2, 1
}

// Custom increment
for (let i = 0; i <= 10; i += 2) {
    console.log(i);  // 0, 2, 4, 6, 8, 10
}

// Looping through array
let fruits = ["apple", "banana", "cherry"];
for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}

// Nested loops
for (let i = 1; i <= 3; i++) {
    for (let j = 1; j <= 3; j++) {
        console.log(`${i} x ${j} = ${i * j}`);
    }
}

// Break and continue
for (let i = 0; i < 10; i++) {
    if (i === 5) break;        // Exit loop entirely
    if (i === 3) continue;     // Skip to next iteration
    console.log(i);            // 0, 1, 2, 4
}
```

#### While Loop

```javascript
// Basic while loop
let count = 0;
while (count < 5) {
    console.log(count);
    count++;
}

// Waiting for condition
let input = "";
while (input !== "quit") {
    // In real code, this would get user input
    input = "quit";  // Simulated
}

// Infinite loop (be careful!)
// while (true) {
//     // This runs forever unless you break
//     if (someCondition) break;
// }

// Processing until empty
let tasks = ["task1", "task2", "task3"];
while (tasks.length > 0) {
    let task = tasks.pop();
    console.log(`Processing: ${task}`);
}
```

#### Do-While Loop

Executes at least once, then checks condition:

```javascript
// Always runs at least once
let num = 10;
do {
    console.log(num);  // Prints 10
    num++;
} while (num < 5);     // Condition is false, but loop ran once

// Useful for menus
let choice;
do {
    // Display menu and get choice
    choice = 3;  // Simulated user choosing "exit"
    
    switch (choice) {
        case 1: console.log("Option 1"); break;
        case 2: console.log("Option 2"); break;
        case 3: console.log("Exiting..."); break;
    }
} while (choice !== 3);
```

#### For...of and For...in

```javascript
// for...of - iterate over VALUES (arrays, strings, iterables)
let colors = ["red", "green", "blue"];
for (let color of colors) {
    console.log(color);  // "red", "green", "blue"
}

// With strings
let word = "Hello";
for (let char of word) {
    console.log(char);  // "H", "e", "l", "l", "o"
}

// for...in - iterate over KEYS/INDICES (objects)
let person = { name: "Alice", age: 25, city: "NYC" };
for (let key in person) {
    console.log(`${key}: ${person[key]}`);
}
// "name: Alice", "age: 25", "city: NYC"

// for...in with arrays (gets indices, not recommended)
for (let index in colors) {
    console.log(index);  // "0", "1", "2" (as strings!)
}

// Better: use for...of or forEach for arrays
colors.forEach((color, index) => {
    console.log(`${index}: ${color}`);
});
```

### Functions

#### Function Declaration

```javascript
// Basic function
function greet() {
    console.log("Hello!");
}
greet();  // "Hello!"

// With parameters
function greetPerson(name) {
    console.log(`Hello, ${name}!`);
}
greetPerson("Alice");  // "Hello, Alice!"

// Multiple parameters
function add(a, b) {
    return a + b;
}
let sum = add(5, 3);  // 8

// Hoisting - declarations are moved to top
sayHi();  // Works! (hoisted)
function sayHi() {
    console.log("Hi!");
}
```

#### Function Expression

```javascript
// Assign function to variable
const greet = function() {
    console.log("Hello!");
};
greet();

// Named function expression
const factorial = function fact(n) {
    if (n <= 1) return 1;
    return n * fact(n - 1);  // Can call itself by name
};

// NOT hoisted - must define before use
// sayBye();  // ERROR!
const sayBye = function() {
    console.log("Bye!");
};
sayBye();  // Works now
```

#### Arrow Functions

Modern, concise function syntax:

```javascript
// Basic arrow function
const greet = () => {
    console.log("Hello!");
};

// With one parameter (no parentheses needed)
const double = n => n * 2;
console.log(double(5));  // 10

// With multiple parameters
const add = (a, b) => a + b;
console.log(add(2, 3));  // 5

// Multi-line with explicit return
const calculate = (a, b) => {
    const sum = a + b;
    const product = a * b;
    return { sum, product };
};

// Returning object literal (needs parentheses)
const createUser = (name, age) => ({ name, age });
console.log(createUser("Alice", 25));  // { name: "Alice", age: 25 }

// Arrow functions and 'this' (lexical this)
const obj = {
    name: "Alice",
    // Regular function - 'this' is the object
    regularMethod: function() {
        console.log(this.name);  // "Alice"
    },
    // Arrow function - 'this' is from outer scope (not the object!)
    arrowMethod: () => {
        console.log(this.name);  // undefined (or window.name)
    }
};
```

#### Parameters and Arguments

```javascript
// Default parameters
function greet(name = "Guest") {
    console.log(`Hello, ${name}!`);
}
greet();          // "Hello, Guest!"
greet("Alice");   // "Hello, Alice!"

// Rest parameters (...) - collect remaining args
function sum(...numbers) {
    return numbers.reduce((total, n) => total + n, 0);
}
sum(1, 2, 3, 4);  // 10

// Combining regular and rest parameters
function introduce(greeting, ...names) {
    names.forEach(name => console.log(`${greeting}, ${name}!`));
}
introduce("Hello", "Alice", "Bob", "Charlie");

// Destructuring parameters
function printUser({ name, age }) {
    console.log(`${name} is ${age}`);
}
printUser({ name: "Alice", age: 25, city: "NYC" });

// Arguments object (old way, avoid in modern code)
function oldSum() {
    let total = 0;
    for (let i = 0; i < arguments.length; i++) {
        total += arguments[i];
    }
    return total;
}
```

#### Return Values

```javascript
// Single return value
function square(n) {
    return n * n;
}

// Early return
function divide(a, b) {
    if (b === 0) {
        return null;  // Exit early
    }
    return a / b;
}

// No return = undefined
function noReturn() {
    console.log("I do something");
}
let result = noReturn();  // undefined

// Return multiple values (via object or array)
function getMinMax(numbers) {
    return {
        min: Math.min(...numbers),
        max: Math.max(...numbers)
    };
}
const { min, max } = getMinMax([3, 1, 4, 1, 5]);

// Return function (higher-order function)
function multiplier(factor) {
    return (number) => number * factor;
}
const double = multiplier(2);
const triple = multiplier(3);
double(5);  // 10
triple(5);  // 15
```

#### Scope

```javascript
// Global scope
let globalVar = "I'm global";

function testScope() {
    // Function scope
    let functionVar = "I'm in function";
    
    if (true) {
        // Block scope
        let blockVar = "I'm in block";
        const alsoBlock = "Me too";
        var notBlock = "I ignore blocks!";  // var is function-scoped
        
        console.log(blockVar);    // Works
    }
    
    console.log(functionVar);     // Works
    // console.log(blockVar);     // ERROR!
    console.log(notBlock);        // Works (var ignores block)
}

console.log(globalVar);           // Works
// console.log(functionVar);      // ERROR!

// Scope chain - inner can access outer
let outer = "outer";
function outerFn() {
    let middle = "middle";
    function innerFn() {
        let inner = "inner";
        console.log(outer);   // Works
        console.log(middle);  // Works
        console.log(inner);   // Works
    }
    innerFn();
}

// Variable shadowing
let name = "Alice";
function greet() {
    let name = "Bob";  // Shadows outer 'name'
    console.log(name); // "Bob"
}
greet();
console.log(name);     // "Alice"
```

### Arrays

#### Creating Arrays

```javascript
// Array literal (most common)
let fruits = ["apple", "banana", "cherry"];

// Empty array
let empty = [];

// Array constructor
let numbers = new Array(1, 2, 3);
let sized = new Array(5);  // Creates array with 5 empty slots

// Array.from - create from iterable
let chars = Array.from("hello");  // ["h", "e", "l", "l", "o"]
let range = Array.from({ length: 5 }, (_, i) => i);  // [0, 1, 2, 3, 4]

// Array.of - create from arguments
let arr = Array.of(1, 2, 3);  // [1, 2, 3]

// Fill with values
let zeros = new Array(5).fill(0);  // [0, 0, 0, 0, 0]

// Mixed types (allowed but not recommended)
let mixed = [1, "two", true, null, { name: "Alice" }];
```

#### Array Methods

```javascript
let arr = [1, 2, 3, 4, 5];

// Length
arr.length              // 5

// Accessing elements
arr[0]                  // 1 (first)
arr[arr.length - 1]     // 5 (last)
arr.at(-1)              // 5 (last, modern)
arr.at(-2)              // 4 (second to last)

// Adding elements
arr.push(6);            // Add to end → [1,2,3,4,5,6]
arr.unshift(0);         // Add to start → [0,1,2,3,4,5,6]

// Removing elements
arr.pop();              // Remove from end, returns 6
arr.shift();            // Remove from start, returns 0

// Splice - add/remove at any position
arr.splice(2, 1);       // Remove 1 element at index 2
arr.splice(2, 0, 'a');  // Insert 'a' at index 2
arr.splice(1, 2, 'x', 'y'); // Replace 2 elements with 'x', 'y'

// Slice - extract portion (doesn't modify original)
let sliced = arr.slice(1, 3);   // Elements from index 1 to 2
let copy = arr.slice();          // Shallow copy

// Concat - merge arrays
let merged = [1, 2].concat([3, 4], [5, 6]);  // [1,2,3,4,5,6]

// Spread operator (modern way to merge)
let merged2 = [...[1, 2], ...[3, 4]];  // [1,2,3,4]

// Finding elements
arr.indexOf(3);         // Index of first 3 (or -1)
arr.lastIndexOf(3);     // Index of last 3
arr.includes(3);        // true if 3 exists
arr.find(x => x > 3);   // First element > 3
arr.findIndex(x => x > 3);  // Index of first element > 3

// Checking
Array.isArray(arr);     // true

// Reversing and sorting
arr.reverse();          // Reverses in place
arr.sort();             // Sorts in place (alphabetically by default!)
arr.sort((a, b) => a - b);  // Numeric sort ascending
arr.sort((a, b) => b - a);  // Numeric sort descending

// Join
arr.join(", ");         // "1, 2, 3, 4, 5"
arr.join("");           // "12345"

// Flat
let nested = [1, [2, [3, [4]]]];
nested.flat();          // [1, 2, [3, [4]]]
nested.flat(2);         // [1, 2, 3, [4]]
nested.flat(Infinity);  // [1, 2, 3, 4]
```

#### Iterating Arrays

```javascript
let fruits = ["apple", "banana", "cherry"];

// for loop
for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}

// for...of
for (let fruit of fruits) {
    console.log(fruit);
}

// forEach
fruits.forEach((fruit, index) => {
    console.log(`${index}: ${fruit}`);
});

// map - transform each element
let upperFruits = fruits.map(f => f.toUpperCase());
// ["APPLE", "BANANA", "CHERRY"]

// filter - keep elements that pass test
let longFruits = fruits.filter(f => f.length > 5);
// ["banana", "cherry"]

// reduce - accumulate into single value
let numbers = [1, 2, 3, 4, 5];
let sum = numbers.reduce((total, n) => total + n, 0);  // 15

// some - at least one passes test
let hasLong = fruits.some(f => f.length > 5);  // true

// every - all pass test
let allLong = fruits.every(f => f.length > 3);  // true

// Chaining methods
let result = numbers
    .filter(n => n % 2 === 0)   // Keep even: [2, 4]
    .map(n => n * 2)            // Double: [4, 8]
    .reduce((sum, n) => sum + n, 0);  // Sum: 12
```

### Objects

#### Creating Objects

```javascript
// Object literal (most common)
let person = {
    name: "Alice",
    age: 25,
    city: "New York"
};

// Empty object
let empty = {};

// With methods
let user = {
    name: "Bob",
    greet: function() {
        console.log(`Hello, I'm ${this.name}`);
    },
    // Shorthand method syntax
    sayBye() {
        console.log("Goodbye!");
    }
};

// Computed property names
let key = "dynamicKey";
let obj = {
    [key]: "value",
    ["key" + 1]: "value1"
};
// { dynamicKey: "value", key1: "value1" }

// Shorthand property names
let name = "Alice";
let age = 25;
let person2 = { name, age };  // { name: "Alice", age: 25 }

// Object.create
let proto = { greet() { console.log("Hi!"); } };
let obj2 = Object.create(proto);

// Constructor function
function Person(name, age) {
    this.name = name;
    this.age = age;
}
let alice = new Person("Alice", 25);
```

#### Object Properties and Methods

```javascript
let person = {
    name: "Alice",
    age: 25,
    "multi word": "value"
};

// Accessing properties
person.name              // "Alice" (dot notation)
person["name"]           // "Alice" (bracket notation)
person["multi word"]     // "value" (bracket required for special keys)

let key = "age";
person[key]              // 25 (dynamic access)

// Adding/modifying properties
person.city = "NYC";     // Add new property
person.age = 26;         // Modify existing

// Deleting properties
delete person.city;

// Checking properties
"name" in person         // true
person.hasOwnProperty("name")  // true
person.job               // undefined (doesn't exist)

// Object methods
Object.keys(person);     // ["name", "age"]
Object.values(person);   // ["Alice", 25]
Object.entries(person);  // [["name", "Alice"], ["age", 25]]

// Iterate over object
for (let key in person) {
    console.log(`${key}: ${person[key]}`);
}

Object.keys(person).forEach(key => {
    console.log(`${key}: ${person[key]}`);
});

// Merge objects
let defaults = { theme: "light", lang: "en" };
let userPrefs = { theme: "dark" };
let settings = { ...defaults, ...userPrefs };
// { theme: "dark", lang: "en" }

let settings2 = Object.assign({}, defaults, userPrefs);

// Freeze (make immutable)
Object.freeze(person);
person.age = 30;         // Silently fails (or error in strict mode)

// Seal (can modify, can't add/delete)
Object.seal(person);
```

#### Object Destructuring

```javascript
let person = {
    name: "Alice",
    age: 25,
    city: "NYC",
    job: {
        title: "Developer",
        company: "Tech Corp"
    }
};

// Basic destructuring
let { name, age } = person;
console.log(name);  // "Alice"
console.log(age);   // 25

// Renaming variables
let { name: personName, age: personAge } = person;
console.log(personName);  // "Alice"

// Default values
let { name, country = "USA" } = person;
console.log(country);  // "USA"

// Nested destructuring
let { job: { title, company } } = person;
console.log(title);  // "Developer"

// Rest pattern
let { name, ...rest } = person;
console.log(rest);  // { age: 25, city: "NYC", job: {...} }

// In function parameters
function greet({ name, age }) {
    console.log(`${name} is ${age}`);
}
greet(person);

// With defaults in parameters
function createUser({ name = "Guest", age = 0 } = {}) {
    return { name, age };
}
createUser();                    // { name: "Guest", age: 0 }
createUser({ name: "Alice" });   // { name: "Alice", age: 0 }
```

### Strings

#### String Methods

```javascript
let str = "Hello, World!";

// Length
str.length              // 13

// Accessing characters
str[0]                  // "H"
str.charAt(0)           // "H"
str.at(-1)              // "!" (last char)

// Case conversion
str.toUpperCase()       // "HELLO, WORLD!"
str.toLowerCase()       // "hello, world!"

// Searching
str.indexOf("o")        // 4 (first occurrence)
str.lastIndexOf("o")    // 8 (last occurrence)
str.indexOf("x")        // -1 (not found)
str.includes("World")   // true
str.startsWith("Hello") // true
str.endsWith("!")       // true

// Extracting
str.slice(0, 5)         // "Hello"
str.slice(-6)           // "World!"
str.substring(0, 5)     // "Hello"
str.substr(0, 5)        // "Hello" (deprecated)

// Replacing
str.replace("World", "JavaScript")  // "Hello, JavaScript!"
str.replace(/o/g, "0")              // "Hell0, W0rld!" (all occurrences)
str.replaceAll("l", "L")            // "HeLLo, WorLd!"

// Splitting
str.split(", ")         // ["Hello", "World!"]
str.split("")           // ["H", "e", "l", "l", "o", ...]
"a,b,c".split(",")      // ["a", "b", "c"]

// Trimming whitespace
"  hello  ".trim()      // "hello"
"  hello  ".trimStart() // "hello  "
"  hello  ".trimEnd()   // "  hello"

// Padding
"5".padStart(3, "0")    // "005"
"5".padEnd(3, "0")      // "500"

// Repeating
"ha".repeat(3)          // "hahaha"

// Joining array into string
["Hello", "World"].join(" ")  // "Hello World"
```

#### Template Literals

```javascript
// Basic interpolation
let name = "Alice";
let age = 25;
let greeting = `Hello, ${name}! You are ${age} years old.`;

// Expressions inside ${}
let a = 5, b = 10;
console.log(`Sum: ${a + b}`);           // "Sum: 15"
console.log(`Double: ${a * 2}`);        // "Double: 10"
console.log(`Is adult: ${age >= 18}`);  // "Is adult: true"

// Function calls
console.log(`Upper: ${name.toUpperCase()}`);  // "Upper: ALICE"

// Multi-line strings
let html = `
    <div class="card">
        <h2>${name}</h2>
        <p>Age: ${age}</p>
    </div>
`;

// Nested templates
let items = ["apple", "banana", "cherry"];
let list = `
    <ul>
        ${items.map(item => `<li>${item}</li>`).join("")}
    </ul>
`;

// Tagged templates (advanced)
function highlight(strings, ...values) {
    return strings.reduce((result, str, i) => {
        return result + str + (values[i] ? `<mark>${values[i]}</mark>` : "");
    }, "");
}

let highlighted = highlight`Hello, ${name}! You are ${age}.`;
// "Hello, <mark>Alice</mark>! You are <mark>25</mark>."

// Raw strings
String.raw`Hello\nWorld`  // "Hello\\nWorld" (backslash not interpreted)
```

---

## Part 2: Advanced Topics

### DOM Manipulation

The DOM (Document Object Model) is a programming interface for HTML. JavaScript can access and modify the DOM to make pages dynamic.

#### Selecting Elements

```javascript
// By ID (returns single element)
const header = document.getElementById("header");

// By class (returns HTMLCollection - live)
const buttons = document.getElementsByClassName("btn");

// By tag (returns HTMLCollection - live)
const paragraphs = document.getElementsByTagName("p");

// Query selector (returns first match)
const firstBtn = document.querySelector(".btn");
const nav = document.querySelector("#nav");
const firstInput = document.querySelector("input[type='text']");

// Query selector all (returns NodeList - static)
const allBtns = document.querySelectorAll(".btn");
const allLinks = document.querySelectorAll("a[href^='http']");

// Special selectors
document.body                    // <body> element
document.head                    // <head> element
document.documentElement         // <html> element
document.forms                   // All forms
document.images                  // All images
document.links                   // All links

// Converting to array for array methods
const btnArray = Array.from(allBtns);
const btnArray2 = [...allBtns];
```

#### Modifying Elements

```javascript
const element = document.querySelector(".card");

// Text content
element.textContent = "New text";           // Sets text (no HTML)
element.innerText = "New text";             // Similar, respects CSS
console.log(element.textContent);           // Gets text

// HTML content
element.innerHTML = "<strong>Bold</strong>"; // Sets HTML (be careful with user input!)
console.log(element.innerHTML);              // Gets HTML

// Attributes
element.setAttribute("data-id", "123");
element.getAttribute("data-id");            // "123"
element.removeAttribute("data-id");
element.hasAttribute("data-id");            // false

// Direct attribute access
element.id = "myCard";
element.className = "card active";
element.href = "https://example.com";       // For links

// Dataset (data-* attributes)
element.dataset.userId = "42";              // Sets data-user-id="42"
console.log(element.dataset.userId);        // "42"

// Classes
element.classList.add("active");
element.classList.remove("active");
element.classList.toggle("active");         // Add if missing, remove if present
element.classList.contains("active");       // true/false
element.classList.replace("old", "new");

// Styles
element.style.color = "red";
element.style.backgroundColor = "blue";     // camelCase!
element.style.fontSize = "16px";
element.style.cssText = "color: red; font-size: 16px;";

// Get computed styles
const styles = getComputedStyle(element);
console.log(styles.color);
```

#### Creating and Removing Elements

```javascript
// Create elements
const div = document.createElement("div");
const text = document.createTextNode("Hello");
const fragment = document.createDocumentFragment();

// Build element
div.className = "card";
div.id = "card-1";
div.textContent = "Card content";
div.innerHTML = `
    <h2>Title</h2>
    <p>Description</p>
`;

// Add to DOM
document.body.appendChild(div);              // Add as last child
parent.insertBefore(div, referenceNode);     // Insert before reference
parent.append(div, div2, "text");           // Append multiple (modern)
parent.prepend(div);                         // Add as first child

// Insert at specific position
element.insertAdjacentHTML("beforebegin", "<p>Before</p>");
element.insertAdjacentHTML("afterbegin", "<p>First child</p>");
element.insertAdjacentHTML("beforeend", "<p>Last child</p>");
element.insertAdjacentHTML("afterend", "<p>After</p>");

element.insertAdjacentElement("beforeend", newElement);
element.insertAdjacentText("beforeend", "Text");

// Clone elements
const clone = element.cloneNode(false);      // Shallow (no children)
const deepClone = element.cloneNode(true);   // Deep (with children)

// Remove elements
element.remove();                            // Remove self
parent.removeChild(child);                   // Remove child
element.replaceWith(newElement);             // Replace self
parent.replaceChild(newChild, oldChild);     // Replace child

// Clear all children
element.innerHTML = "";
while (element.firstChild) {
    element.removeChild(element.firstChild);
}
element.replaceChildren();                   // Modern way
```

#### Traversing the DOM

```javascript
const element = document.querySelector(".item");

// Parent
element.parentNode                 // Parent node (any type)
element.parentElement              // Parent element only

// Children
element.childNodes                 // All child nodes (includes text)
element.children                   // Child elements only
element.firstChild                 // First node
element.firstElementChild          // First element
element.lastChild                  // Last node
element.lastElementChild           // Last element
element.childElementCount          // Number of child elements

// Siblings
element.nextSibling                // Next node
element.nextElementSibling         // Next element
element.previousSibling            // Previous node
element.previousElementSibling     // Previous element

// Closest ancestor
element.closest(".container");     // Find nearest matching ancestor

// Check relationships
parent.contains(child);            // true if child is descendant
node.isEqualNode(otherNode);       // Compare nodes
```

### Events

#### Event Listeners

```javascript
const button = document.querySelector("button");

// Add event listener
button.addEventListener("click", function(event) {
    console.log("Clicked!");
});

// With arrow function
button.addEventListener("click", (e) => {
    console.log("Clicked!", e);
});

// Named function (can be removed)
function handleClick(e) {
    console.log("Clicked!");
}
button.addEventListener("click", handleClick);
button.removeEventListener("click", handleClick);

// Options
button.addEventListener("click", handleClick, {
    once: true,          // Remove after first trigger
    passive: true,       // Never calls preventDefault (performance)
    capture: true        // Use capture phase
});

// Common events
// Mouse: click, dblclick, mousedown, mouseup, mousemove, mouseenter, mouseleave
// Keyboard: keydown, keyup, keypress (deprecated)
// Form: submit, change, input, focus, blur
// Window: load, DOMContentLoaded, resize, scroll
// Touch: touchstart, touchmove, touchend

// Multiple events
["click", "touchstart"].forEach(event => {
    button.addEventListener(event, handleClick);
});
```

#### Event Object

```javascript
button.addEventListener("click", function(event) {
    // Common properties
    event.type                    // "click"
    event.target                  // Element that triggered event
    event.currentTarget           // Element with the listener
    event.timeStamp               // When event occurred
    
    // Mouse events
    event.clientX, event.clientY  // Position relative to viewport
    event.pageX, event.pageY      // Position relative to document
    event.offsetX, event.offsetY  // Position relative to element
    event.button                  // Which mouse button (0=left, 1=middle, 2=right)
    event.buttons                 // Which buttons are pressed
    event.altKey, event.ctrlKey, event.shiftKey, event.metaKey  // Modifier keys
    
    // Keyboard events
    event.key                     // "a", "Enter", "ArrowUp", etc.
    event.code                    // "KeyA", "Enter", "ArrowUp", etc.
    event.repeat                  // true if key is held down
    
    // Touch events
    event.touches                 // All current touches
    event.targetTouches           // Touches on target element
    event.changedTouches          // Touches that changed
});

// Example: keyboard input
document.addEventListener("keydown", (e) => {
    if (e.key === "Escape") {
        closeModal();
    }
    if (e.ctrlKey && e.key === "s") {
        e.preventDefault();
        saveDocument();
    }
});
```

#### Event Bubbling and Capturing

```javascript
// Events propagate in two phases:
// 1. Capturing: window → document → html → body → ... → target
// 2. Bubbling: target → ... → body → html → document → window

document.querySelector(".outer").addEventListener("click", () => {
    console.log("Outer clicked");
}, false);  // false = bubbling phase (default)

document.querySelector(".inner").addEventListener("click", () => {
    console.log("Inner clicked");
}, true);   // true = capturing phase

// Clicking inner logs: "Inner clicked" then "Outer clicked"

// Stop propagation
element.addEventListener("click", (e) => {
    e.stopPropagation();         // Stop bubbling/capturing
    e.stopImmediatePropagation(); // Stop + prevent other handlers on same element
});
```

#### Event Delegation

Handle events on parent instead of many children:

```javascript
// Instead of adding listener to each item...
// document.querySelectorAll(".item").forEach(item => {
//     item.addEventListener("click", handleClick);
// });

// ...add one listener to parent
document.querySelector(".list").addEventListener("click", (e) => {
    // Check if clicked element matches
    if (e.target.matches(".item")) {
        console.log("Item clicked:", e.target.textContent);
    }
    
    // Or find closest matching ancestor
    const item = e.target.closest(".item");
    if (item) {
        console.log("Item clicked:", item.textContent);
    }
});

// Benefits:
// - Works for dynamically added elements
// - Uses less memory (one listener vs many)
// - Less setup code
```

#### Preventing Default Behavior

```javascript
// Prevent form submission
form.addEventListener("submit", (e) => {
    e.preventDefault();
    // Handle form with JavaScript instead
});

// Prevent link navigation
link.addEventListener("click", (e) => {
    e.preventDefault();
    // Do something else
});

// Prevent context menu
element.addEventListener("contextmenu", (e) => {
    e.preventDefault();
    // Show custom context menu
});

// Check if preventable
if (e.cancelable) {
    e.preventDefault();
}

// Check if default was prevented
console.log(e.defaultPrevented);  // true/false
```

### Asynchronous JavaScript

#### Callbacks

```javascript
// Callback = function passed to another function
function fetchData(callback) {
    setTimeout(() => {
        const data = { name: "Alice", age: 25 };
        callback(data);
    }, 1000);
}

fetchData((data) => {
    console.log(data);  // { name: "Alice", age: 25 }
});

// Error-first callbacks (Node.js convention)
function readFile(path, callback) {
    setTimeout(() => {
        if (path === "invalid") {
            callback(new Error("File not found"), null);
        } else {
            callback(null, "File contents");
        }
    }, 1000);
}

readFile("data.txt", (error, data) => {
    if (error) {
        console.error(error.message);
        return;
    }
    console.log(data);
});

// Callback hell (avoid this!)
getUser(userId, (user) => {
    getOrders(user.id, (orders) => {
        getOrderDetails(orders[0].id, (details) => {
            // Deeply nested, hard to read
        });
    });
});
```

#### Promises

```javascript
// Creating a promise
const promise = new Promise((resolve, reject) => {
    setTimeout(() => {
        const success = true;
        if (success) {
            resolve({ data: "Success!" });
        } else {
            reject(new Error("Failed!"));
        }
    }, 1000);
});

// Using a promise
promise
    .then((result) => {
        console.log(result);  // { data: "Success!" }
        return result.data;
    })
    .then((data) => {
        console.log(data);    // "Success!"
    })
    .catch((error) => {
        console.error(error.message);
    })
    .finally(() => {
        console.log("Done!");  // Always runs
    });

// Promise states: pending → fulfilled OR rejected

// Static methods
Promise.resolve(42);              // Create resolved promise
Promise.reject(new Error("No")); // Create rejected promise

// Multiple promises
const p1 = fetch("/api/user");
const p2 = fetch("/api/posts");
const p3 = fetch("/api/comments");

Promise.all([p1, p2, p3])         // Wait for ALL (fails if any fails)
    .then(([user, posts, comments]) => {
        console.log("All loaded!");
    });

Promise.allSettled([p1, p2, p3])  // Wait for ALL (never fails)
    .then((results) => {
        results.forEach((result) => {
            if (result.status === "fulfilled") {
                console.log(result.value);
            } else {
                console.log(result.reason);
            }
        });
    });

Promise.race([p1, p2, p3])        // First to settle (resolve or reject)
    .then((firstResult) => {
        console.log("First finished!");
    });

Promise.any([p1, p2, p3])         // First to resolve (ignores rejections)
    .then((firstSuccess) => {
        console.log("First success!");
    });
```

#### Async/Await

```javascript
// Async function always returns a promise
async function fetchUser() {
    return { name: "Alice" };  // Wrapped in Promise.resolve()
}

fetchUser().then(user => console.log(user));

// Await pauses execution until promise resolves
async function getUser(id) {
    const response = await fetch(`/api/users/${id}`);
    const user = await response.json();
    return user;
}

// Error handling with try/catch
async function fetchData() {
    try {
        const response = await fetch("/api/data");
        if (!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`);
        }
        const data = await response.json();
        return data;
    } catch (error) {
        console.error("Fetch failed:", error.message);
        throw error;  // Re-throw if needed
    } finally {
        console.log("Cleanup");
    }
}

// Parallel execution
async function loadDashboard() {
    // Sequential (slow)
    const user = await getUser();
    const posts = await getPosts();
    
    // Parallel (fast)
    const [user2, posts2] = await Promise.all([
        getUser(),
        getPosts()
    ]);
}

// Top-level await (in modules)
const data = await fetch("/api/config").then(r => r.json());

// IIFE for top-level await (older environments)
(async () => {
    const data = await fetchData();
    console.log(data);
})();
```

#### Error Handling

```javascript
// Catching async errors
async function example() {
    try {
        const data = await riskyOperation();
    } catch (error) {
        if (error instanceof TypeError) {
            console.error("Type error:", error.message);
        } else if (error instanceof NetworkError) {
            console.error("Network error:", error.message);
        } else {
            throw error;  // Re-throw unknown errors
        }
    }
}

// Handling multiple operations
async function processItems(items) {
    const results = [];
    const errors = [];
    
    for (const item of items) {
        try {
            const result = await processItem(item);
            results.push(result);
        } catch (error) {
            errors.push({ item, error });
        }
    }
    
    return { results, errors };
}

// Global unhandled rejection handler
window.addEventListener("unhandledrejection", (event) => {
    console.error("Unhandled promise rejection:", event.reason);
    event.preventDefault();  // Prevent default logging
});
```

### Fetch API and AJAX

#### Making HTTP Requests

```javascript
// Basic GET request
fetch("/api/users")
    .then(response => response.json())
    .then(data => console.log(data));

// With async/await
async function getUsers() {
    const response = await fetch("/api/users");
    const users = await response.json();
    return users;
}

// POST request
fetch("/api/users", {
    method: "POST",
    headers: {
        "Content-Type": "application/json"
    },
    body: JSON.stringify({
        name: "Alice",
        email: "alice@example.com"
    })
});

// Other methods
fetch("/api/users/1", { method: "PUT", body: JSON.stringify(data) });
fetch("/api/users/1", { method: "PATCH", body: JSON.stringify(data) });
fetch("/api/users/1", { method: "DELETE" });

// Full options
fetch(url, {
    method: "POST",
    headers: {
        "Content-Type": "application/json",
        "Authorization": "Bearer token123"
    },
    body: JSON.stringify(data),
    mode: "cors",                  // cors, no-cors, same-origin
    credentials: "include",        // include, same-origin, omit
    cache: "no-cache",            // default, no-cache, reload, force-cache
    redirect: "follow",           // follow, error, manual
    signal: abortController.signal // For cancellation
});

// Cancellation with AbortController
const controller = new AbortController();

fetch("/api/data", { signal: controller.signal })
    .catch(err => {
        if (err.name === "AbortError") {
            console.log("Request cancelled");
        }
    });

// Cancel after timeout
setTimeout(() => controller.abort(), 5000);
```

#### Working with JSON

```javascript
// Parse JSON string to object
const jsonString = '{"name": "Alice", "age": 25}';
const obj = JSON.parse(jsonString);
console.log(obj.name);  // "Alice"

// Convert object to JSON string
const user = { name: "Alice", age: 25 };
const json = JSON.stringify(user);
console.log(json);  // '{"name":"Alice","age":25}'

// Pretty print
JSON.stringify(user, null, 2);  // 2-space indentation

// Custom serialization
const data = {
    name: "Alice",
    password: "secret",
    date: new Date()
};

JSON.stringify(data, (key, value) => {
    if (key === "password") return undefined;  // Exclude
    if (value instanceof Date) return value.toISOString();
    return value;
});

// Reviver function for parsing
JSON.parse(json, (key, value) => {
    if (key === "date") return new Date(value);
    return value;
});
```

#### Handling Responses

```javascript
async function fetchData(url) {
    const response = await fetch(url);
    
    // Check response status
    console.log(response.status);       // 200, 404, 500, etc.
    console.log(response.statusText);   // "OK", "Not Found", etc.
    console.log(response.ok);           // true if status 200-299
    
    // Response headers
    console.log(response.headers.get("Content-Type"));
    
    // Handle different statuses
    if (!response.ok) {
        if (response.status === 404) {
            throw new Error("Resource not found");
        } else if (response.status === 401) {
            throw new Error("Unauthorized");
        } else {
            throw new Error(`HTTP error: ${response.status}`);
        }
    }
    
    // Parse response body (can only be read once!)
    const data = await response.json();     // JSON
    // const text = await response.text();  // Plain text
    // const blob = await response.blob();  // Binary data
    // const form = await response.formData(); // Form data
    // const buffer = await response.arrayBuffer(); // Raw bytes
    
    return data;
}

// Clone response to read multiple times
async function example() {
    const response = await fetch(url);
    const clone = response.clone();
    
    const text = await response.text();
    const json = await clone.json();
}
```

### ES6+ Features

#### Destructuring

```javascript
// Array destructuring
const [first, second, third] = [1, 2, 3];
const [a, , c] = [1, 2, 3];           // Skip elements
const [head, ...tail] = [1, 2, 3, 4]; // Rest pattern
const [x = 0, y = 0] = [1];           // Defaults

// Swapping variables
let m = 1, n = 2;
[m, n] = [n, m];

// Object destructuring
const { name, age } = { name: "Alice", age: 25 };
const { name: userName } = user;       // Rename
const { role = "user" } = user;        // Default
const { address: { city } } = user;    // Nested

// In function parameters
function greet({ name, age = 0 }) {
    console.log(`${name} is ${age}`);
}

// Mixed
const [{ name }] = [{ name: "Alice" }];
```

#### Spread and Rest Operators

```javascript
// Spread (...) - expand iterables
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];         // [1, 2, 3, 4, 5]
const copy = [...arr1];                // Shallow copy

const obj1 = { a: 1, b: 2 };
const obj2 = { ...obj1, c: 3 };       // { a: 1, b: 2, c: 3 }
const merged = { ...obj1, ...obj2 };

// Function arguments
Math.max(...arr1);                     // Same as Math.max(1, 2, 3)

// Rest (...) - collect remaining
function sum(...numbers) {             // Collect arguments
    return numbers.reduce((a, b) => a + b, 0);
}
sum(1, 2, 3, 4);  // 10

const [first, ...rest] = [1, 2, 3, 4]; // first=1, rest=[2,3,4]
const { a, ...others } = { a: 1, b: 2, c: 3 }; // others={b:2,c:3}
```

#### Default Parameters

```javascript
function greet(name = "Guest", greeting = "Hello") {
    return `${greeting}, ${name}!`;
}

greet();                    // "Hello, Guest!"
greet("Alice");             // "Hello, Alice!"
greet("Alice", "Hi");       // "Hi, Alice!"
greet(undefined, "Hey");    // "Hey, Guest!" (undefined triggers default)

// Expression as default
function createId(prefix = "id", num = Date.now()) {
    return `${prefix}_${num}`;
}

// Using earlier parameters
function rectangle(width, height = width) {
    return width * height;
}
rectangle(5);  // 25 (square)

// Destructuring with defaults
function createUser({ name = "Guest", age = 0 } = {}) {
    return { name, age };
}
createUser();  // { name: "Guest", age: 0 }
```

#### Classes

```javascript
class Person {
    // Constructor
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
    
    // Instance method
    greet() {
        return `Hello, I'm ${this.name}`;
    }
    
    // Getter
    get birthYear() {
        return new Date().getFullYear() - this.age;
    }
    
    // Setter
    set birthYear(year) {
        this.age = new Date().getFullYear() - year;
    }
    
    // Static method
    static createAnonymous() {
        return new Person("Anonymous", 0);
    }
    
    // Static property
    static species = "Homo sapiens";
    
    // Private field (prefix with #)
    #secret = "hidden";
    
    getSecret() {
        return this.#secret;
    }
}

// Usage
const alice = new Person("Alice", 25);
alice.greet();              // "Hello, I'm Alice"
alice.birthYear;            // 2001
Person.createAnonymous();   // Person { name: "Anonymous", age: 0 }
Person.species;             // "Homo sapiens"

// Inheritance
class Employee extends Person {
    constructor(name, age, jobTitle) {
        super(name, age);   // Call parent constructor
        this.jobTitle = jobTitle;
    }
    
    greet() {
        return `${super.greet()}, I work as ${this.jobTitle}`;
    }
}

const bob = new Employee("Bob", 30, "Developer");
bob.greet();  // "Hello, I'm Bob, I work as Developer"
bob instanceof Employee;  // true
bob instanceof Person;    // true
```

#### Modules

```javascript
// math.js - Named exports
export const PI = 3.14159;
export function add(a, b) { return a + b; }
export function subtract(a, b) { return a - b; }

// Or export at end
const multiply = (a, b) => a * b;
const divide = (a, b) => a / b;
export { multiply, divide };

// user.js - Default export
export default class User {
    constructor(name) {
        this.name = name;
    }
}

// Can have one default + multiple named
export default class User {}
export const ROLES = ["admin", "user"];

// main.js - Importing
import User from "./user.js";                    // Default import
import { PI, add } from "./math.js";             // Named imports
import { add as sum } from "./math.js";          // Rename
import * as math from "./math.js";               // Import all
import User, { ROLES } from "./user.js";         // Mixed

// Dynamic import
const module = await import("./module.js");
const { default: Component } = await import("./Component.js");

// HTML
<script type="module" src="main.js"></script>
```

#### Map and Set

```javascript
// Map - key-value pairs (any type as key)
const map = new Map();
map.set("name", "Alice");
map.set(123, "number key");
map.set({ id: 1 }, "object key");

map.get("name");        // "Alice"
map.has("name");        // true
map.delete("name");
map.size;               // 2
map.clear();

// Initialize with entries
const map2 = new Map([
    ["a", 1],
    ["b", 2]
]);

// Iterate
for (let [key, value] of map2) {
    console.log(key, value);
}
map2.forEach((value, key) => console.log(key, value));
map2.keys();            // Iterator of keys
map2.values();          // Iterator of values
map2.entries();         // Iterator of [key, value]

// Convert to/from object
const obj = Object.fromEntries(map2);
const map3 = new Map(Object.entries(obj));

// Set - unique values
const set = new Set();
set.add(1);
set.add(2);
set.add(1);             // Ignored (already exists)

set.has(1);             // true
set.delete(1);
set.size;               // 1
set.clear();

// Initialize with array
const set2 = new Set([1, 2, 3, 3, 4]);  // {1, 2, 3, 4}

// Remove duplicates from array
const unique = [...new Set([1, 2, 2, 3, 3, 3])];  // [1, 2, 3]

// Iterate
for (let value of set2) {
    console.log(value);
}
set2.forEach(value => console.log(value));
```

### Advanced Functions

#### Closures

```javascript
// A closure is a function that remembers its outer scope
function createCounter() {
    let count = 0;  // Private variable
    
    return {
        increment() {
            count++;
            return count;
        },
        decrement() {
            count--;
            return count;
        },
        getCount() {
            return count;
        }
    };
}

const counter = createCounter();
counter.increment();  // 1
counter.increment();  // 2
counter.getCount();   // 2
// count is not accessible directly

// Practical example: function factory
function createMultiplier(factor) {
    return (number) => number * factor;
}

const double = createMultiplier(2);
const triple = createMultiplier(3);

double(5);  // 10
triple(5);  // 15

// Closures in loops (common mistake)
// Wrong - all functions share same i
for (var i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 100);  // 3, 3, 3
}

// Fix with let (block scope)
for (let i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 100);  // 0, 1, 2
}

// Fix with closure
for (var i = 0; i < 3; i++) {
    ((j) => {
        setTimeout(() => console.log(j), 100);
    })(i);  // 0, 1, 2
}
```

#### Higher-Order Functions

```javascript
// A function that takes/returns functions
function withLogging(fn) {
    return function(...args) {
        console.log(`Calling ${fn.name} with:`, args);
        const result = fn(...args);
        console.log(`Result:`, result);
        return result;
    };
}

function add(a, b) {
    return a + b;
}

const loggedAdd = withLogging(add);
loggedAdd(2, 3);
// "Calling add with: [2, 3]"
// "Result: 5"

// Common higher-order functions
[1, 2, 3].map(x => x * 2);          // Transform each
[1, 2, 3].filter(x => x > 1);       // Keep matching
[1, 2, 3].reduce((acc, x) => acc + x, 0);  // Accumulate
[1, 2, 3].forEach(x => console.log(x));    // Side effect
[1, 2, 3].find(x => x > 1);         // Find first
[1, 2, 3].some(x => x > 2);         // Any match?
[1, 2, 3].every(x => x > 0);        // All match?

// Compose functions
const compose = (...fns) => (x) => 
    fns.reduceRight((acc, fn) => fn(acc), x);

const pipe = (...fns) => (x) => 
    fns.reduce((acc, fn) => fn(acc), x);

const addOne = x => x + 1;
const double = x => x * 2;
const square = x => x * x;

const composed = compose(square, double, addOne);
composed(2);  // square(double(addOne(2))) = 36

const piped = pipe(addOne, double, square);
piped(2);     // square(double(addOne(2))) = 36
```

#### IIFE (Immediately Invoked Function Expression)

```javascript
// Runs immediately after definition
(function() {
    console.log("I run immediately!");
})();

// With arrow function
(() => {
    console.log("Arrow IIFE!");
})();

// With parameters
((name) => {
    console.log(`Hello, ${name}!`);
})("Alice");

// Returns value
const result = (() => {
    const x = 10;
    const y = 20;
    return x + y;
})();  // 30

// Private scope pattern
const counter = (() => {
    let count = 0;  // Private
    
    return {
        increment: () => ++count,
        decrement: () => --count,
        getCount: () => count
    };
})();

// Async IIFE
(async () => {
    const data = await fetchData();
    console.log(data);
})();
```

### Object-Oriented Programming

#### Constructor Functions

```javascript
// Before ES6 classes
function Person(name, age) {
    this.name = name;
    this.age = age;
}

Person.prototype.greet = function() {
    return `Hello, I'm ${this.name}`;
};

const alice = new Person("Alice", 25);
alice.greet();  // "Hello, I'm Alice"

// Static method
Person.create = function(name) {
    return new Person(name, 0);
};
```

#### Prototypes

```javascript
// Every object has a prototype
const person = { name: "Alice" };
console.log(Object.getPrototypeOf(person));  // Object.prototype

// Prototype chain
person.toString();  // Found on Object.prototype

// Add to prototype
Person.prototype.sayBye = function() {
    return `Goodbye from ${this.name}`;
};

// All instances get the method
alice.sayBye();  // "Goodbye from Alice"

// Check prototype
alice instanceof Person;  // true
Person.prototype.isPrototypeOf(alice);  // true
alice.hasOwnProperty("name");  // true
alice.hasOwnProperty("greet");  // false (on prototype)

// Create object with specific prototype
const proto = { greet() { return "Hello!"; } };
const obj = Object.create(proto);
obj.greet();  // "Hello!"
```

#### Inheritance

```javascript
// ES6 class inheritance
class Animal {
    constructor(name) {
        this.name = name;
    }
    
    speak() {
        console.log(`${this.name} makes a sound`);
    }
}

class Dog extends Animal {
    constructor(name, breed) {
        super(name);  // Call parent constructor
        this.breed = breed;
    }
    
    speak() {
        console.log(`${this.name} barks`);
    }
    
    fetch() {
        console.log(`${this.name} fetches the ball`);
    }
}

const dog = new Dog("Rex", "German Shepherd");
dog.speak();  // "Rex barks"
dog.fetch();  // "Rex fetches the ball"

// Prototype-based inheritance (old way)
function Animal(name) {
    this.name = name;
}

Animal.prototype.speak = function() {
    console.log(`${this.name} makes a sound`);
};

function Dog(name, breed) {
    Animal.call(this, name);
    this.breed = breed;
}

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;
```

#### Encapsulation

```javascript
class BankAccount {
    // Private fields (ES2022+)
    #balance = 0;
    #pin;
    
    constructor(initialBalance, pin) {
        this.#balance = initialBalance;
        this.#pin = pin;
    }
    
    // Private method
    #validatePin(pin) {
        return this.#pin === pin;
    }
    
    // Public interface
    deposit(amount) {
        if (amount > 0) {
            this.#balance += amount;
            return true;
        }
        return false;
    }
    
    withdraw(amount, pin) {
        if (!this.#validatePin(pin)) {
            throw new Error("Invalid PIN");
        }
        if (amount > this.#balance) {
            throw new Error("Insufficient funds");
        }
        this.#balance -= amount;
        return amount;
    }
    
    getBalance(pin) {
        if (!this.#validatePin(pin)) {
            throw new Error("Invalid PIN");
        }
        return this.#balance;
    }
}

const account = new BankAccount(1000, "1234");
account.deposit(500);
account.getBalance("1234");    // 1500
// account.#balance;           // SyntaxError: Private field
```

### Advanced Array Methods

#### map(), filter(), reduce()

```javascript
const numbers = [1, 2, 3, 4, 5];

// map - transform each element
const doubled = numbers.map(n => n * 2);
// [2, 4, 6, 8, 10]

const users = [
    { name: "Alice", age: 25 },
    { name: "Bob", age: 30 }
];
const names = users.map(u => u.name);
// ["Alice", "Bob"]

// filter - keep elements that pass test
const evens = numbers.filter(n => n % 2 === 0);
// [2, 4]

const adults = users.filter(u => u.age >= 18);
// [{ name: "Alice", age: 25 }, { name: "Bob", age: 30 }]

// reduce - accumulate into single value
const sum = numbers.reduce((acc, n) => acc + n, 0);
// 15

const product = numbers.reduce((acc, n) => acc * n, 1);
// 120

// Reduce to object
const byId = users.reduce((acc, user) => {
    acc[user.name] = user;
    return acc;
}, {});
// { Alice: {...}, Bob: {...} }

// Flatten array
const nested = [[1, 2], [3, 4], [5]];
const flat = nested.reduce((acc, arr) => [...acc, ...arr], []);
// [1, 2, 3, 4, 5]

// Chaining
const result = numbers
    .filter(n => n % 2 === 0)     // [2, 4]
    .map(n => n * 3)               // [6, 12]
    .reduce((a, b) => a + b, 0);   // 18
```

#### find(), findIndex()

```javascript
const users = [
    { id: 1, name: "Alice", role: "admin" },
    { id: 2, name: "Bob", role: "user" },
    { id: 3, name: "Charlie", role: "user" }
];

// find - returns first matching element
const admin = users.find(u => u.role === "admin");
// { id: 1, name: "Alice", role: "admin" }

const notFound = users.find(u => u.id === 99);
// undefined

// findIndex - returns index of first match
const bobIndex = users.findIndex(u => u.name === "Bob");
// 1

const notFoundIndex = users.findIndex(u => u.id === 99);
// -1

// findLast, findLastIndex (ES2023)
const lastUser = users.findLast(u => u.role === "user");
// { id: 3, name: "Charlie", role: "user" }
```

#### some(), every()

```javascript
const numbers = [1, 2, 3, 4, 5];

// some - at least one passes test
numbers.some(n => n > 4);       // true
numbers.some(n => n > 10);      // false

// every - all pass test
numbers.every(n => n > 0);      // true
numbers.every(n => n > 3);      // false

// Practical examples
const users = [
    { name: "Alice", active: true },
    { name: "Bob", active: false }
];

const hasActiveUser = users.some(u => u.active);  // true
const allActive = users.every(u => u.active);      // false

// Early exit (performance)
// some() stops at first true
// every() stops at first false
```

#### sort()

```javascript
// Default sort (alphabetical, converts to strings!)
[3, 1, 4, 1, 5].sort();        // [1, 1, 3, 4, 5] (lucky)
[10, 2, 30].sort();            // [10, 2, 30] (wrong!)

// Numeric sort
[10, 2, 30].sort((a, b) => a - b);  // [2, 10, 30] ascending
[10, 2, 30].sort((a, b) => b - a);  // [30, 10, 2] descending

// String sort
const words = ["banana", "Apple", "cherry"];
words.sort();                               // Case-sensitive
words.sort((a, b) => a.localeCompare(b));  // Proper string sort

// Object sort
const users = [
    { name: "Charlie", age: 35 },
    { name: "Alice", age: 25 },
    { name: "Bob", age: 30 }
];

// By age
users.sort((a, b) => a.age - b.age);

// By name
users.sort((a, b) => a.name.localeCompare(b.name));

// Multiple criteria
users.sort((a, b) => {
    if (a.age !== b.age) return a.age - b.age;
    return a.name.localeCompare(b.name);
});

// toSorted() - non-mutating (ES2023)
const sorted = numbers.toSorted((a, b) => a - b);
// Original array unchanged
```

### Error Handling

#### Try/Catch/Finally

```javascript
try {
    // Code that might throw
    const data = JSON.parse(invalidJson);
    processData(data);
} catch (error) {
    // Handle error
    console.error("Error:", error.message);
    console.error("Stack:", error.stack);
} finally {
    // Always runs
    cleanup();
}

// Specific error types
try {
    riskyOperation();
} catch (error) {
    if (error instanceof TypeError) {
        console.error("Type error:", error.message);
    } else if (error instanceof RangeError) {
        console.error("Range error:", error.message);
    } else if (error instanceof SyntaxError) {
        console.error("Syntax error:", error.message);
    } else {
        throw error;  // Re-throw unknown errors
    }
}

// Optional catch binding (ES2019)
try {
    return JSON.parse(str);
} catch {
    return null;  // No need for error variable
}
```

#### Throwing Errors

```javascript
// Throw built-in error types
throw new Error("Something went wrong");
throw new TypeError("Expected a string");
throw new RangeError("Value out of range");
throw new ReferenceError("Variable not defined");

// Throw anything (but Error is preferred)
throw "Error message";     // Not recommended
throw 404;                 // Not recommended
throw { code: 404 };       // Not recommended

// Validate input
function divide(a, b) {
    if (typeof a !== "number" || typeof b !== "number") {
        throw new TypeError("Arguments must be numbers");
    }
    if (b === 0) {
        throw new RangeError("Cannot divide by zero");
    }
    return a / b;
}
```

#### Custom Error Types

```javascript
// Extend Error class
class ValidationError extends Error {
    constructor(message, field) {
        super(message);
        this.name = "ValidationError";
        this.field = field;
    }
}

class HttpError extends Error {
    constructor(message, statusCode) {
        super(message);
        this.name = "HttpError";
        this.statusCode = statusCode;
    }
}

// Usage
function validateUser(user) {
    if (!user.email) {
        throw new ValidationError("Email is required", "email");
    }
    if (!user.email.includes("@")) {
        throw new ValidationError("Invalid email format", "email");
    }
}

try {
    validateUser({ name: "Alice" });
} catch (error) {
    if (error instanceof ValidationError) {
        console.error(`${error.field}: ${error.message}`);
    }
}
```

### Local Storage and Session Storage

#### Storing Data

```javascript
// localStorage - persists until cleared
localStorage.setItem("username", "Alice");
localStorage.setItem("theme", "dark");

// Store objects (must stringify)
const user = { name: "Alice", age: 25 };
localStorage.setItem("user", JSON.stringify(user));

// sessionStorage - cleared when tab closes
sessionStorage.setItem("sessionId", "abc123");
sessionStorage.setItem("cart", JSON.stringify(cartItems));
```

#### Retrieving Data

```javascript
// Get string value
const username = localStorage.getItem("username");  // "Alice"

// Get and parse object
const userJson = localStorage.getItem("user");
const user = userJson ? JSON.parse(userJson) : null;

// Check if exists
if (localStorage.getItem("theme")) {
    applyTheme(localStorage.getItem("theme"));
}

// Get all keys
for (let i = 0; i < localStorage.length; i++) {
    const key = localStorage.key(i);
    console.log(key, localStorage.getItem(key));
}

// Using Object.keys
Object.keys(localStorage).forEach(key => {
    console.log(key, localStorage.getItem(key));
});
```

#### Removing Data

```javascript
// Remove single item
localStorage.removeItem("username");

// Clear all items
localStorage.clear();

// Helper function
function removeFromStorage(key) {
    try {
        localStorage.removeItem(key);
        return true;
    } catch (e) {
        return false;
    }
}

// Storage wrapper class
class Storage {
    static get(key, defaultValue = null) {
        const item = localStorage.getItem(key);
        if (!item) return defaultValue;
        try {
            return JSON.parse(item);
        } catch {
            return item;
        }
    }
    
    static set(key, value) {
        const item = typeof value === "string" ? value : JSON.stringify(value);
        localStorage.setItem(key, item);
    }
    
    static remove(key) {
        localStorage.removeItem(key);
    }
    
    static clear() {
        localStorage.clear();
    }
}
```

### Regular Expressions

#### Pattern Matching

```javascript
// Creating regex
const regex1 = /pattern/flags;
const regex2 = new RegExp("pattern", "flags");

// Flags
// i - case insensitive
// g - global (find all matches)
// m - multiline
// s - dotall (. matches newlines)
// u - unicode
// y - sticky

// Testing
const pattern = /hello/i;
pattern.test("Hello World");   // true

// Matching
const str = "Hello World";
str.match(/o/g);               // ["o", "o"]
str.match(/world/i);           // ["World"]

// Replacing
str.replace(/world/i, "JS");   // "Hello JS"
str.replaceAll(/o/g, "0");     // "Hell0 W0rld"

// Searching
str.search(/world/i);          // 6 (index)

// Splitting
"a,b;c".split(/[,;]/);         // ["a", "b", "c"]

// Exec (detailed match info)
const re = /(\w+)@(\w+)/g;
let match;
while ((match = re.exec("alice@example")) !== null) {
    console.log(match[0]);     // Full match
    console.log(match[1]);     // First group
    console.log(match.index);  // Position
}
```

#### Common Regex Patterns

```javascript
// Email
const email = /^[\w.-]+@[\w.-]+\.\w{2,}$/;
email.test("user@example.com");  // true

// Phone (US)
const phone = /^\(?(\d{3})\)?[-.\s]?(\d{3})[-.\s]?(\d{4})$/;
phone.test("(555) 123-4567");   // true

// URL
const url = /^(https?:\/\/)?([\w-]+\.)+[\w-]+(\/[\w-./?%&=]*)?$/;

// Password (min 8 chars, 1 upper, 1 lower, 1 number)
const password = /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d).{8,}$/;

// Date (YYYY-MM-DD)
const date = /^\d{4}-\d{2}-\d{2}$/;

// HTML tags
const htmlTag = /<\/?[\w\s="'-]+\/?>/g;

// Whitespace
const whitespace = /\s+/g;
"hello   world".replace(whitespace, " ");  // "hello world"

// Extract groups
const datePattern = /(\d{4})-(\d{2})-(\d{2})/;
const [, year, month, day] = "2025-12-31".match(datePattern);

// Named groups
const namedPattern = /(?<year>\d{4})-(?<month>\d{2})-(?<day>\d{2})/;
const { groups } = "2025-12-31".match(namedPattern);
console.log(groups.year);  // "2025"
```

---

## Part 3: Best Practices & Tips

### Code Organization

#### File Structure

```
project/
├── index.html
├── css/
│   └── styles.css
├── js/
│   ├── main.js           # Entry point
│   ├── utils/            # Helper functions
│   │   ├── helpers.js
│   │   └── validators.js
│   ├── components/       # UI components
│   │   ├── modal.js
│   │   └── dropdown.js
│   ├── services/         # API calls
│   │   └── api.js
│   └── config/           # Configuration
│       └── constants.js
└── assets/
    └── images/
```

#### Module Organization

```javascript
// constants.js - Group related constants
export const API_BASE_URL = "https://api.example.com";
export const MAX_RETRIES = 3;
export const TIMEOUT_MS = 5000;

export const HTTP_STATUS = {
    OK: 200,
    CREATED: 201,
    BAD_REQUEST: 400,
    UNAUTHORIZED: 401,
    NOT_FOUND: 404
};

// utils/helpers.js - Small, reusable functions
export function formatDate(date) {
    return new Intl.DateTimeFormat("en-US").format(date);
}

export function capitalize(str) {
    return str.charAt(0).toUpperCase() + str.slice(1);
}

export function debounce(fn, delay) {
    let timeoutId;
    return (...args) => {
        clearTimeout(timeoutId);
        timeoutId = setTimeout(() => fn(...args), delay);
    };
}

// services/api.js - API interaction layer
import { API_BASE_URL, TIMEOUT_MS } from "../config/constants.js";

class ApiService {
    async get(endpoint) {
        const response = await fetch(`${API_BASE_URL}${endpoint}`);
        if (!response.ok) throw new Error(`HTTP ${response.status}`);
        return response.json();
    }
    
    async post(endpoint, data) {
        const response = await fetch(`${API_BASE_URL}${endpoint}`, {
            method: "POST",
            headers: { "Content-Type": "application/json" },
            body: JSON.stringify(data)
        });
        if (!response.ok) throw new Error(`HTTP ${response.status}`);
        return response.json();
    }
}

export const api = new ApiService();
```

#### Single Responsibility Principle

```javascript
// BAD - One function doing too much
function handleUserRegistration(formData) {
    // Validate
    if (!formData.email.includes("@")) return;
    if (formData.password.length < 8) return;
    
    // Format
    formData.email = formData.email.toLowerCase();
    formData.name = formData.name.trim();
    
    // Save
    fetch("/api/users", { method: "POST", body: JSON.stringify(formData) });
    
    // Update UI
    document.getElementById("form").style.display = "none";
    document.getElementById("success").style.display = "block";
}

// GOOD - Separate concerns
function validateForm(formData) {
    const errors = [];
    if (!formData.email.includes("@")) errors.push("Invalid email");
    if (formData.password.length < 8) errors.push("Password too short");
    return errors;
}

function formatUserData(formData) {
    return {
        ...formData,
        email: formData.email.toLowerCase().trim(),
        name: formData.name.trim()
    };
}

async function saveUser(userData) {
    const response = await fetch("/api/users", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify(userData)
    });
    return response.json();
}

function showSuccess() {
    document.getElementById("form").style.display = "none";
    document.getElementById("success").style.display = "block";
}

// Main function orchestrates
async function handleUserRegistration(formData) {
    const errors = validateForm(formData);
    if (errors.length > 0) {
        displayErrors(errors);
        return;
    }
    
    const userData = formatUserData(formData);
    await saveUser(userData);
    showSuccess();
}
```

### Naming Conventions

#### Variables and Functions

```javascript
// Use camelCase for variables and functions
const firstName = "Alice";
const isActive = true;
const userList = [];

function calculateTotal(items) { }
function getUserById(id) { }
function handleClick(event) { }

// Use UPPER_SNAKE_CASE for constants
const MAX_SIZE = 100;
const API_KEY = "abc123";
const DEFAULT_TIMEOUT = 5000;

// Use PascalCase for classes and constructors
class UserAccount { }
class ShoppingCart { }
function Person(name) { }  // Constructor function

// Use descriptive names
// BAD
const d = new Date();
const u = getUser();
function calc(a, b) { }

// GOOD
const currentDate = new Date();
const currentUser = getUser();
function calculateDiscount(price, percentage) { }

// Boolean names should be questions
const isVisible = true;
const hasPermission = false;
const canEdit = true;
const shouldUpdate = false;

// Functions should be verbs
function getUsers() { }
function setName(name) { }
function createOrder(items) { }
function validateEmail(email) { }
function handleSubmit(event) { }

// Event handlers
function onClick() { }      // or handleClick
function onSubmit() { }     // or handleSubmit
function onUserLoad() { }   // or handleUserLoad
```

#### Consistency Matters

```javascript
// Pick one style and stick with it
// Either:
getUserData();
setUserData();
deleteUserData();

// Or:
fetchUser();
updateUser();
removeUser();

// Not mixed:
getUserData();
updateUser();      // Inconsistent!
deleteUserData();
```

### Clean Code Principles

#### Keep Functions Small

```javascript
// BAD - Too long, does too much
function processOrder(order) {
    // 50+ lines of validation, calculation, formatting, saving...
}

// GOOD - Small, focused functions
function processOrder(order) {
    validateOrder(order);
    const total = calculateTotal(order.items);
    const formattedOrder = formatOrder(order, total);
    return saveOrder(formattedOrder);
}

// Each helper is small and testable
function validateOrder(order) {
    if (!order.items?.length) throw new Error("No items");
    if (!order.customerId) throw new Error("No customer");
}

function calculateTotal(items) {
    return items.reduce((sum, item) => sum + item.price * item.quantity, 0);
}
```

#### Avoid Deep Nesting

```javascript
// BAD - Deep nesting
function processUser(user) {
    if (user) {
        if (user.isActive) {
            if (user.hasPermission) {
                if (user.role === "admin") {
                    // Finally do something
                }
            }
        }
    }
}

// GOOD - Early returns (guard clauses)
function processUser(user) {
    if (!user) return;
    if (!user.isActive) return;
    if (!user.hasPermission) return;
    if (user.role !== "admin") return;
    
    // Do something
}

// GOOD - Extract conditions
function processUser(user) {
    if (!canProcessUser(user)) return;
    // Do something
}

function canProcessUser(user) {
    return user?.isActive && user?.hasPermission && user?.role === "admin";
}
```

#### Use Meaningful Comments

```javascript
// BAD - Obvious comments
// Set x to 5
let x = 5;

// Loop through array
for (let i = 0; i < arr.length; i++) { }

// GOOD - Explain WHY, not WHAT
// Using 5 retries because the API is flaky during peak hours
const MAX_RETRIES = 5;

// Binary search requires sorted array - sort first if needed
const index = binarySearch(sortedArray, target);

// GOOD - Document complex logic
/**
 * Calculates compound interest using the formula A = P(1 + r/n)^(nt)
 * @param {number} principal - Initial investment
 * @param {number} rate - Annual interest rate (decimal)
 * @param {number} times - Times compounded per year
 * @param {number} years - Investment period
 * @returns {number} Final amount
 */
function calculateCompoundInterest(principal, rate, times, years) {
    return principal * Math.pow(1 + rate / times, times * years);
}

// GOOD - Mark TODOs and FIXMEs
// TODO: Add input validation
// FIXME: This breaks when quantity is 0
// HACK: Temporary workaround for API bug
// NOTE: This assumes prices are in cents
```

#### Don't Repeat Yourself (DRY)

```javascript
// BAD - Repeated code
function validateEmail(email) {
    if (!email) {
        showError("Email is required");
        return false;
    }
    if (!email.includes("@")) {
        showError("Email is invalid");
        return false;
    }
    return true;
}

function validatePassword(password) {
    if (!password) {
        showError("Password is required");
        return false;
    }
    if (password.length < 8) {
        showError("Password is too short");
        return false;
    }
    return true;
}

// GOOD - Reusable validation
const validators = {
    required: (value, field) => value ? null : `${field} is required`,
    email: (value) => value.includes("@") ? null : "Invalid email",
    minLength: (min) => (value) => 
        value.length >= min ? null : `Must be at least ${min} characters`
};

function validate(value, field, rules) {
    for (const rule of rules) {
        const error = rule(value, field);
        if (error) {
            showError(error);
            return false;
        }
    }
    return true;
}

// Usage
validate(email, "Email", [validators.required, validators.email]);
validate(password, "Password", [validators.required, validators.minLength(8)]);
```

### Performance Optimization

#### DOM Manipulation

```javascript
// BAD - Multiple reflows
for (let i = 0; i < 100; i++) {
    document.body.innerHTML += `<div>${i}</div>`;
}

// GOOD - Build string first
let html = "";
for (let i = 0; i < 100; i++) {
    html += `<div>${i}</div>`;
}
document.body.innerHTML = html;

// BETTER - Use DocumentFragment
const fragment = document.createDocumentFragment();
for (let i = 0; i < 100; i++) {
    const div = document.createElement("div");
    div.textContent = i;
    fragment.appendChild(div);
}
document.body.appendChild(fragment);

// BAD - Reading layout in loop (causes reflow)
const items = document.querySelectorAll(".item");
items.forEach(item => {
    const height = item.offsetHeight;  // Triggers reflow
    item.style.height = height * 2 + "px";  // Triggers reflow
});

// GOOD - Batch reads, then batch writes
const heights = [...items].map(item => item.offsetHeight);
items.forEach((item, i) => {
    item.style.height = heights[i] * 2 + "px";
});
```

#### Debouncing and Throttling

```javascript
// Debounce - Execute after delay (good for search input)
function debounce(fn, delay) {
    let timeoutId;
    return function(...args) {
        clearTimeout(timeoutId);
        timeoutId = setTimeout(() => fn.apply(this, args), delay);
    };
}

const searchInput = document.getElementById("search");
searchInput.addEventListener("input", debounce((e) => {
    fetchSearchResults(e.target.value);
}, 300));

// Throttle - Execute at most once per interval (good for scroll)
function throttle(fn, limit) {
    let inThrottle = false;
    return function(...args) {
        if (!inThrottle) {
            fn.apply(this, args);
            inThrottle = true;
            setTimeout(() => inThrottle = false, limit);
        }
    };
}

window.addEventListener("scroll", throttle(() => {
    updateScrollProgress();
}, 100));
```

#### Memory Management

```javascript
// Remove event listeners when done
class Component {
    constructor(element) {
        this.element = element;
        this.handleClick = this.handleClick.bind(this);
        this.element.addEventListener("click", this.handleClick);
    }
    
    handleClick() {
        console.log("Clicked");
    }
    
    destroy() {
        this.element.removeEventListener("click", this.handleClick);
        this.element = null;
    }
}

// Clear intervals/timeouts
const intervalId = setInterval(update, 1000);
// When done:
clearInterval(intervalId);

// Avoid memory leaks with closures
function createHandler() {
    const largeData = new Array(1000000);  // Large array
    
    return function() {
        // If this closure isn't needed, largeData stays in memory
        console.log(largeData.length);
    };
}

// WeakMap/WeakSet for object references
const cache = new WeakMap();  // Allows garbage collection
cache.set(someObject, expensiveComputation(someObject));
```

#### Lazy Loading

```javascript
// Lazy load images
<img src="placeholder.jpg" data-src="actual-image.jpg" class="lazy">

const lazyImages = document.querySelectorAll(".lazy");
const imageObserver = new IntersectionObserver((entries, observer) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            const img = entry.target;
            img.src = img.dataset.src;
            img.classList.remove("lazy");
            observer.unobserve(img);
        }
    });
});

lazyImages.forEach(img => imageObserver.observe(img));

// Lazy load modules
button.addEventListener("click", async () => {
    const { heavyFunction } = await import("./heavy-module.js");
    heavyFunction();
});
```

### Debugging Techniques

#### Console Methods

```javascript
// Beyond console.log
console.log("Basic message");
console.info("Informational");
console.warn("Warning!");
console.error("Error!");

// Styled output
console.log("%cStyled text", "color: blue; font-size: 20px;");

// Tables for arrays/objects
console.table([
    { name: "Alice", age: 25 },
    { name: "Bob", age: 30 }
]);

// Grouping
console.group("User Details");
console.log("Name: Alice");
console.log("Age: 25");
console.groupEnd();

console.groupCollapsed("Collapsed Group");  // Starts collapsed
console.log("Hidden by default");
console.groupEnd();

// Timing
console.time("fetch");
await fetch("/api/data");
console.timeEnd("fetch");  // "fetch: 123.45ms"

// Counting
function processItem(item) {
    console.count("processItem called");
}

// Assertions
console.assert(x > 0, "x should be positive");

// Stack trace
console.trace("How did we get here?");

// Clear console
console.clear();
```

#### Breakpoints and Debugger

```javascript
// Add debugger statement
function calculateTotal(items) {
    debugger;  // Execution pauses here when DevTools is open
    return items.reduce((sum, item) => sum + item.price, 0);
}

// Conditional breakpoints (in DevTools)
// Right-click line number → "Add conditional breakpoint"
// Enter condition: user.role === "admin"

// Logpoints (log without stopping)
// Right-click → "Add logpoint"
// Enter: "User ID:", user.id

// Break on DOM changes (in DevTools)
// Elements panel → Right-click element → "Break on..."
// - Subtree modifications
// - Attribute modifications
// - Node removal
```

#### Error Tracking

```javascript
// Global error handler
window.onerror = function(message, source, line, column, error) {
    console.error("Global error:", { message, source, line, column, error });
    // Send to error tracking service
    reportError({ message, source, line, column, stack: error?.stack });
    return false;  // Don't suppress default handling
};

// Unhandled promise rejections
window.addEventListener("unhandledrejection", (event) => {
    console.error("Unhandled rejection:", event.reason);
    reportError({ type: "unhandledrejection", reason: event.reason });
});

// Error boundary pattern
async function safeExecute(fn, fallback = null) {
    try {
        return await fn();
    } catch (error) {
        console.error("Execution failed:", error);
        reportError(error);
        return fallback;
    }
}

const data = await safeExecute(() => fetchData(), []);
```

### Security Best Practices

#### Preventing XSS (Cross-Site Scripting)

```javascript
// BAD - Direct HTML insertion
element.innerHTML = userInput;  // DANGEROUS!

// GOOD - Use textContent for text
element.textContent = userInput;

// GOOD - Escape HTML if needed
function escapeHtml(str) {
    const div = document.createElement("div");
    div.textContent = str;
    return div.innerHTML;
}

// GOOD - Use template with proper escaping
function createCard(user) {
    const card = document.createElement("div");
    card.className = "card";
    
    const name = document.createElement("h2");
    name.textContent = user.name;  // Safe
    
    const bio = document.createElement("p");
    bio.textContent = user.bio;    // Safe
    
    card.append(name, bio);
    return card;
}

// If using innerHTML, sanitize first
import DOMPurify from "dompurify";
element.innerHTML = DOMPurify.sanitize(userInput);
```

#### Validating Input

```javascript
// Always validate on the server too!
// Client-side validation is for UX, not security

function validateInput(input) {
    // Remove leading/trailing whitespace
    input = input.trim();
    
    // Check length
    if (input.length > 1000) {
        throw new Error("Input too long");
    }
    
    // Check for expected format
    if (!/^[a-zA-Z0-9\s]+$/.test(input)) {
        throw new Error("Invalid characters");
    }
    
    return input;
}

// Validate URLs before using
function isValidUrl(string) {
    try {
        const url = new URL(string);
        return url.protocol === "http:" || url.protocol === "https:";
    } catch {
        return false;
    }
}

// Don't use eval() or Function() with user input
// BAD
eval(userInput);  // NEVER DO THIS
new Function(userInput)();  // EQUALLY DANGEROUS
```

#### Secure API Calls

```javascript
// Use HTTPS
fetch("https://api.example.com/data");  // Not http://

// Include CSRF token
fetch("/api/update", {
    method: "POST",
    headers: {
        "Content-Type": "application/json",
        "X-CSRF-Token": getCsrfToken()
    },
    body: JSON.stringify(data)
});

// Don't expose sensitive data in URLs
// BAD
fetch(`/api/user?password=${password}`);

// GOOD
fetch("/api/user", {
    method: "POST",
    body: JSON.stringify({ password })
});

// Handle authentication tokens securely
// Store in httpOnly cookies (server-set) when possible
// If using localStorage, be aware of XSS risks
```

### Modern JavaScript Tooling

#### Package Managers

```bash
# npm (Node Package Manager)
npm init -y                    # Create package.json
npm install lodash             # Add dependency
npm install -D jest            # Add dev dependency
npm uninstall lodash           # Remove
npm update                     # Update all
npm run build                  # Run script

# Common scripts in package.json
{
    "scripts": {
        "start": "node server.js",
        "dev": "vite",
        "build": "vite build",
        "test": "jest",
        "lint": "eslint src/"
    }
}
```

#### Linters and Formatters

```javascript
// ESLint configuration (.eslintrc.json)
{
    "env": {
        "browser": true,
        "es2021": true
    },
    "extends": "eslint:recommended",
    "rules": {
        "no-unused-vars": "warn",
        "no-console": "warn",
        "eqeqeq": "error",
        "curly": "error"
    }
}

// Prettier configuration (.prettierrc)
{
    "semi": true,
    "singleQuote": true,
    "tabWidth": 4,
    "trailingComma": "es5"
}

// Run linter
// npx eslint src/
// npx eslint --fix src/
```

#### Build Tools

```javascript
// Vite - Fast development server and bundler
// vite.config.js
import { defineConfig } from "vite";

export default defineConfig({
    root: "src",
    build: {
        outDir: "../dist"
    },
    server: {
        port: 3000
    }
});

// Common build tool features:
// - Bundling (combining files)
// - Minification (reducing file size)
// - Tree shaking (removing unused code)
// - Code splitting (lazy loading)
// - Hot Module Replacement (instant updates)
// - TypeScript/JSX compilation
```

### Testing Basics

#### Unit Testing

```javascript
// Using Jest
// math.js
export function add(a, b) {
    return a + b;
}

export function divide(a, b) {
    if (b === 0) throw new Error("Cannot divide by zero");
    return a / b;
}

// math.test.js
import { add, divide } from "./math.js";

describe("Math functions", () => {
    test("add should sum two numbers", () => {
        expect(add(2, 3)).toBe(5);
        expect(add(-1, 1)).toBe(0);
    });
    
    test("divide should divide two numbers", () => {
        expect(divide(10, 2)).toBe(5);
    });
    
    test("divide should throw on zero", () => {
        expect(() => divide(10, 0)).toThrow("Cannot divide by zero");
    });
});

// Run tests
// npx jest
// npx jest --watch    # Watch mode
// npx jest --coverage # Coverage report
```

#### Testing Async Code

```javascript
// Async function
export async function fetchUser(id) {
    const response = await fetch(`/api/users/${id}`);
    if (!response.ok) throw new Error("User not found");
    return response.json();
}

// Test with async/await
test("fetchUser returns user data", async () => {
    // Mock fetch
    global.fetch = jest.fn(() =>
        Promise.resolve({
            ok: true,
            json: () => Promise.resolve({ id: 1, name: "Alice" })
        })
    );
    
    const user = await fetchUser(1);
    expect(user.name).toBe("Alice");
    expect(fetch).toHaveBeenCalledWith("/api/users/1");
});

test("fetchUser throws on error", async () => {
    global.fetch = jest.fn(() =>
        Promise.resolve({ ok: false })
    );
    
    await expect(fetchUser(999)).rejects.toThrow("User not found");
});
```

### Common Mistakes to Avoid

#### JavaScript Gotchas

```javascript
// 1. Equality comparison
0 == ""           // true (coercion!)
0 === ""          // false (use this)
null == undefined // true
null === undefined // false

// Always use === and !==

// 2. this context
const obj = {
    name: "Alice",
    greet: function() {
        setTimeout(function() {
            console.log(this.name);  // undefined (wrong this)
        }, 100);
    }
};

// Fix with arrow function
greet: function() {
    setTimeout(() => {
        console.log(this.name);  // "Alice" (correct)
    }, 100);
}

// 3. Array/Object reference
const arr1 = [1, 2, 3];
const arr2 = arr1;
arr2.push(4);
console.log(arr1);  // [1, 2, 3, 4] - Same array!

// Fix: Create copy
const arr2 = [...arr1];
const obj2 = { ...obj1 };

// 4. Floating point
0.1 + 0.2 === 0.3  // false!
0.1 + 0.2          // 0.30000000000000004

// Fix: Use tolerance or integers
Math.abs((0.1 + 0.2) - 0.3) < 0.0001  // true

// 5. typeof null
typeof null  // "object" (historical bug)

// Check for null explicitly
value === null

// 6. Array methods that mutate
const arr = [3, 1, 2];
arr.sort();        // Mutates original!
arr.reverse();     // Mutates original!
arr.splice(0, 1);  // Mutates original!

// Non-mutating alternatives (ES2023+)
arr.toSorted();
arr.toReversed();
arr.toSpliced(0, 1);

// 7. parseInt surprises
parseInt("08");      // 8 (OK now, was 0 in old browsers)
parseInt("10px");    // 10 (stops at non-digit)
parseInt("hello");   // NaN

// Always specify radix
parseInt("08", 10);  // 8

// 8. for...in vs for...of
const arr = ["a", "b", "c"];

for (let i in arr) {
    console.log(i);  // "0", "1", "2" (indices as strings!)
}

for (let val of arr) {
    console.log(val);  // "a", "b", "c" (values)
}
```

### Resources for Further Learning

#### Documentation
- **MDN Web Docs**: [developer.mozilla.org](https://developer.mozilla.org) - The definitive JavaScript reference
- **JavaScript.info**: [javascript.info](https://javascript.info) - Modern JavaScript tutorial
- **ECMAScript Specification**: [tc39.es](https://tc39.es) - Official language specification

#### Interactive Learning
- **freeCodeCamp**: Free JavaScript curriculum with projects
- **Codecademy**: Interactive JavaScript courses
- **Exercism**: Practice problems with mentorship
- **LeetCode/HackerRank**: Algorithm challenges

#### Books
- "Eloquent JavaScript" by Marijn Haverbeke (free online)
- "You Don't Know JS" series by Kyle Simpson (free on GitHub)
- "JavaScript: The Good Parts" by Douglas Crockford

#### Tools
- **VS Code**: Popular editor with excellent JS support
- **Chrome DevTools**: Debugging, profiling, network analysis
- **Node.js**: Run JavaScript outside the browser
- **TypeScript**: Add static typing to JavaScript

#### Communities
- Stack Overflow
- Reddit (r/javascript, r/learnjavascript)
- Discord servers (Reactiflux, TypeScript Community)
- Twitter/X (follow JS developers)

---

**Congratulations!** 🎉 You now have a solid foundation in JavaScript. Remember:
- Practice regularly by building projects
- Read other people's code
- Don't be afraid to make mistakes - debugging is learning
- Stay curious and keep exploring new features

Happy coding!
