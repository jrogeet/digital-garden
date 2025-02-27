---
{"dg-publish":true,"permalink":"/programming/web-development/front-end/javascript-vanilla/03-objects/07-symbol-type/06-symbol-key-for/","tags":["programming","webdevelopment","frontend","JavaScript"],"created":"2024-11-09T11:30:33.335+08:00"}
---


# Symbol.keyFor

---

- `Symbol.for(key)`

```javascript
// get symbol by name
let sym = Symbol.for("name");
let sym2 = Symbol.for("id");

// get name by symbol
alert(Symbol.keyFor(sym)); // name
alert(Symbol.keyFor(sym2)); // id
```

> [!tip] `Symbol.keyFor` only works with **Global Symbol**
> `Symbol.keyFor` uses the **Global Symbol registry**
> It doesn't work with **_Non-global symbols_**
>
> ```javascript
> let globalSymbol = Symbol.for("name");
> let localSymbol = Symbol("name");
>
> alert(Symbol.keyFor(globalSymbol)); // name, global symbol
> alert(Symbol.keyFor(localSymbol)); // undefined, not global
>
> alert(localSymbol.description); // name
> ```
