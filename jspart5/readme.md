# Browser Storage and Timers

JavaScript provides browser storage APIs and timer functions to store data and execute code after a delay or repeatedly.

---

# Local Storage

Local Storage stores data in the browser permanently until it is removed manually.

### Features

- Stores data as strings
- Persists even after browser restart
- Data remains until deleted

---

## setItem()

Stores data.

```js
localStorage.setItem("name", "manav");
```

---

## getItem()

Retrieves stored data.

```js
let value = localStorage.getItem("name");

console.log(value); // manav
```

---

## removeItem()

Removes specific data.

```js
localStorage.removeItem("name");
```

---

## Updating Data

Simply store a new value using the same key.

```js
localStorage.setItem("name", "bhatt");

console.log(
    localStorage.getItem("name")
); // bhatt
```

---

# Storing Arrays and Objects

Local Storage only stores strings.

Use JSON methods for arrays and objects.

---

## JSON.stringify()

Converts JavaScript data into JSON string format.

```js
let friends = [
    "manav",
    "ram",
    "john"
];

localStorage.setItem(
    "friends",
    JSON.stringify(friends)
);
```

---

## JSON.parse()

Converts JSON string back into JavaScript data.

```js
let data = '["manav","ram","john"]';

let friends = JSON.parse(data);

console.log(friends);

// ["manav","ram","john"]
```

---

# Session Storage

Stores data only for the current browser tab.

Data is removed when the tab is closed.

```js
sessionStorage.setItem(
    "name",
    "hello"
);

console.log(
    sessionStorage.getItem("name")
); // hello
```

---

## Local Storage vs Session Storage

| Feature | Local Storage | Session Storage |
|----------|----------|----------|
| Lifetime | Permanent | Until tab closes |
| Capacity | Larger | Smaller |
| Shared Between Tabs | Yes | No |

---

# Timers

Timers allow code to execute after a delay or repeatedly.

---

## setTimeout()

Executes code once after a delay.

```js
setTimeout(function(){

    console.log("hello");

}, 3000);
```

Output after 3 seconds:

```js
hello
```

---

## clearTimeout()

Cancels a timeout.

```js
let timer = setTimeout(function(){

    console.log("hello");

}, 3000);

clearTimeout(timer);
```

Output:

```js
Nothing happens
```

---

# setInterval()

Executes code repeatedly.

```js
setInterval(function(){

    console.log("hi");

}, 2000);
```

Output:

```js
hi
hi
hi
...
```

Every 2 seconds.

---

## clearInterval()

Stops a repeating interval.

```js
let interval = setInterval(function(){

    console.log("hi");

}, 2000);

clearInterval(interval);
```

---

# Countdown Timer Example

```js
let count = 10;

let timer = setInterval(function(){

    if(count >= 1){

        count--;

        console.log(count);

    }

    else{

        clearInterval(timer);

    }

}, 1000);
```

Output:

```js
9
8
7
...
0
```

---

# Progress Bar Example

Updating UI with setInterval.

```js
let count = 0;

setInterval(function(){

    count++;

    progress.style.width =
    `${count}%`;

}, 70);
```

### Result

```text
0% → 100%
```

Progress bar fills gradually.

---

# Auto Hide Message

Hide an element after a delay.

```js
setTimeout(function(){

    div.style.display = "none";

}, 3000);
```

### Result

```text
Message disappears after 3 seconds
```

---

# Common Use Cases

## Local Storage

- Dark mode preference
- Shopping cart
- User settings

---

## Session Storage

- Temporary login data
- Multi-step forms

---

## setTimeout()

- Notifications
- Delayed actions
- Splash screens

---

## setInterval()

- Clocks
- Countdowns
- Progress bars
- Live updates

---

# Quick Revision

| Method | Purpose |
|----------|----------|
| localStorage.setItem() | Store data |
| localStorage.getItem() | Retrieve data |
| localStorage.removeItem() | Remove data |
| JSON.stringify() | Convert JS → JSON |
| JSON.parse() | Convert JSON → JS |
| sessionStorage.setItem() | Store temporary data |
| setTimeout() | Run once after delay |
| clearTimeout() | Cancel timeout |
| setInterval() | Run repeatedly |
| clearInterval() | Stop interval |

---

# One-Line Definition

**Local Storage, Session Storage, and Timers allow JavaScript to store data in the browser and execute code after a delay or at regular intervals.**
