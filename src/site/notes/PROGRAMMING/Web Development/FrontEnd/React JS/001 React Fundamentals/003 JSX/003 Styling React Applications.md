---
{"dg-publish":true,"permalink":"/programming/web-development/front-end/react-js/001-react-fundamentals/003-jsx/003-styling-react-applications/","tags":["programming","ReactJS","javascript","jsx"],"created":"2024-12-28T22:25:08.060+08:00"}
---

---

__React doesn't care about styling.__
### Inline CSS:
#### Inline:
```js
function Header() {
	return (
		<h1 style={{ color: "red", fontSize: "48px", textTransform: "uppercase" }}>
			Fast React Pizza Co. 
		</h1>
	); 
```

#### Variable:
```js
function Header() {
	const style = { color: "red", fontSize: "48px", textTransform: "uppercase" };

	return (
		<h1 style={style}>
			Fast React Pizza Co. 
		</h1>
	); 
```

> [!caution] Downside:
> When the application became bigger, It can get out of hand and can be a lot of work.


### External CSS
##### Importing CSS File:
```js
import React from "react";
import ReactDOM from "react-dom/client";

import "./index.css";
```

##### `className` instead of `class`
because `class` is a ___reserved word___ in _JavaScript_ already.
```js
function App() {
  return (
    <div className="container">
      <Header />
      <Menu />
      <Footer />
    </div>
  );
}
```
- We'd get this ___ERROR___, If we use `class`
	- ![Pasted image 20241228232814.png](/img/user/Misc/attachments/Pasted%20image%2020241228232814.png)
### Current Example Code:
```js
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";

const pizzaData = [
  {
    name: "Focaccia",
    ingredients: "Bread with italian olive oil and rosemary",
    price: 6,
    photoName: "pizzas/focaccia.jpg",
    soldOut: false,
  },
  {
    name: "Pizza Margherita",
    ingredients: "Tomato and mozarella",
    price: 10,
    photoName: "pizzas/margherita.jpg",
    soldOut: false,
  },
  {
    name: "Pizza Spinaci",
    ingredients: "Tomato, mozarella, spinach, and ricotta cheese",
    price: 12,
    photoName: "pizzas/spinaci.jpg",
    soldOut: false,
  },
  {
    name: "Pizza Funghi",
    ingredients: "Tomato, mozarella, mushrooms, and onion",
    price: 12,
    photoName: "pizzas/funghi.jpg",
    soldOut: false,
  },
  {
    name: "Pizza Salamino",
    ingredients: "Tomato, mozarella, and pepperoni",
    price: 15,
    photoName: "pizzas/salamino.jpg",
    soldOut: true,
  },
  {
    name: "Pizza Prosciutto",
    ingredients: "Tomato, mozarella, ham, aragula, and burrata cheese",
    price: 18,
    photoName: "pizzas/prosciutto.jpg",
    soldOut: false,
  },
];

function App() {
  return (
    <div class="container">
      <Header />
      <Menu />
      <Footer />
    </div>
  );
}

function Header() {
  //   const style = { color: "red", fontSize: "48px", textTransform: "uppercase" };
  const style = {};

  return (
    <header className="header">
      <h1 style={style}>Fast React Pizza Co.</h1>
    </header>
  );
}

function Menu() {
  return (
    <main className="menu">
      <h2>Our Menu</h2>
      <Pizza />
      <Pizza />
      <Pizza />
    </main>
  );
}

function Footer() {
  const hour = new Date().getHours();
  const openHour = 12;
  const closeHour = 22;
  const isOpen = hour >= openHour && hour <= closeHour;
  console.log(isOpen);

  //   if (hour >= openHour && hour <= closeHour) alert("We're currently open!");
  //   else alert("Sorry we're closed");

  return (
    <footer className="footer">
      {new Date().toLocaleTimeString()}. We're currently open!
    </footer>
  );

  //   return React.createElement("footer", null, "We're currently open!");
}

function Pizza() {
  return (
    <div>
      <img src="pizzas/spinaci.jpg" alt="Pizza Spinaci" />
      <h3>Pizza Spinaci</h3>
      <p>Tomato, mozarella, mushrooms, and onion</p>
    </div>
  );
}

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

```
