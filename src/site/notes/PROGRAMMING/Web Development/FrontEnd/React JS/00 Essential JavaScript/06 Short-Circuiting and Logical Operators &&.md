---
{"dg-publish":true,"permalink":"/programming/web-development/front-end/react-js/00-essential-java-script/06-short-circuiting-and-logical-operators-and-and/","tags":["programming","jsbasics","javascript","JS-Fundamentals"],"created":"2024-12-24T17:38:05.003+08:00"}
---


- __Short-Circuiting__: In logical operations, operator will return the _1st value_ ___without even looking___ at the _second value_ 

### `&&` (AND) operator
```javascript
console.log(true && "Some string"); // Some string
console.log(false && "Some string"); // false

const hasMovieAdaptation = true;
console.log(hasMovieAdaptation && "This book has a movie"); // This book has a movie
```

Falsy: `0`, `''`, `null`, `undefined`
```javascript
console.log("jonas" && "Some string"); // Some string
```
- `"jonas"` returns as __True__, so the _second value_ is picked.

```javascript
console.log(0 && "Some string"); // 0
```
- `0` is a ___Falsy___ value

### `||` (OR) operator

```js
console.log(true || "Some string"); // true
console.log(false || "Some string"); // Some string
```


---
> [!example]
> ```js
> console.log(book.translations.spanish); // undefined
> const spanishTranslation = book.translations.spanish || "NOT TRANSLATED"; // NOT TRANSLATED
> ```
> 
> ```js
> console.log(book.reviews.librarything.reviewsCount); // 0
> const countWrong = book.reviews.librarything.reviewsCount || "no data"'; // no data
> 
> ```
> - It says `no data` even tho, there's a value `0`
> - It's wrong, so we'll use [[04 Nullish coalescing operator \| Null Coalescing Operator]]:
> 	- returns the _second value_ only if it's `null` or `undefined` BUT __NOT__ if it's `0` or `''` (empty string)
> ```js
> const count = book.reviews.librarything.reviewsCount ?? "no data";
> ```

