## Creating an Array

```js
let marks = [10, 20, 30, 40];

console.log(marks[2]); // 30

marks[2] = 50;

console.log(marks); // [10, 20, 50, 40]
```

---

### push()

Adds an element to the end of an array.

```js
let arr = [1, 2, 3];

arr.push(4);

console.log(arr); // [1, 2, 3, 4]
```

---

### pop()

Removes the last element.

```js
let arr = [1, 2, 3, 4];

arr.pop();

console.log(arr); // [1, 2, 3]
```

---

### shift()

Removes the first element.

```js
let arr = [1, 2, 3, 4];

arr.shift();

console.log(arr); // [2, 3, 4]
```

---

### unshift()

Adds an element to the beginning.

```js
let arr = [1, 2, 3];

arr.unshift(10);

console.log(arr); // [10, 1, 2, 3]
```

---

### splice()

Adds or removes elements from an array.

```js
let arr = [1, 2, 3, 4, 5];

arr.splice(2, 1);

console.log(arr); // [1, 2, 4, 5]
```

---

### slice()

Returns a portion of an array.

```js
let arr = [1, 2, 3, 4, 5];

let newArr = arr.slice(1, 4);

console.log(newArr); // [2, 3, 4]
```

---

### reverse()

Reverses the array.

```js
let arr = [1, 2, 3];

arr.reverse();

console.log(arr); // [3, 2, 1]
```

---

### sort()

Sorts array elements.

```js
let arr = [2, 6, 4, 7];

arr.sort(function(a, b){
    return a - b;
});

console.log(arr); // [2, 4, 6, 7]
```

---

### forEach()

Executes a function for every element.

```js
let arr = [1, 2, 3];

arr.forEach(function(val){
    console.log(val);
});

// 1
// 2
// 3
```

---

### map()

Creates a new array based on each element.

```js
let arr = [1, 2, 3];

let result = arr.map(function(val){
    return val * 2;
});

console.log(result); // [2, 4, 6]
```

---

### filter()

Returns elements that satisfy a condition.

```js
let arr = [1, 2, 3, 4, 5];

let result = arr.filter(function(val){
    return val > 3;
});

console.log(result); // [4, 5]
```

---

### reduce()

Reduces an array to a single value.

```js
let arr = [1, 2, 3, 4];

let sum = arr.reduce(function(acc, val){
    return acc + val;
}, 0);

console.log(sum); // 10
```

---

### find()

Returns the first matching element.

```js
let arr = [3, 5, 6, 7];

let result = arr.find(function(val){
    return val === 3;
});

console.log(result); // 3
```

---

### some()

Checks if at least one element satisfies a condition.

```js
let arr = [20, 34, 45, 67];

let result = arr.some(function(val){
    return val > 60;
});

console.log(result); // true
```

---

### every()

Checks if all elements satisfy a condition.

```js
let arr = [23, 45, 35, 78];

let result = arr.every(function(val){
    return val > 20;
});

console.log(result); // true
```

---

### Array Destructuring

```js
let arr = [1, 2, 3, 4];

let [a, b, , c] = arr;

console.log(a); // 1
console.log(b); // 2
console.log(c); // 4
```

---

### Spread Operator (...)

```js
let arr1 = [1, 2];
let arr2 = [3, 4];

let merged = [...arr1, ...arr2];

console.log(merged); // [1, 2, 3, 4]
```

## Quick Revision

| Method | Purpose |
|----------|----------|
| push() | Add at end |
| pop() | Remove from end |
| shift() | Remove from start |
| unshift() | Add at start |
| splice() | Add/Remove elements |
| slice() | Copy part of array |
| reverse() | Reverse array |
| sort() | Sort array |
| forEach() | Perform action on each element |
| map() | Create new transformed array |
| filter() | Select matching elements |
| reduce() | Reduce to single value |
| find() | Find first matching element |
| some() | Check if at least one matches |
| every() | Check if all match |
| Destructuring | Extract values |
| Spread Operator | Copy/expand arrays |

---

## One-Line Definition

**Arrays are ordered collections of values that allow storing and manipulating multiple items using indexes and built-in methods.**


# Objects

Objects are used to store data in key-value pairs.

```js
let user = {
    name: "Manav",
    age: 20
};
```

---

## Creating an Object

```js
let user = {
    name: "Manav",
    age: 20
};

console.log(user);
```

---

## Accessing Properties

### Dot Notation

```js
let user = {
    name: "Manav"
};

console.log(user.name); // Manav
```

### Bracket Notation

```js
let user = {
    name: "Manav"
};

console.log(user["name"]); // Manav
```

### When to Use Bracket Notation

Useful when:

- Property names contain spaces or special characters
- Property names are dynamic

```js
const user = {
    "first-name": "Manav"
};

console.log(user["first-name"]); // Manav
```

---

## Nested Objects

Objects can contain other objects.

```js
const user = {
    name: "Manav",
    address: {
        city: "Delhi",
        location: {
            lat: 21.3,
            lng: 17.5
        }
    }
};

console.log(user.address.location.lat); // 21.3
```

---

## Object Destructuring

Extract properties into variables.

```js
const user = {
    address: {
        location: {
            lat: 21.3,
            lng: 17.5
        }
    }
};

let { lat, lng } = user.address.location;

console.log(lat); // 21.3
console.log(lng); // 17.5
```

---

## Destructuring Special Property Names

```js
const user = {
    "first-name": "Manav"
};

let { "first-name": firstName } = user;

console.log(firstName); // Manav
```

---

## Looping Through Objects

### for...in Loop

```js
let user = {
    name: "Manav",
    age: 20
};

for(let key in user){
    console.log(key, user[key]);
}
```

Output:

```js
name Manav
age 20
```

---

## Object.keys()

Returns all keys as an array.

```js
let user = {
    name: "Manav",
    age: 20
};

console.log(Object.keys(user));

// ["name", "age"]
```

---

## Object.entries()

Returns key-value pairs as arrays.

```js
let user = {
    name: "Manav",
    age: 20
};

console.log(Object.entries(user));

// [["name","Manav"],["age",20]]
```

---

## Dynamic Property Access

```js
let key = "age";

const user = {
    age: 20
};

console.log(user[key]); // 20
```

---

## Dynamic Property Creation

```js
const key = "role";

const user = {
    name: "Manav",
    [key]: "admin"
};

console.log(user.role); // admin
```

---

## Object Copying

### Spread Operator

```js
let obj1 = {
    name: "Raj",
    age: 24
};

let obj2 = { ...obj1 };

console.log(obj2);

// { name: "Raj", age: 24 }
```

---

### Object.assign()

```js
let obj1 = {
    name: "Raj",
    age: 24
};

let obj2 = Object.assign(
    { price: Infinity },
    obj1
);

console.log(obj2);

// { price: Infinity, name: "Raj", age: 24 }
```

---

## Deep Cloning

Creates a completely separate copy.

```js
let obj = {
    name: "Max",
    address: {
        city: "Delhi"
    }
};

let copy = JSON.parse(
    JSON.stringify(obj)
);

console.log(copy);
```

### Why?

Changing nested values in the copied object will not affect the original object.

---

## Optional Chaining

Prevents errors when accessing properties that may not exist.

```js
let user = {
    name: "Max"
};

console.log(user.price); // undefined

console.log(user.name?.age); // undefined
```

### Benefit

Instead of throwing an error, JavaScript returns `undefined`.

---

## Object Keys Can Be Numbers or Booleans

```js
const obj = {
    true: "yes",
    43: "answer"
};

console.log(obj[43]); // answer

console.log(obj[true]); // yes
```

---

## Practice Example

```js
let student = {
    name: "Manav",
    age: 20,
    isEnrolled: true
};

console.log(student.name); // Manav
```

---

## Quick Revision

| Concept | Purpose |
|----------|----------|
| Dot Notation | Access property |
| Bracket Notation | Access dynamic/special properties |
| Nested Objects | Objects inside objects |
| Destructuring | Extract properties |
| for...in | Loop through object |
| Object.keys() | Get all keys |
| Object.entries() | Get key-value pairs |
| Spread Operator | Copy object |
| Object.assign() | Copy/Merge objects |
| Deep Clone | Independent copy |
| Optional Chaining | Safe property access |

---

## One-Line Definition

**Objects are collections of key-value pairs used to store and organize related data.**
