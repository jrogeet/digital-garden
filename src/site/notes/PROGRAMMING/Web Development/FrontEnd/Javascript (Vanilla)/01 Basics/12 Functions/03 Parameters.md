---
{"dg-publish":true,"permalink":"/programming/web-development/front-end/javascript-vanilla/01-basics/12-functions/03-parameters/","tags":["programming","webdevelopment","frontend","JavaScript"],"created":"2024-11-09T11:30:42.458+08:00"}
---

# 03 Parameters

--- 
>[!INFO]
>- A __parameter__ is the variable listed inside the _parentheses_ in the function declaration
>- An ___argument___ is the value that is passed to the function when it is called

```javascript
function showMessage(from, text) { // paraemeters: from, text
	alert(from + ' : ' + text);
}

showMessage('Ann', 'Hello!'); // Ann: Hello!
showMessage('Ann', "What's up?"); // Ann: What's up?
```

```javascript
function showMessage(from, text) {
	from = '*' + from + '*'; // make "from" look nicer
	
	alert( from + ': ' + text);
}

let from = "Ann";

showMessage(from, "Helo"); // *Ann*: Hello

// the value of "from" is the same, the function modified a local copy
alert( from ); // Ann
```
- The global variable `from` is _not modified_
- The function changes `from`
	- but is not seen outside, because a function gets a copy of the value