---
{"dg-publish":true,"permalink":"/programming/web-development/front-end/javascript-vanilla/03-objects/04-object-methods-this/02-this-in-methods/","tags":["programming","webdevelopment","frontend","JavaScript"],"created":"2024-11-09T11:30:39.564+08:00"}
---


# "this" in methods

---

> [!info] **To access an object, a method can use the `this` keyword.**
> An object method commonly needs to access the information in the `object`.
> Like the code inside `user.sayHi()` may need the name of the `user`.
>
> The value of `this` is the object "_before dot_", the one used to call the method.
> Example:
>
> ```javascript
> let user = {
>   name: "John",
>   age: 30,
>
>   sayHi() {
>     // "this" is the "current object"
>     alert(this.name);
>   },
> };
>
> user.sayHi();
> ```
>
> > [!danger] It's also possible to access the object without `this`, by referencing it via the outer variable:
> >
> > ```javascript
> > let user = {
> >   name: "John",
> >   age: 30,
> >
> >   sayHi() {
> >     alert(user.name); // "user" instead of "this"
> >   },
> > };
> > ```
> >
> > But it's **UNRELIABLE**. If we decide to copy `user` to another variable e.g. `admin = user` and **_overwrite_** `user` with something else, then **it will access the wrong object.**
> >
> > ```javascript
> > let user = {
> >   name: "John",
> >   age: 30,
> >
> >   sayHi() {
> >     alert(user.name); // leads to an error
> >   },
> > };
> >
> > let admin = user;
> > user = null; // overwrite to make things obvious
> >
> > admin.sayHi(); // TypeError: Cannot read property 'name' of null
> > ```
> >
> > using `this.name` inside the `alert` would work.
> > `user.name` wouldn't work.

> [!tip] `this` **is not bound**
> It can be used in any function, even **if it's not a method of an object.**
> No syntax error:
>
> ```javascript
> function sayHi() {
>   alert(this.name);
> }
> ```
>
> ```javascript
> let user = { name: "John" };
> let admin = { name: "Admin" };
>
> function sayHi() {
>   alert(this.name);
> }
>
> // use the same function in two objects
> user.f = sayHi;
> admin.f = sayHi;
>
> // these calls have different this
> // "this" inside the function the object "before the dot"
> user.f(); // John (this == user)
> admin.f(); // Admin (this == admin)
>
> admin["f"](); // Admin (dot or square brackets access the method - doesn't matter)
> ```
>
> > [!danger] Calling **without an object:** `this == undefined`
> >
> > ```javascript
> > function sayHi() {
> >   alert(this);
> > }
> >
> > sayHi(); // undefined
> > ```
> >
> > here `this` is `undefined` in **_strict mode_**. `this.name` will cause an error.
> > in **_non-strict mode_**, the value of `this` will be the **global object**.

> [!caution] **Arrow functions** have no `"this"`
> Arrow functions are special and don't have their "own" `this`
> If we reference `this` from such a function, it's taken from the **outer "normal" function**.
>
> ```javascript
> let user = {
>   firstName: "Ilya",
>   sayHi() {
>     let arrow = () => alert(this.firstName);
>     arrow();
>   },
> };
>
> user.sayHi(); // Ilya
> ```
>
> here `arrow()` uses `this` form the **outer `user.sayHi()` method**.

---

> [!example] Using `this` in **object literal**
>
> > [!danger] Error:
> >
> > ```javascript
> > function makeUser() {
> >   return {
> >     name: "John",
> >     ref: this,
> >   };
> > }
> >
> > let user = makeUser();
> >
> > alert(user.ref.name); // Error: Cannot read property 'name' of undefined
> > ```
> >
> > - the value of `this` inside `makeUser()` is `undefined`, because it's called as a _function_, **_not as a method with "dot" syntax._**
> > - value of `this` is one for the whole function, **code blocks and object literals** **_do not affect it_**.
> > - `ref: this` takes current `this` of the function
> >
> > ```javascript
> > function makeUser() {
> >   return this; // this time there's no object literal
> > }
> >
> > alert(makeUser().name); // Error: Cannot read property 'name' of undefined
> > ```
>
> > [!done] Working:
> > This works because `user.ref()` is a method. And the value of `this` is set to the object **before dot `.`**
> >
> > ```javascript
> > function makeUser() {
> >   return {
> >     name: "John",
> >     ref() {
> >       return this;
> >     },
> >   };
> > }
> >
> > let user = makeUser();
> >
> > alert(user.ref().name); //John
> > ```

> [!example] Calculator
> Object `calculator` with Three methods: `read()`, `sum()` and `mul()`.
>
> ```javascript
> let calculator = {
>   sum() {
>     return this.a + this.b;
>   },
>
>   mul() {
>     return this.a * this.b;
>   },
>
>   read() {
>     this.a = +prompt("a?", 0);
>     this.b = +prompt("b?", 0);
>   },
> };
>
> calculator.read();
> alert(calculator.sum());
> alert(calculator.mul());
> ```
>
> > [!danger]- My attempt:
> >
> > ```javascript
> > let red = {}
> >
> > let calculator = {
> > 	read() {
> > 		let first = prompt("Enter first number:");
> > 		let second = prompt("Enter second number:");
> >
> > 		red.a = first;
> > 		red.b = second;
> > 	},
> > 	sum() {
> > 		let summ = Number(red.a) + Number(red.b);
> > 		return summ;
> > 	}.
> > 	mul() {
> > 		let mull = (red.a) * (red.b);
> > 		return mull;
> > 	}
> > };
> >
> > calculator.read();
> > console.log( calculator.sum() );
> > console.log( calculator.mul() );
> > ```

> [!example] Ladder
>
> ```javascript
> let ladder = {
>   step: 0,
>   up() {
>     this.step++;
>     return this;
>   },
>   down() {
>     this.step--;
>     return this;
>   },
>   showStep() {
>     alert(this.step);
>     return this;
>   },
> };
>
> ladder.up().up().down().showStep().down().showStep(); // shows 1 then 0
> ```
>
> > [!danger]- My attempt:
> >
> > ```javascript
> > let ladder = {
> >   step: 0,
> >   up() {
> >     this.step++;
> >     return Object.assign({}, this);
> >   },
> >   down() {
> >     this.step--;
> >     return Object.assign({}, this);
> >   },
> >   showStep: function () {
> >     console.log(this.step);
> >     return Object.assign({}, this);
> >   },
> > };
> >
> > ladder.up().up().down().showStep().down().showStep();
> > ```
