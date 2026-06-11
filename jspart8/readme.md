# Advanced JavaScript

These concepts are commonly used in real-world applications for API calls, code organization, design patterns, and performance optimization.

---

# Fetch API

The Fetch API is used to make HTTP requests and retrieve data from servers.

```js
fetch("https://randomuser.me/api/")
    .then(function(response){
        return response.json();
    })
    .then(function(data){
        console.log(data);
    })
    .catch(function(error){
        console.log(error);
    });
```

### Flow

```text
Request
   ↓
Response
   ↓
Convert to JSON
   ↓
Use Data
```

### Important

- Returns a Promise
- Used for API calls
- Common in React applications

---

# IIFE (Immediately Invoked Function Expression)

A function that executes immediately after being created.

```js
(function(){

    console.log("Hello");

})();
```

Output:

```js
Hello
```

### Why Use It?

- Create private variables
- Avoid global scope pollution

---

# Module Pattern

Uses closures to create private data and expose only selected methods.

```js
let bank = (function(){

    let balance = 10000;

    function checkBalance(){
        console.log(balance);
    }

    return {
        checkBalance
    };

})();
```

### Benefit

```text
Private Data
+
Public Methods
```

---

# Revealing Module Pattern

Similar to Module Pattern but explicitly reveals public methods.

```js
let bank = (function(){

    function withdraw(){}

    return {
        draw: withdraw
    };

})();
```

### Benefit

Provides cleaner public APIs.

---

# Factory Function Pattern

Functions that create and return objects.

```js
function createProduct(name, price){

    return {
        name,
        price
    };

}

let iphone = createProduct(
    "iPhone",
    70000
);
```

### Why Use Factory Functions?

- Create multiple similar objects
- Simpler than classes for small projects

---

# Observer Pattern

A design pattern where subscribers are notified when something changes.

### Real Examples

- YouTube subscriptions
- Notifications
- React state updates

---

## Example

```js
channel.subscribe(user);

channel.notify(
    "New Video Uploaded"
);
```

Output:

```js
Manav, New Video Uploaded
Ram, New Video Uploaded
```

### Flow

```text
Publisher
      ↓
Subscribers
      ↓
Notification
```

---

# Debouncing

Limits how often a function executes.

The function runs only after the user stops triggering events.

```js
function debounce(fn, delay){

    let timer;

    return function(...args){

        clearTimeout(timer);

        timer = setTimeout(function(){

            fn(...args);

        }, delay);

    };

}
```

### Example

```js
Search Bar
```

User types:

```text
m
ma
man
mana
manav
```

Only one API request is sent after typing stops.

### Benefit

- Improves performance
- Reduces API calls

---

# Throttling

Limits function execution to once every specified interval.

```js
function throttle(fn, delay){

    let lastTime = 0;

    return function(...args){

        let now = Date.now();

        if(now - lastTime >= delay){

            lastTime = now;

            fn(...args);

        }

    };

}
```

### Example

```text
Scrolling
Mouse Movement
Window Resize
```

### Benefit

Prevents excessive function calls.

---

# Debounce vs Throttle

| Feature | Debounce | Throttle |
|----------|----------|----------|
| Execution | After user stops | At fixed intervals |
| Best For | Search bars | Scroll events |
| API Calls | Reduced greatly | Controlled frequency |

---

# Quick Revision

| Concept | Purpose |
|----------|----------|
| Fetch API | Request data from servers |
| IIFE | Execute function immediately |
| Module Pattern | Private + Public methods |
| Revealing Module Pattern | Cleaner module API |
| Factory Function | Create objects |
| Observer Pattern | Notify subscribers |
| Debounce | Delay execution |
| Throttle | Limit execution rate |

---

# One-Line Definitions

### Fetch API

Retrieve data from servers using HTTP requests.

### IIFE

A function that runs immediately after creation.

### Module Pattern

Uses closures to create private data and public methods.

### Factory Function

A function that returns objects.

### Observer Pattern

Subscribers receive updates when data changes.

### Debounce

Wait until events stop before executing.

### Throttle

Limit execution to once per specified interval.
