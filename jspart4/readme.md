# Form Validation

Form Validation ensures that user input is correct before processing or submitting data.

---

## Why Validation?

Validation helps:

- Prevent invalid data
- Improve user experience
- Increase security
- Ensure required fields are filled

---

## Prevent Form Submission

By default, forms reload the page after submission.

Use `preventDefault()` to stop this behavior.

```js
form.addEventListener("submit", function(event){

    event.preventDefault();

    console.log("Form Submitted");
});
```

---

## Basic Name Validation

Check if the name contains at least 3 characters.

```js
form.addEventListener("submit", function(event){

    event.preventDefault();

    if(name.value.length <= 2){
        error.style.display = "block";
    }
});
```

### Example

Input:

```text
ab
```

Output:

```text
your name should be more than 2 characters
```

---

## Regular Expressions (Regex)

Regex is used to match patterns inside strings.

Example:

```js
const regex = /abc/;
```

### Common Use Cases

- Email validation
- Password validation
- Phone numbers
- Usernames

---

## Email Validation

### Email Regex

```js
const emailRegex =
/^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
```

### Test Email

```js
let result = emailRegex.test("manav@test.com");

console.log(result); // true
```

### Invalid Email

```js
let result = emailRegex.test("manav@test./com");

console.log(result); // false
```

---

## Password Validation

### Password Rules

Password must contain:

- At least 8 characters
- One letter
- One number
- One special character

### Password Regex

```js
const passwordRegex =
/^(?=.*[A-Za-z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$/;
```

### Example

```js
passwordRegex.test("Manav@123");

// true
```

---

## Regex test()

Used to check whether a string matches a pattern.

```js
const regex = /abc/;

console.log(regex.test("abcdef")); // true
console.log(regex.test("xyz")); // false
```

---

## Displaying Error Messages

```js
if(!emailValid){

    emailError.textContent =
    "Email is incorrect";

    emailError.style.display =
    "block";
}
```

### Result

```text
Email is incorrect
```

---

## Success Message

```js
if(emailValid && passwordValid){

    successMessage.textContent =
    "Everything is Correct";

    successMessage.style.display =
    "block";
}
```

### Result

```text
Everything is Correct
```

---

## Validation Flow

```text
User Input
     ↓
Form Submit
     ↓
preventDefault()
     ↓
Validate Data
     ↓
Show Error OR Success
```

---

## Mini Example

```js
form.addEventListener("submit", function(event){

    event.preventDefault();

    if(emailRegex.test(email.value)){
        console.log("Valid Email");
    }
    else{
        console.log("Invalid Email");
    }
});
```

---

## Quick Revision

| Concept | Purpose |
|----------|----------|
| Form Validation | Check user input |
| preventDefault() | Stop page reload |
| Regex | Pattern matching |
| test() | Check pattern match |
| Email Regex | Validate email |
| Password Regex | Validate password |
| Error Message | Show validation errors |
| Success Message | Show successful validation |

---

## Common Regex Examples

### Digits Only

```js
/^\d+$/
```

### Letters Only

```js
/^[A-Za-z]+$/
```

### Email

```js
/^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/
```

---

## One-Line Definition

**Form Validation is the process of checking user input before accepting or processing it.**
