---
{"dg-publish":true,"permalink":"/programming/web-development/front-end/javascript-vanilla/01-basics/08-conditionals/05-multiple-question-mark-ternary-operator/","tags":["programming","webdevelopment","frontend","JavaScript"],"created":"2024-11-09T11:30:42.206+08:00"}
---


# 05 Multiple Question Mark (Ternary) Operator

---

```javascript
let age = prompt("age?", 18);

let message =
  age < 3
    ? "Hi, baby!"
    : age < 18
    ? "Hello"
    : age < 100
    ? "Greetings!"
    : "What an unusual age!";

alert(message);
```

> [!example]- How it works:
>
> 1. The first question mark checks whether `age < 3`.
> 2. If true – it returns `'Hi, baby!'`. Otherwise, it continues to the expression after the colon “:”, checking `age < 18`.
> 3. If that’s true – it returns `'Hello!'`. Otherwise, it continues to the expression after the next colon “:”, checking `age < 100`.
> 4. If that’s true – it returns `'Greetings!'`. Otherwise, it continues to the expression after the last colon “:”, returning `'What an unusual age!'`.

Here's how it looks using `if...else`:

```javascript
if (age < 3) {
  message = "Hi, baby!";
} else if (age < 18) {
  message = "Hello!";
} else if (age < 100) {
  message = "Greetings!";
} else {
  message = "What an unsual age!";
}
```
