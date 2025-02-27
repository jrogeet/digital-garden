---
{"dg-publish":true,"permalink":"/programming/web-development/front-end/javascript-vanilla/01-basics/07-comparisons/05-comparison-with-null-and-undefined/","tags":["programming","webdevelopment","frontend","JavaScript"],"created":"2024-11-09T11:30:41.759+08:00"}
---


# 05 Comparison with null and undefined

---

**String Equally check** `===`

- These values are different, because each of them is a different type

```javascript
alert(null === undefined); // false
```

**Non-strict check** `==`

- They equal each other (in the sense of `==`), but not any other value.

```javascript
alert(null == undefined); // true
```

**Math and other comparisons** `< > <= >=`

- `null` becomes `0`
- `undefined` becomes `NaN`

> [!caution] null vs 0
>
> ```javascript
> alert(null > 0); // (1) false
> alert(null == 0); // (2) false
> alert(null >= 0); // (3) true
> ```
>
> **Equality check** `==` and **_comparisons_** `> < >= <=` work differently.
>
> - Comparisons convert `null` to a number, treating it as `0`.
>   - That's why (3) `null >= 0` is _true_ and (1) `null > 0` is _false_
> - Equality check `==` for `undefined` and `null` (without any conversion) equal each other
>   - and don't equal anything else.
>   - That's why (2) `null == 0` is false

> [!caution] An incomparable undefined
> The value `undefined` shouldn't be compared to other values:
>
> ```javascript
> alert(undefined > 0); // false (1)
> alert(undefined < 0); // false (2)
> alert(undefined == 0); // false (3)
> ```
>
> - Comparisons `(1)` and `(2)` returns `false` because `undefined` gets converted to `NaN`
>   - `NaN` is a special numeric value which returns `false` for **all comparisons**
> - Equality check `(3)` returns `false` because `undefined` **_only equals_** `null`,`undefined`, and no other value.

### More examples:

```javascript
5 > 4; // true
```

```javascript
"apple" > "pineapple"; // false
```

- False, Dictionary comparison, `"a"` is smaller than `"p"`.

```javascript
"2" > "12"; // true
```

- True, Dictionary comparison, first char `"2"` is greater than the first char `"1"`

```javascript
undefined == null; // true
```

- `null` and `undefined` equal each other only.

```javascript
undefined === null; // false
```

- **Strict equality** is strict.
  - Different types from both sides lead to _false_

```javascript
null == "\n0\n"; // false
```

- _False_, `null` only equals `undefined`

```javascript
null === +"\n0\n"; // false
```

- Strict equality of different types.
