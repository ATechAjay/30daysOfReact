# Do you need React to build an app?

Not really, Any web application needs `HTML` to structure the content, `CSS` to style it, and `JavaScript` to make it interactive. These three technologies form the foundation of web development.

# Why are DOM operations the most expensive in web development?

Browsers were not originally designed for rich DOM manipulation like we see today; instead, they were created to display text content or documents.

Browsers are written in C++, but websites are created in JavaScript. JavaScript is a slower language that does not interact directly with hardware.

JavaScript needs another language to help it interact with hardware. For this, the browser uses `C++`.

The JavaScript engine, like V8, converts JavaScript code into low-level code using C++ so that the hardware can understand and act on it.

When I write code like `document.getElementById()`, the JavaScript engine converts this code into a low-level language so it can perform its task and communicate with the hardware.

Any DOM manipulation relies on some C++ methods or objects behind the scenes.

![Amir Khan from PK](https://akm-img-a-in.tosshub.com/indiatoday/images/story/201412/pknew-story_650_120714115207.jpg)

It's like the character in the movie `"P.K."` trying to communicate from one planet ("GOLA") to another, which slows down app performance.

This intercommunication between the two "planets" is the costliest aspect. That's why DOM manipulation is so expensive.

However, there is an option, React JS addresses this problem using the `virtual DOM`. I'll talk later about this.

# What is the difference between a traditional web app and a single-page app (SPA)?

**Traditional websites:**

The main purpose of traditional websites has historically been to display text content and link pages together.

When a user clicks on a link, the entire webpage is reloaded to display new content. This means that the server sends a new HTML page, which can lead to slower navigation and a less seamless user experience.

Each page load requires a new request to the server, which can result in longer wait times and a less dynamic user experience.

**Single-Page Applications (SPAs):**

SPAs provide a more dynamic and fluid user experience. When a user interacts with the app (e.g: clicking on a link), the address of the website may change, but the entire webpage does not reload.

SPAs update the content dynamically without requiring a full page reload. This is often achieved using JavaScript frameworks and libraries such as `React` and libraries like `react-router-dom` for managing navigation.

When new content is needed, SPAs can fetch data asynchronously from the server and update parts of the webpage as necessary. This reduces load times and provides a smoother user experience.

The result is a faster, more responsive application that behaves more like a desktop application, enhancing the overall user experience.

# What is React?

React is a JavaScript library for building user interfaces. It helps developers create interactive, dynamic web applications more easily. These are the key concepts of React:

1. **Declarative:** React makes it easy to build interactive UIs. You design a simple screen for your application, and React takes care of updating and rendering the right parts when your data changes.

2. **Component-Based:** React components are written in JavaScript. You build small, reusable components that manage their state. These components can be combined to create complex user interfaces.

# How does imperative and declarative code look like?

**Imperative code:**

Imperative programming is a style of programming where you explicitly describe the steps that the computer must take to perform a task. It involves giving a sequence of commands or instructions.

```js
// Imperative approach to adding items to a list
const list = document.getElementById("myList");
const newItem = document.createElement("li");
newItem.textContent = "This is list item";
list.appendChild(newItem);
```

In the above example, you manually create a new list item `<li>`, set its text content, and then append it to an existing list `<ul>` or `<ol>`. Each step of the process is explicitly defined.

**Declarative Code:**

Declarative programming is a style of programming where you describe what you want to achieve without explicitly listing the steps. You define the desired outcome, and the underlying system handles the details.

```js
// Declarative approach

// Other code goes here...
<div>
  <ul>
    {items.map((item, index) => (
      <li key={index}>{item}</li>
    ))}
  </ul>
  <button onClick={addItem}>Add Item</button>
</div>
```

In the above code, You don't manually manipulate the DOM; instead, you describe the desired UI structure and let React handle the rendering.

# What problems does React solve?

React helps developers create user interfaces more efficiently. One of the big problems it solves is making updates to web pages faster and smoother.

Normally, every time something changes on a web page, the browser has to update the DOM (Document Object Model), which can be slow and make the page feel less responsive. React uses a special system called the `Virtual DOM (VDOM)` to make this process better.

Here’s how it works:

- **Virtual Representation:** Instead of directly changing the real DOM, React creates a virtual copy of the DOM. This is a lightweight version of the actual DOM.

- **Efficient Updates:** When something changes, React updates the VDOM first. It compares the new VDOM with the old one to see what exactly has changed.

- **Minimized Changes:** After figuring out what’s different, React only updates those specific parts in the real DOM. This means fewer changes and less work for the browser.

By using the Virtual DOM, React reduces the number of direct updates to the real DOM. This makes web pages faster and more responsive, improving the user experience.

# How many ways are there to add React to a JavaScript project?

There are several ways to add React to your JavaScript project. Some of them are:

#### 1. Create React App (CRA)

A command-line tool that sets up a new React project with a lot of the configuration already done for you.

Run a single command in your terminal, and it creates a project with all the files and settings you need to start coding right away.

```shell
npx create-react-app my-app
```

#### 2. Vite

A modern build tool that provides a faster and leaner development experience for modern web projects.

Similar to CRA, you run a command in your terminal, and it sets up a React project. Vite is known for its speed and simplicity.

```shell
npm create vite@latest my-app
```

#### 3. CDN (Content Delivery Network)

A 3rd way to add React to your project is by including links to React libraries directly in your HTML file.

Add script tags in your HTML file to load [React from a CDN](https://legacy.reactjs.org/docs/cdn-links.html). This is great for small projects or adding React to an existing site without a build process.

```js
<script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
```

#### 3. Manual with NPM

Adding React to your project by manually installing React libraries using NPM (Node Package Manager).

You install `React` and `ReactDOM` using NPM commands and then import them into your JavaScript files.

```sh
npm install react react-dom
```

Then in your JavaScript file:

```js
import React from "react";
import ReactDOM from "react-dom";
```

Each method has its pros and cons depending on your project needs. CRA and Vite are great for quickly starting new projects.

# What is Babel, and why is it essential these days?

Babel is a tool known as a `transpiler`. It converts modern JavaScript code into older versions of JavaScript that web browsers can understand.

#### Why is Babel Essential?

1. **Browser Compatibility:**

Web browsers only understand standard HTML, CSS, and JavaScript. However, not all browsers support the latest JavaScript features and syntax.

Developers like to use new JavaScript features because they make coding easier and more efficient. But these new features might not work in all browsers, especially older ones.

2. **Babel as a Transpiler:**

Babel takes your modern JavaScript code and `transpiles` it, which means it converts it into an older version of JavaScript that all browsers can understand.

For example, If you write JavaScript code using ES6 features (like `let`, `const`, or arrow functions), Babel will convert it into ES5 code, which is compatible with most browsers.

```js
// Modern JavaScript (ES6)
const greet = () => {
  console.log("Hello, world!");
};

// Transpiled JavaScript (ES5)
var greet = function () {
  console.log("Hello, world!");
};
```

By using Babel, developers ensure that their web applications work consistently across all browsers, regardless of whether they support the latest JavaScript features.

Babel allows developers to use the latest and most powerful features of JavaScript today, without waiting for all browsers to catch up in support.

# What is JSX?

JSX stands for JavaScript XML. It's a syntax extension for JavaScript created by the React team that makes writing React components easier and more intuitive.

JSX looks like HTML but is JavaScript. It allows you to write HTML-like code within JavaScript.

The React team developed JSX to make it easier to create and visualize the structure of the UI components.

JSX is an extension of JavaScript syntax, meaning it adds some extra features to JavaScript to make writing UI elements simpler.

```js
const element = <h1>Hello, world!</h1>;
```

##### Rules of JSX

1. **Can't Return Multiple Elements:**

In JSX, you can't return multiple sibling elements without wrapping them in a single parent element. This is because JavaScript functions and expressions can only return one value. You can resolve this issue using an `array` or `React fragments`.

```js
// Using React Fragment
return (
  <>
    <h1>Title</h1>
    <p>Description</p>
  </>
);

// Using Array
return [<h1 key="1">Title</h1>, <p key="2">Description</p>];
```

2. **Attributes are Written in camelCase:**

In JSX, attribute names should be written in `camelCase`, just like JavaScript properties. For example, `class` becomes `className`, and `onclick` becomes `onClick`.

```js
// Other code goes here...
const element = (
  <button className="my-button" onClick={handleClick}>
    Click me
  </button>
);
```

3. **Self-Closing Tags:**

Tags that don't have children can be self-closed. For instance, `<img />` instead of `<img></img>`.

```js
// Should be self-closed
const image = <img src="image.jpg" alt="Example" />;
```

4. **JavaScript Expressions in JSX:**

You can embed JavaScript `expressions` in JSX by wrapping them in curly braces `{}`. This is useful for dynamic values.

```js
const name = "John";
const element = <h1>Hello, {name}!</h1>;
```
