---
{"dg-publish":true,"permalink":"/programming/web-development/front-end/react-js/00-essential-java-script/014-asynchronous-java-script-async-await/","tags":["programming","jsbasics","javascript","JS-Fundamentals"],"created":"2024-12-27T21:14:31.689+08:00"}
---


> [!tip] After learning it: 
 There's actually no difference between the original `fetch().then()` and `async/await`, only for __readability__ & _syntax_

> [!quote] Asynchronous
 JavaScript will __NOT wait until the data is fetched__, `fetch()` will just execute as a function and ___move to the next line___.

> [!abstract] AsyncAwait
> with `async` & `await`, it turns the `fetch()` method into a __synchronous__.
> ```js
> async function getTodos() {
>  const res = await fetch("https://jsonplaceholder.typicode.com/todos")
>  const data = await res.json();
>  console.log(data);
> }
> 
> getTodos();
> ```
> - Though, only inside the `async function` becomes synchronous
> ```js
> async function getTodos() {
>  const res = await fetch("https://jsonplaceholder.typicode.com/todos")
>  const data = await res.json();
>  console.log(data);
>  
>  return data;
> }
> 
>const todos = getTodos(); // You'd want to put an async/await or then here if you want to handle this promise again
>console.log(todos); // Promise { <pending> }
>
> console.log("Still the same as asynchronous....idk bruh");
> ```
> - You'd have to put a `then()` after the `const todos...` line,
> 	- but that is not common in ReactJS, since after receiving the data from the `fetch`; We set the `state`

