# 🚀 JavaScript Beginner's Cheatsheet

*Created by [Shizo Techie](https://github.com/shizothetechie)*

## 📌 Table of Contents
- [Variables & Data Types](#variables--data-types)
- [Operators](#operators)
- [Control Flow](#control-flow)
- [Functions](#functions)
- [Arrays](#arrays)
- [Objects](#objects)
- [Loops](#loops)
- [DOM Manipulation](#dom-manipulation)
- [Events](#events)
- [Tips & Tricks](#tips--tricks)

---

## Variables & Data Types

### Declaring Variables
```javascript
// Three ways to declare variables
let name = "John";        // Block-scoped, can be reassigned
const age = 25;           // Block-scoped, cannot be reassigned
var isStudent = true;     // Function-scoped (avoid using)
```

### Data Types
```javascript
// Primitives
let string = "Hello World";              // String
let number = 42;                         // Number
let decimal = 3.14;                      // Number (decimal)
let boolean = true;                      // Boolean
let nothing = null;                      // Null
let notDefined = undefined;              // Undefined
let bigInt = 9007199254740991n;          // BigInt
let uniqueSymbol = Symbol("description"); // Symbol

// Non-primitive
let array = [1, 2, 3];                   // Array
let object = { name: "John", age: 25 };  // Object
let today = new Date();                  // Date object
```

### Type Checking
```javascript
typeof "Hello"  // Returns "string"
typeof 42       // Returns "number"
typeof true     // Returns "boolean"
typeof {}       // Returns "object"
Array.isArray([1, 2, 3])  // Returns true
```

---

## Operators

### Arithmetic Operators
```javascript
let sum = 5 + 3;        // Addition: 8
let difference = 10 - 4; // Subtraction: 6
let product = 4 * 3;     // Multiplication: 12
let quotient = 12 / 4;   // Division: 3
let remainder = 10 % 3;  // Modulus: 1
let power = 2 ** 3;      // Exponentiation: 8
let increment = 5;
increment++;             // Increases by 1: 6
let decrement = 5;
decrement--;             // Decreases by 1: 4
```

### Comparison Operators
```javascript
5 == "5"    // Equality (value): true
5 === 5     // Strict equality (value & type): true
5 === "5"   // Strict equality (value & type): false
5 != "6"    // Inequality: true
5 !== "5"   // Strict inequality: true
5 > 3       // Greater than: true
5 >= 5      // Greater than or equal: true
3 < 5       // Less than: true
3 <= 3      // Less than or equal: true
```

### Logical Operators
```javascript
true && true   // Logical AND: true
true && false  // Logical AND: false
true || false  // Logical OR: true
false || false // Logical OR: false
!true          // Logical NOT: false
```

---

## Control Flow

### If-Else Statements
```javascript
if (age >= 18) {
    console.log("You are an adult");
} else if (age >= 13) {
    console.log("You are a teenager");
} else {
    console.log("You are a child");
}
```

### Switch Statements
```javascript
switch (day) {
    case "Monday":
        console.log("Start of the work week");
        break;
    case "Friday":
        console.log("End of the work week");
        break;
    case "Saturday":
    case "Sunday":
        console.log("Weekend!");
        break;
    default:
        console.log("Midweek");
}
```

### Ternary Operator
```javascript
// condition ? valueIfTrue : valueIfFalse
let status = age >= 18 ? "Adult" : "Minor";
```

---

## Functions

### Function Declaration
```javascript
function greet(name) {
    return `Hello, ${name}!`;
}
```

### Function Expression
```javascript
const greet = function(name) {
    return `Hello, ${name}!`;
}
```

### Arrow Functions
```javascript
// Arrow function with implicit return
const add = (a, b) => a + b;

// Arrow function with block body
const greet = (name) => {
    const message = `Hello, ${name}!`;
    return message;
};

// Arrow function with no parameters
const sayHi = () => "Hi there!";
```

### Default Parameters
```javascript
function greet(name = "Guest") {
    return `Hello, ${name}!`;
}
```

---

## Arrays

### Creating Arrays
```javascript
let fruits = ["Apple", "Banana", "Cherry"];
let emptyArray = [];
let mixedArray = [1, "Hello", true, { name: "John" }];
```

### Array Methods
```javascript
// Adding/removing elements
fruits.push("Orange");     // Add to end: ["Apple", "Banana", "Cherry", "Orange"]
fruits.pop();              // Remove from end: ["Apple", "Banana", "Cherry"]
fruits.unshift("Mango");   // Add to beginning: ["Mango", "Apple", "Banana", "Cherry"]
fruits.shift();            // Remove from beginning: ["Apple", "Banana", "Cherry"]

// Finding elements
fruits.indexOf("Banana");  // Returns 1
fruits.includes("Apple");  // Returns true

// Transforming arrays
fruits.join(", ");         // Returns "Apple, Banana, Cherry"
fruits.slice(1, 2);        // Returns ["Banana"]
fruits.concat(["Orange"]); // Returns ["Apple", "Banana", "Cherry", "Orange"]

// Higher-order methods
let numbers = [1, 2, 3, 4, 5];
numbers.map(num => num * 2);           // Returns [2, 4, 6, 8, 10]
numbers.filter(num => num > 2);        // Returns [3, 4, 5]
numbers.reduce((sum, num) => sum + num, 0); // Returns 15
```

---

## Objects

### Creating Objects
```javascript
let person = {
    firstName: "John",
    lastName: "Doe",
    age: 30,
    isStudent: false,
    greet: function() {
        return `Hello, my name is ${this.firstName}`;
    }
};
```

### Accessing Object Properties
```javascript
person.firstName;           // Dot notation: "John"
person["lastName"];         // Bracket notation: "Doe"

// Adding new properties
person.email = "john@example.com";

// Deleting properties
delete person.isStudent;
```

### Object Methods
```javascript
// Object methods
Object.keys(person);     // Returns ["firstName", "lastName", "age", "email", "greet"]
Object.values(person);   // Returns ["John", "Doe", 30, "john@example.com", function]
Object.entries(person);  // Returns array of [key, value] pairs
```

---

## Loops

### For Loop
```javascript
for (let i = 0; i < 5; i++) {
    console.log(i); // Prints 0, 1, 2, 3, 4
}
```

### For...of Loop (Arrays)
```javascript
for (let fruit of fruits) {
    console.log(fruit); // Prints each fruit
}
```

### For...in Loop (Objects)
```javascript
for (let key in person) {
    console.log(`${key}: ${person[key]}`);
}
```

### While Loop
```javascript
let i = 0;
while (i < 5) {
    console.log(i); // Prints 0, 1, 2, 3, 4
    i++;
}
```

### Do...While Loop
```javascript
let i = 0;
do {
    console.log(i); // Prints 0
    i++;
} while (i < 1);
```

---

## DOM Manipulation

### Selecting Elements
```javascript
// By ID
const element = document.getElementById("myId");

// By class name
const elements = document.getElementsByClassName("myClass");

// By tag name
const divs = document.getElementsByTagName("div");

// Query selectors (returns first match)
const element = document.querySelector("#myId");
const element = document.querySelector(".myClass");

// Query selector all (returns all matches)
const elements = document.querySelectorAll("div.myClass");
```

### Modifying Elements
```javascript
// Changing content
element.textContent = "New text";
element.innerHTML = "<span>New HTML</span>";

// Changing attributes
element.setAttribute("href", "https://example.com");
element.id = "newId";
element.className = "newClass";

// Styling
element.style.color = "red";
element.style.backgroundColor = "blue";

// Adding/removing classes
element.classList.add("active");
element.classList.remove("inactive");
element.classList.toggle("visible");
element.classList.contains("active"); // Returns true/false
```

### Creating/Removing Elements
```javascript
// Create new element
const newDiv = document.createElement("div");
newDiv.textContent = "Hello!";

// Append to document
document.body.appendChild(newDiv);

// Insert before another element
const parent = document.querySelector("#parent");
const sibling = document.querySelector("#sibling");
parent.insertBefore(newDiv, sibling);

// Remove element
element.remove();
```

---

## Events

### Adding Event Listeners
```javascript
const button = document.querySelector("button");

// Basic syntax
button.addEventListener("click", function() {
    console.log("Button clicked!");
});

// With arrow function
button.addEventListener("click", () => {
    console.log("Button clicked!");
});

// With named function
function handleClick() {
    console.log("Button clicked!");
}
button.addEventListener("click", handleClick);
```

### Common Events
```javascript
// Mouse events
element.addEventListener("click", handler);      // Mouse click
element.addEventListener("dblclick", handler);   // Double click
element.addEventListener("mouseover", handler);  // Mouse over
element.addEventListener("mouseout", handler);   // Mouse out

// Keyboard events
element.addEventListener("keydown", handler);    // Key pressed
element.addEventListener("keyup", handler);      // Key released
element.addEventListener("keypress", handler);   // Key pressed (character)

// Form events
form.addEventListener("submit", handler);        // Form submission
input.addEventListener("change", handler);       // Value changed
input.addEventListener("input", handler);        // Value changing

// Document/Window events
window.addEventListener("load", handler);        // Page loaded
window.addEventListener("resize", handler);      // Window resized
document.addEventListener("DOMContentLoaded", handler); // DOM ready
```

### Event Object
```javascript
button.addEventListener("click", function(event) {
    console.log(event.target);        // The element that triggered the event
    console.log(event.type);          // The event type (e.g., "click")
    console.log(event.clientX, event.clientY); // Mouse coordinates
    event.preventDefault();           // Prevent default behavior
    event.stopPropagation();          // Stop event bubbling
});
```

---

## Tips & Tricks

### 💡 Debugging
```javascript
// Quick logging
console.log("Variable:", variable);
console.table(arrayOfObjects);  // Display data as table
console.error("Something went wrong");  // Error message
console.time("Timer"); // Start timer
console.timeEnd("Timer"); // End timer and display time
debugger; // Add breakpoint for browser's debugger
```

### 💡 String Templates
```javascript
// String interpolation with template literals
let name = "John";
let greeting = `Hello, ${name}!`;  // "Hello, John!"

// Multi-line strings
let message = `This is a
multi-line
string`;
```

### 💡 Destructuring
```javascript
// Array destructuring
let [a, b] = [1, 2];  // a = 1, b = 2

// Object destructuring
let {name, age} = {name: "John", age: 30};  // name = "John", age = 30

// Function parameter destructuring
function displayPerson({name, age}) {
    console.log(`${name} is ${age} years old`);
}
```

### 💡 Spread Operator
```javascript
// Combining arrays
let arr1 = [1, 2];
let arr2 = [3, 4];
let combined = [...arr1, ...arr2];  // [1, 2, 3, 4]

// Copying objects and adding properties
let person = { name: "John" };
let personWithAge = { ...person, age: 30 };  // { name: "John", age: 30 }
```

### 💡 Optional Chaining
```javascript
// Avoid errors when accessing nested properties
const user = {}; 
const city = user?.address?.city;  // undefined instead of error
```

### 💡 Nullish Coalescing
```javascript
// Fallback only for null/undefined (not for 0 or "")
const count = data.count ?? 0;  // Use 0 if data.count is null/undefined
```

### 💡 Short-circuit Evaluation
```javascript
// For conditional execution
isLoggedIn && showDashboard();  // Run showDashboard only if isLoggedIn is true

// For default values
const username = inputName || "Guest";  // Use "Guest" if inputName is falsy
```

### 💡 Convert to Number
```javascript
// Quick number conversion
let num1 = +"42";  // 42 (number)
let num2 = parseInt("42px");  // 42 (number)
let num3 = parseFloat("3.14");  // 3.14 (number)
```

### 💡 Array Tricks
```javascript
// Create array with specific length
Array(5).fill(0);  // [0, 0, 0, 0, 0]

// Remove duplicates from array
[...new Set([1, 2, 2, 3, 3])];  // [1, 2, 3]

// Find unique elements between arrays
const onlyInFirst = arr1.filter(item => !arr2.includes(item));
```

### 💡 Object Tricks
```javascript
// Check if property exists
object.hasOwnProperty("propertyName");  // true/false

// Merge objects
Object.assign({}, obj1, obj2);  // New object with properties from obj1 and obj2
```

---

## 📚 Additional Resources

- [MDN JavaScript Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- [JavaScript.info](https://javascript.info/)
- [W3Schools JavaScript Tutorial](https://www.w3schools.com/js/)
- [freeCodeCamp JavaScript Course](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/)

---

*Happy coding!* 😊

*Created by [Shizo Techie](https://github.com/shizothetechie)*
