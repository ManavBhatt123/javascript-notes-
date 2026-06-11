# Variables

## var

- Function scoped
- Can be redeclared
- Can be reassigned
- Hoisted and initialized with `undefined`

```js
var a = 10;
var a = 20;
a = 30;
```

## let

- Block scoped
- Cannot be redeclared in same scope
- Can be reassigned
- Hoisted but not initialized

```js
let age = 20;
age = 21;
```

## const

- Block scoped
- Cannot be redeclared
- Cannot be reassigned

```js
const pi = 3.14;
```

## Objects with const

`const` prevents reassignment of the variable, not modification of object properties.

```js
const person = { name: "Manav" };

person.name = "Bhatt"; // Allowed
```

## Scope

### Block Scope

```js
{
    let x = 10;
}
```

`x` cannot be accessed outside the block.

### Function Scope

```js
function test() {
    var a = 10;
}
```

`a` exists only inside the function.

## Hoisting

Variables declared with `var` are hoisted.

```js
console.log(a);
var a = 10;
```

Output:

```js
undefined
```

because JavaScript treats it like:

```js
var a;
console.log(a);
a = 10;
```
Hoisting is JavaScript's behavior of moving variable and function declarations to the top of their scope before code execution.


# Data Types

## Primitive Data Types

Primitive values are copied by value.

When one variable is assigned to another, a separate copy is created.

```js
let a = 12;
let b = a;

a = 14;

console.log(a); // 14
console.log(b); // 12
```

### Simple Explanation

Think of it as photocopying a document.

If you write on your copy, the original copy does not change.

---

## Reference Data Types

Arrays and objects are stored by reference.

When one variable is assigned to another, both point to the same data in memory.

```js
let c = [1, 2, 3];
let d = c;

c.pop();

console.log(c); // [1, 2]
console.log(d); // [1, 2]
```

### Simple Explanation

Think of two people sharing the same notebook.

If one person erases a page, both see the change.

---

## Dynamic Typing

JavaScript is dynamically typed.

A variable can hold different types of values during execution.

```js
let x = 12;
x = true;
```

The same variable changes from Number to Boolean.

---

## typeof Quirks

### typeof null

```js
typeof null
```

Output:

```js
"object"
```

This is a historical bug in JavaScript that was never fixed.

### typeof NaN

```js
typeof NaN
```

Output:

```js
"number"
```

Although NaN means "Not a Number", JavaScript treats it as a Number type.

---

## Type Coercion

JavaScript automatically converts data types in some operations.

### String + Number

```js
"4" + 1
```

Output:

```js
"41"
```

The number is converted to a string.

### String - Number

```js
"4" - 1
```

Output:

```js
3
```


# Operators and Conditions

## Types of Operators

### Arithmetic Operators

Used for mathematical calculations.

```js
+
-
*
/
%
**
```

Example:

```js
let a = 10;
let b = 5;

console.log(a + b); // 15
```

---

### Comparison Operators

Used to compare two values.

```js
>
<
>=
<=
==
===
!=
!==
```

Example:

```js
10 > 5 // true
```

---

### Logical Operators

Used to combine multiple conditions.

```js
&&  // AND
||  // OR
!   // NOT
```

Example:

```js
if(x > 5 && y < 25){
    console.log("A");
}
```

Both conditions must be true.

---

### Assignment Operators

Used to assign values.

```js
=
+=
-=
*=
/=
```

Example:

```js
let x = 10;
x += 5; // x = 15
```

---

### Unary Operators

Work on a single operand.

```js
++
--
```

Example:

```js
let p = 3;
p++;
```

### Post Increment

```js
let p = 3;
let q = p++;

console.log(p); // 4
console.log(q); // 3
```

First the old value is assigned to `q`,
then `p` is increased.

---

### Ternary Operator

Short form of if-else.

Syntax:

```js
condition ? value_if_true : value_if_false
```

Example:

```js
let age = 18;

let result = age >= 18 ? "Adult" : "Minor";
```

---

## Truthy and Falsy Values

In JavaScript, some values are treated as `true`
and some as `false` when used in conditions.

### Falsy Values

```js
false
0
""
null
undefined
NaN
```

Example:

```js
let a = 0;

if(a){
    console.log("truthy");
}
else{
    console.log("falsy");
}
```

Output:

```js
falsy
```

### Truthy Values

Almost everything else is truthy.

Examples:

```js
1
"hello"
[]
{}
true
```

---

## Nested Ternary Example

```js
let score = 78;

let grade =
score >= 90 ? "A" :
score >= 75 ? "B" :
score >= 60 ? "C" :
"Fail";
```

Output:

```js
B
```

The string is converted to a number.

### Easy Rule

- `+` prefers string concatenation.
- `-`, `*`, `/` prefer numeric conversion.


# Control Flow

Control Flow determines the order in which code executes.

It helps programs make decisions based on conditions.

---

## if Statement

Executes code only when a condition is true.

```js
let age = 20;

if(age >= 18){
    console.log("Adult");
}
```

---

## if-else Statement

Executes one block if the condition is true and another if it is false.

```js
let age = 16;

if(age >= 18){
    console.log("Adult");
}
else{
    console.log("Minor");
}
```

---

## else if Ladder

Used when multiple conditions need to be checked.

```js
let marks = 75;

if(marks >= 90){
    console.log("A");
}
else if(marks >= 75){
    console.log("B");
}
else{
    console.log("C");
}
```

---

## Early Return Pattern

Returns from a function as soon as a condition is met.

```js
function getGrade(score){
    if(score < 25) return "D";
    if(score < 50) return "C";
    if(score < 75) return "B";
    return "A";
}
```

### Benefits

- Cleaner code
- Less nesting
- Easier to read

---

## Ternary Operator

Short form of if-else.

```js
let age = 20;

let result = age >= 18 ? "Adult" : "Minor";

console.log(result);
```

---

## Example: Grade Calculator

```js
function getGrade(score){
    if(score <= 32) return "Fail";
    else if(score <= 59) return "D";
    else if(score <= 69) return "C";
    else if(score <= 79) return "B";
    else if(score <= 89) return "A";
    else return "A+";
}
```

---

## Example: Rock Paper Scissors

```js
function rps(user, comp){
    if(user === comp) return "Draw";

    if(user === "rock" && comp === "scissor")
        return "User Wins";

    return "Computer Wins";
}
```

---

## Quick Revision

- `if` → run code when condition is true
- `if-else` → choose between two options
- `else if` → check multiple conditions
- `return` → exit a function and send back a value
- Ternary → short form of if-else
- Early Return → return as soon as a condition is met

### One-Line Definition

**Control Flow is the mechanism that determines which code executes and in what order based on conditions.**

# Loops

Loops are used to execute a block of code repeatedly until a condition becomes false.

---

## for Loop

Used when the number of iterations is known.

```js
for(let i = 1; i < 10; i++){
    console.log(i);
}
```

### Syntax

```js
for(initialization; condition; increment/decrement){
    // code
}
```

---

## while Loop

Executes as long as the condition is true.

```js
let j = 1;

while(j < 20){
    console.log(j);
    j++;
}
```

### Use Case

When the number of iterations is not known beforehand.

---

## do...while Loop

Executes the code at least once, even if the condition is false.

```js
let k = 23;

do{
    console.log(k);
    k++;
}
while(k < 2);
```

Output:

```js
23
```

### Why?

The loop body runs first, then the condition is checked.

---

## break Statement

Used to immediately exit a loop.

```js
for(let i = 1; i < 201; i++){
    if(i === 32){
        break;
    }
    console.log(i);
}
```

### Use Case

Stop the loop when a specific condition is met.

---

## continue Statement

Used to skip the current iteration and move to the next one.

```js
for(let i = 1; i < 30; i++){
    if(i === 12){
        continue;
    }
    console.log(i);
}
```

Output:

```js
1 2 3 ... 11 13 14 ...
```

The value `12` is skipped.

---

## Difference Between break and continue

### break

```js
break;
```

- Exits the loop completely.

### continue

```js
continue;
```

- Skips the current iteration.
- Continues with the next iteration.

---

## Quick Revision

| Loop | Purpose |
|--------|---------|
| for | Known number of iterations |
| while | Run while condition is true |
| do...while | Runs at least once |
| break | Exit loop completely |
| continue | Skip current iteration |

### One-Line Definition

**Loops are used to execute a block of code repeatedly based on a condition.**



# Functions

Functions are reusable blocks of code that perform a specific task.

---

## Function Declaration

A function defined using the `function` keyword.

```js
function greet(){
    console.log("Hello");
}

greet();
```

### Features

- Hoisted
- Can be called before declaration

---

## Function with Parameters

Parameters allow data to be passed into a function.

```js
function add(a, b){
    return a + b;
}

console.log(add(2, 3));
```

### Parameters vs Arguments

```js
function add(a, b) // Parameters

add(2, 3); // Arguments
```

---

## Function Expression

A function stored inside a variable.

```js
const greet = function(){
    console.log("Hello");
};

greet();
```

### Note

Function expressions are not hoisted like function declarations.

---

## Arrow Functions

A shorter syntax for writing functions.

```js
const greet = () => {
    console.log("Hello");
};

greet();
```

### Example

```js
const sum = (a, b) => {
    return a + b;
};

console.log(sum(3, 4));
```

---

## Default Parameters

Used when no argument is provided.

```js
function add(a = 1, b = 1){
    console.log(a + b);
}

add();
```

Output:

```js
2
```

---

## Rest Parameters

Collect multiple arguments into an array.

```js
function numbers(...values){
    console.log(values);
}

numbers(1, 2, 3, 4);
```

Output:

```js
[1, 2, 3, 4]
```

### Use Case

Useful when the number of arguments is unknown.

---

## Return Statement

Returns a value from a function.

```js
function getNumber(){
    return 12;
}

let value = getNumber();

console.log(value);
```

### Important

After `return`, the function stops executing.

---

## Function Scope

Variables declared inside a function can only be accessed inside that function.

```js
function test(){
    let a = 10;
}

console.log(a); // Error
```

---

## Lexical Scope

An inner function can access variables from its outer scope.

```js
let a = 10;

function outer(){
    let b = 20;

    function inner(){
        console.log(a, b);
    }

    inner();
}

outer();
```

Output:

```js
10 20
```

### Simple Rule

A function can access:

- Its own variables
- Parent function variables
- Global variables

---

## Introduction to First-Class Functions

JavaScript treats functions like values.

Functions can be:

- Stored in variables
- Passed as arguments
- Returned from functions

```js
function greet(){
    console.log("Hello");
}
```

> Detailed notes in the Advanced Functions section.

---

## Introduction to Higher Order Functions

A Higher Order Function is a function that:

- Takes another function as an argument
- Returns a function

```js
function execute(fn){
    fn();
}
```

> Detailed notes in the Higher Order Functions section.

---

## Introduction to Closures

A closure allows an inner function to access variables from its outer function.

```js
function outer(){
    let a = 10;

    return function(){
        console.log(a);
    };
}
```

> Detailed notes in the Closures section.

---

## Quick Revision

| Concept | Purpose |
|----------|----------|
| Function Declaration | Define reusable code |
| Parameters | Receive data |
| Arguments | Pass data |
| Function Expression | Store function in a variable |
| Arrow Function | Shorter function syntax |
| Default Parameters | Provide default values |
| Rest Parameters | Collect multiple arguments |
| Return | Send value back |
| Function Scope | Variables accessible only inside function |
| Lexical Scope | Access parent scope variables |

---

## One-Line Definition

**Functions are reusable blocks of code that perform specific tasks and help organize programs into smaller, manageable pieces.**
