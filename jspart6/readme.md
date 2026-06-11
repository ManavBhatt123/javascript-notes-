
 
# Object-Oriented Programming (OOP)

Object-Oriented Programming is a programming paradigm that organizes code into objects and classes.

A class acts as a blueprint, while objects are instances created from that blueprint.

---

## Class

A class is a template used to create objects.

```js
class Pencil{
    constructor(name,color){
        this.name = name;
        this.color = color;
    }
}
```

---

## Constructor

A special method that runs automatically when an object is created.

```js
class Pencil{
    constructor(name,color){
        this.name = name;
        this.color = color;
    }
}
```

---

## Creating Objects

Objects are created using the `new` keyword.

```js
let p1 = new Pencil("Nataraj","red");

console.log(p1.name); // Nataraj
console.log(p1.color); // red
```

---

## Instance Methods

Methods are functions defined inside a class.

```js
class Pencil{

    write(text){
        console.log(text);
    }

}
```

### Example

```js
p1.write("Hello");

// Hello
```

---

## Example: Pencil Class

```js
class CreatePencil{

    constructor(name,color,price,company){
        this.name = name;
        this.color = color;
        this.price = price;
        this.company = company;
    }

    write(text){

        let h1 = document.createElement("h1");

        h1.textContent = text;

        h1.style.color = this.color;

        document.body.appendChild(h1);
    }

}
```

---

## Inheritance

Inheritance allows one class to acquire properties and methods from another class.

```js
class User{

    write(text){
        console.log(text);
    }

}

class Admin extends User{

}
```

### Benefit

Code reuse.

---

## extends Keyword

Used to inherit from another class.

```js
class Admin extends User{

}
```

---

## super()

Calls the parent class constructor.

```js
class Admin extends User{

    constructor(name){

        super(name);

    }

}
```

---

## Example: User and Admin

```js
class User{

    constructor(name){
        this.name = name;
    }

}

class Admin extends User{

    constructor(name){

        super(name);

        this.role = "admin";

    }

}
```

### Creating Objects

```js
let user = new User("Manav");

let admin = new Admin("Ram");

console.log(admin.role); // admin
```

---

## Method Overriding

A child class can define its own version of a method.

```js
class User{

    greet(){
        console.log("Hello User");
    }

}

class Admin extends User{

    greet(){
        console.log("Hello Admin");
    }

}
```

---

## Quick Revision

| Concept | Purpose |
|----------|----------|
| class | Blueprint for objects |
| constructor | Initialize object |
| new | Create object |
| this | Current object |
| method | Function inside class |
| extends | Inherit class |
| super() | Call parent constructor |
| inheritance | Reuse code |

---

## One-Line Definition

**OOP is a programming approach that organizes code into classes and objects to improve reusability and maintainability.**
