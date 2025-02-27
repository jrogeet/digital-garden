---
{"dg-publish":true,"permalink":"/programming/web-development/front-end/javascript-vanilla/01-basics/10-loops/05-continue-to-next-iteration/","tags":["programming","webdevelopment","frontend","JavaScript"],"created":"2024-11-09T11:30:42.091+08:00"}
---


# 05 Continue to next iteration

---

"lighter version of `break`"
Doesn't stop the whole loop,
It stops the **current iteration** and forces the loop to start a new one.

```javascript
for (let i = 0; i < 10; i++) {
  // if true, skip the remaining part of the body
  if (i % 2 == 0) continue;

  alert(i); // 1, then 3, 5, 7, 9
}
```

> [!Tip] `continue` directive helps decrease _nesting_
> The same as above, but less readable:
>
> ```javascript
> for (let i = 0; i < 10; i++) {
>   if (i % 2) {
>     alert(i);
>   }
> }
> ```

> [!danger] No `break/continue` to the right side of `?`
> Syntax constructs that are not expressions cannot be used with ternary operator `?`
>
> - like `break/continue` aren't allowed:
>
> ```javascript
> if (i > 5) {
> 	alert(i);
> } else {
> 	continue;
> }
> ```
>
> rewrite using question mark:
>
> ```javascript
> (i > 5) ? alert(i) : continue; // continue isn't allowed here
> ```
