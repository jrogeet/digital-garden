---
{"dg-publish":true,"permalink":"/programming/web-development/front-end/javascript-vanilla/01-basics/06-basic-operators/07-modify-in-place/","tags":["programming","webdevelopment","frontend","JavaScript"],"created":"2024-11-09T11:30:42.329+08:00"}
---


# 07 Modify-in-place

---

```javascript
let n = 2;

n = n + 5;
n += 5; // n = 7 (same as n = n + 5)

n = n * 2;
n *= 2; // n = 14 (same as n = n * 2)

alert(n); // 14
```

```javascript
let n = 2;

n *= 3 + 5; // right part evaluated first, same as n *= 8

alert(n); // 16
```
