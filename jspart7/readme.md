# Asynchronous JavaScript

JavaScript is single-threaded, but it can handle asynchronous tasks using callbacks, promises, and async/await.

---

# Synchronous JavaScript

Code executes line by line.

```js
console.log("hello1");
console.log("hello2");
console.log("hello3");
```

Output:

```js
hello1
hello2
hello3
```

### Characteristics

- Executes one statement at a time.
- Waits for current task to finish before moving to the next.

---

# Asynchronous JavaScript

Some tasks take time to complete.

JavaScript does not wait for them and continues executing the remaining code.

```js
console.log("hey1");
console.log("hey2");

setTimeout(() => {
    console.log("hey3");
}, 3000);

console.log("hey4");
```

Output:

```js
hey1
hey2
hey4
hey3
```

### Why?

`setTimeout()` is handled by browser APIs and executes later.

---

# Callback Functions

A callback is a function passed as an argument to another function.

```js
function greet(callback){
    callback();
}

greet(function(){
    console.log("Hello");
});
```

Output:

```js
Hello
```

---

## Example

```js
function kuchDerBaad(callback){

    setTimeout(callback, 2000);

}

kuchDerBaad(function(){

    console.log("Hello");

});
```

Output after 2 seconds:

```js
Hello
```

---

# Callback Example with Data

```js
function profileLekarAao(username, callback){

    setTimeout(() => {

        callback({ username });

    }, 2000);

}

profileLekarAao("manav", function(data){

    console.log(data);

});
```

Output:

```js
{
  username: "manav"
}
```

---

# Promises

A Promise represents a value that may be available now, later, or never.

---

## Promise States

```text
Pending
   ↓
Fulfilled (Resolved)

OR

Rejected
```

---

## Creating a Promise

```js
let pr = new Promise(function(resolve, reject){

    setTimeout(() => {

        resolve("Success");

    }, 2000);

});
```

---

## then()

Runs when promise is resolved.

```js
pr.then(function(value){

    console.log(value);

});
```

Output:

```js
Success
```

---

## catch()

Runs when promise is rejected.

```js
pr.catch(function(error){

    console.log(error);

});
```

---

## Example

```js
let pr = new Promise(function(resolve, reject){

    let random = Math.floor(Math.random() * 10);

    if(random > 5)
        resolve(random);

    else
        reject(random);

});
```

### Possible Output

```js
8
```

or

```js
3
```

---

# Async and Await

`async/await` is a cleaner way to work with promises.

---

## async Function

```js
async function demo(){

}
```

An async function automatically returns a Promise.

---

## await Keyword

Waits for a Promise to finish.

```js
let value = await promise;
```

---

## Example

```js
let pr = new Promise(function(resolve){

    setTimeout(() => {

        resolve("Success");

    }, 1000);

});

async function test(){

    let value = await pr;

    console.log(value);

}

test();
```

Output:

```js
Success
```

---

# Error Handling with try...catch

Used with async/await.

```js
async function test(){

    try{

        let value = await pr;

        console.log(value);

    }

    catch(error){

        console.log(error);

    }

}
```

---

## Example

```js
async function abcd(){

    try{

        let value = await pr1;

        console.log(value);

    }

    catch(error){

        console.log(error);

    }

}

abcd();
```

---

# Flow Comparison

## Callback

```js
getData(function(data){

    console.log(data);

});
```

---

## Promise

```js
getData()
    .then(function(data){

        console.log(data);

    });
```

---

## Async/Await

```js
let data = await getData();

console.log(data);
```

---

# Quick Revision

| Concept | Purpose |
|----------|----------|
| Synchronous | Executes line by line |
| Asynchronous | Doesn't block execution |
| Callback | Function passed to another function |
| Promise | Handles future values |
| resolve() | Promise success |
| reject() | Promise failure |
| then() | Handle success |
| catch() | Handle error |
| async | Creates async function |
| await | Wait for promise |
| try...catch | Handle async errors |

---

# One-Line Definition

**Asynchronous JavaScript allows time-consuming operations to run without blocking the execution of other code using callbacks, promises, and async/await.**

