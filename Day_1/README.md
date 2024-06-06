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

```jsx
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

# How many ways are there to add React to a JavaScript project?

# What is Babel, and why is it essential these days?

# What is JSX?
