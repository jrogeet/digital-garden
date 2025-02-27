---
{"dg-publish":true,"permalink":"/programming/web-development/front-end/javascript-vanilla/01-basics/07-comparisons/03-comparison-of-different-types/","tags":["programming","webdevelopment","frontend","JavaScript"],"created":"2024-11-09T11:30:41.743+08:00"}
---


# 03 Comparison of Different Types

---

JavaScript converts values to numbers when comparing values of different types.

```javascript
alert("2" > 1); // true, string '2' becomes number 2
alert("01" == 1); // true, string '01' becomes number 1
```

Boolean values:

- `true` == `1`
- `false` == `0`

```javascript
alert(true == 1); // true
alert(false == 0); // false
```

> [!tip]
> It's possible that at the same time:
>
> - Two values are equal
> - One of them is `true` as a boolean,
> - and the other one is `false` as a boolean.
>
> ```javascript
> let a = 0;
> alert(Boolean(a)); // false
>
> let b = "0";
> alert(Boolean(b)); // true
>
> alert(a == b); // true
> ```
