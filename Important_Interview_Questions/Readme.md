This document contains a list of commonly asked React.js interview questions. Click on a question to jump to the answer.

## Table of Contents

1. [What is React?](#1-what-is-react)
2. [What are components in React?](#2-what-are-components-in-react)
3. [What is JSX?](#3-what-is-jsx)
4. [What is the virtual DOM?](#4-what-is-the-virtual-dom)
5. [What are props?](#5-what-are-props)
6. [What is state in React?](#6-what-is-state-in-react)
7. [How do you handle events in React?](#7-how-do-you-handle-events-in-react)
8. [What are hooks in React?](#8-what-are-hooks-in-react)
9. [What is the purpose of `useEffect`?](#9-what-is-the-purpose-of-useeffect)
10. [What is context in React?](#10-what-is-context-in-react)
11. [How do you manage state in large applications?](#11-how-do-you-manage-state-in-large-applications)
12. [What are higher-order components (HOCs)?](#12-what-are-higher-order-components-hocs)
13. [What are render props?](#13-what-are-render-props)
14. [What is code splitting?](#14-what-is-code-splitting)
15. [How can you optimize performance in a React app?](#15-how-can-you-optimize-performance-in-a-react-app)
16. [What are some common performance issues in React?](#16-what-are-some-common-performance-issues-in-react)
17. [How do you handle forms in React?](#17-how-do-you-handle-forms-in-react)
18. [What is the difference between controlled and uncontrolled components?](#18-what-is-the-difference-between-controlled-and-uncontrolled-components)
19. [How do you test React components?](#19-how-do-you-test-react-components)
20. [What are some common debugging techniques in React?](#20-what-are-some-common-debugging-techniques-in-react)
21. [What are error boundaries?](#21-what-are-error-boundaries)
22. [How do you implement routing in a React app?](#22-how-do-you-implement-routing-in-a-react-app)
23. [What is the significance of keys in lists?](#23-what-is-the-significance-of-keys-in-lists)
24. [How do you perform API calls in React?](#24-how-do-you-perform-api-calls-in-react)
25. [What are some lifecycle methods in React?](#25-what-are-some-lifecycle-methods-in-react)

---

## Answers

### 1. What is React?
React is an open-source JavaScript library used for building user interfaces, especially single-page applications. It was developed by Facebook and is maintained by Facebook along with a large community of developers. React is component-based, meaning it allows developers to build encapsulated components that manage their own state, then compose them to create complex UIs.

Key features of React include:

1. **Component-Based Architecture**: React allows you to build reusable UI components that can manage their own state.
2. **JSX (JavaScript XML)**: React uses JSX, a syntax extension of JavaScript, which allows HTML to be written within JavaScript code. This makes it easier to visualize the user interface structure.
3. **Virtual DOM**: React uses a virtual DOM to optimize rendering by updating only the changed parts of the real DOM, improving performance.
4. **One-Way Data Flow**: React follows unidirectional data flow, making the code more predictable and easier to debug.
5. **State and Props**: Components in React can have internal state and receive data through props (properties), enabling dynamic and interactive UIs.

React is widely used for building modern, fast, and responsive web applications.

[Back to top](#table-of-contents)

### 2. What are components in React?
In React, components are the building blocks of the user interface. They allow you to break down complex UIs into small, reusable, and independent pieces. Each component represents a part of the UI and can be a class or a function that returns a React element (JSX).

### Types of Components:

1. **Functional Components**:
   - These are JavaScript functions that accept `props` as arguments and return JSX (the UI).
   - Since React 16.8, with the introduction of **React Hooks**, functional components can also manage state and handle lifecycle events.
   - Example:
     ```jsx
     function Greeting(props) {
       return <h1>Hello, {props.name}!</h1>;
     }
     ```

2. **Class Components**:
   - These are ES6 classes that extend `React.Component` and have access to lifecycle methods and state management.
   - Example:
     ```jsx
     class Greeting extends React.Component {
       render() {
         return <h1>Hello, {this.props.name}!</h1>;
       }
     }
     ```

### Component Concepts:

- **Props**: Short for "properties," these are inputs passed to a component. Props are immutable and allow data to flow from parent components to child components.
- **State**: Components can have internal state, which is mutable and can change over time. When the state changes, the component re-renders to reflect the new state.
- **Lifecycle Methods**: Available in class components, these are methods that allow you to hook into different stages of a component’s lifecycle, such as when it mounts, updates, or unmounts. Examples include `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.

### Example of a Functional Component with Hooks:
```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

### Benefits of Components:
- **Reusability**: Components can be reused across different parts of the application, which helps maintain consistency.
- **Separation of Concerns**: Components encapsulate logic and UI, allowing developers to focus on specific parts of the UI without affecting other areas.
- **Modularity**: Components allow for modular development, where large UIs can be broken down into smaller, manageable pieces.

In short, components are the fundamental concept in React for structuring and organizing the user interface.

[Back to top](#table-of-contents)

### 3. What is JSX?
JSX (JavaScript XML) is a syntax extension for JavaScript that allows you to write HTML-like code within your JavaScript files. It is used in React to describe the structure of the UI, making it easier to create and visualize the component structure.

### Key Features of JSX:

1. **HTML-like Syntax**: JSX allows you to write code that looks like HTML, but it's actually JavaScript. This makes it more intuitive to define the structure of the UI inside React components.
   - Example:
     ```jsx
     const element = <h1>Hello, world!</h1>;
     ```

2. **JavaScript in JSX**: You can embed JavaScript expressions inside JSX by using curly braces `{}`.
   - Example:
     ```jsx
     const name = "Shweta";
     const element = <h1>Hello, {name}!</h1>;
     ```

3. **JSX Transpilation**: JSX is not valid JavaScript by itself. Under the hood, it is transpiled to `React.createElement()` calls using a tool like Babel. This function creates React elements that the browser can understand.
   - For instance, the JSX:
     ```jsx
     const element = <h1>Hello, world!</h1>;
     ```
     gets transpiled to:
     ```javascript
     const element = React.createElement('h1', null, 'Hello, world!');
     ```

4. **JSX with Components**: You can use JSX to nest components, making the code more readable and maintainable.
   - Example:
     ```jsx
     function Welcome(props) {
       return <h1>Hello, {props.name}</h1>;
     }

     const element = <Welcome name="Shweta" />;
     ```

5. **Attributes in JSX**: You can pass attributes to JSX elements just like in HTML. In React, they are referred to as "props" and must follow the camelCase convention for attributes like `className`, `onClick`, etc.
   - Example:
     ```jsx
     const button = <button className="btn" onClick={handleClick}>Click Me</button>;
     ```

6. **Fragment Syntax**: You can use fragments (`<></>`) in JSX to group multiple elements without adding an extra wrapper element to the DOM.
   - Example:
     ```jsx
     return (
       <>
         <h1>Heading</h1>
         <p>Some text</p>
       </>
     );
     ```

### Why Use JSX?
- **Readability**: JSX allows you to write HTML-like syntax directly in JavaScript, which makes it easier to read and understand the UI structure.
- **Combines Markup with Logic**: JSX allows you to integrate JavaScript logic into the UI code, making it more powerful and flexible.
- **React Optimized**: JSX is specifically designed for React, making it the preferred choice for building components and UIs.

In summary, JSX is a syntax that looks like HTML but works within JavaScript, enabling developers to create more readable and dynamic UIs using React.

[Back to top](#table-of-contents)

### 4. What is the virtual DOM?
The **Virtual DOM (Document Object Model)** is a lightweight, in-memory representation of the real DOM that React uses to optimize updates to the user interface. Instead of directly interacting with the real DOM, which is slow and expensive in terms of performance, React uses the virtual DOM to make updates more efficient.

### How the Virtual DOM Works:

1. **Initial Rendering**: When a React component is first rendered, a virtual DOM is created as a virtual copy of the real DOM. This virtual DOM is a JavaScript object that mimics the structure of the actual DOM.

2. **Component Re-rendering**: When there’s a change in the state or props of a component, React creates a new virtual DOM tree to represent the updated UI. However, it doesn’t immediately update the real DOM.

3. **Diffing Algorithm**: React compares the new virtual DOM with the previous one using a process called **reconciliation**. It identifies what has changed (the "diff") between the two versions of the virtual DOM.

4. **Batching Updates**: Once React knows what has changed, it updates only the parts of the real DOM that are necessary. This selective updating ensures that only the components or elements that actually changed are re-rendered, avoiding unnecessary updates.

5. **Efficient Updates**: The virtual DOM updates in memory are much faster than manipulating the actual DOM because JavaScript operations are generally faster than direct DOM operations.

### Benefits of the Virtual DOM:

1. **Performance Optimization**: Manipulating the real DOM can be slow because browsers need to repaint and reflow elements. The virtual DOM minimizes these operations by only applying changes that are absolutely necessary.

2. **Efficient Re-renders**: React updates only the changed parts of the DOM instead of re-rendering the entire page, making it more efficient, especially in complex applications with many UI updates.

3. **Declarative UI**: React allows developers to write UI updates in a declarative way, meaning they only describe what the UI should look like at any point in time, and React efficiently handles the rendering behind the scenes using the virtual DOM.

### Example of Virtual DOM in Action:
Consider a simple React app where a counter increases each time a button is clicked.

```jsx
function Counter() {
  const [count, setCount] = React.useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}
```

- When the button is clicked, React creates a new virtual DOM where only the text inside the `<p>` element has changed.
- React compares the new virtual DOM with the old one, detects that the `<p>` element needs to be updated, and only modifies that specific element in the real DOM.

### Why the Virtual DOM Matters:
- **Faster UI Updates**: Because the virtual DOM reduces the number of interactions with the real DOM, UI updates are faster and smoother, enhancing performance.
- **Improved Developer Experience**: The virtual DOM allows developers to write cleaner, more declarative code without worrying about manually updating the DOM.

In summary, the virtual DOM is a key concept in React that optimizes performance by ensuring that only the necessary changes are applied to the real DOM, improving the efficiency of UI updates.

[Back to top](#table-of-contents)

### 5. What are props?
**Props** in React are inputs passed from a parent component to a child component. They allow components to receive dynamic data and be reusable. Props are **immutable** (read-only) and enable a one-way data flow, ensuring that data moves from parent to child. Components can access props to display or use the data, but they cannot modify them.

In essence, props make React components flexible and customizable, allowing them to work with different inputs.

[Back to top](#table-of-contents)

### 6. What is state in React?
State in React is a built-in object that stores dynamic data for a component. Unlike props, which are passed from parent to child and are immutable, state is internal to the component and can change over time, allowing the component to react to user interactions, network requests, or other events.

Key Features of State:
Mutable: State can be changed within a component using the setState method (for class components) or the useState hook (for functional components).

Triggers Re-rendering: When the state changes, React re-renders the component to reflect the updated data on the UI.

Local to Component: State is local to a component and cannot be accessed by other components unless passed down via props.

[Back to top](#table-of-contents)

### 7. How do you handle events in React?
In React, handling events is similar to handling DOM events in plain JavaScript, but with some key differences. React uses **synthetic events**, which are cross-browser wrappers around native events, providing a consistent API.

### Steps to Handle Events in React:

1. **Attach Event Handlers**: Use camelCase syntax for event names, unlike in HTML where event handlers are lowercase (e.g., `onClick` instead of `onclick`).
2. **Pass Event Handler Functions**: You pass a function as the event handler rather than a string, as you would in traditional HTML.

### Example of Handling Events:

#### Functional Component with `useState`:
```jsx
import React, { useState } from 'react';

function ClickButton() {
  const [count, setCount] = useState(0);

  // Event handler function
  const handleClick = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={handleClick}>Click me</button>
    </div>
  );
}
```

#### Class Component:
```jsx
class ClickButton extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };

    // Bind the event handler
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    this.setState({ count: this.state.count + 1 });
  }

  render() {
    return (
      <div>
        <p>You clicked {this.state.count} times</p>
        <button onClick={this.handleClick}>Click me</button>
      </div>
    );
  }
}
```

### Event Handling Features:

1. **Passing Arguments**: If you need to pass arguments to the event handler, you can use an inline arrow function.
   ```jsx
   <button onClick={() => handleClick(id)}>Click me</button>
   ```

2. **Event Object**: React automatically passes the event object to the handler. You can access the event properties (e.g., `event.target`) just like in native DOM events.
   ```jsx
   function handleClick(event) {
     console.log(event.target); // Logs the clicked element
   }
   ```

3. **Prevent Default Behavior**: You can prevent the default behavior by calling `event.preventDefault()` inside the event handler.
   ```jsx
   function handleSubmit(event) {
     event.preventDefault();
     console.log('Form submitted!');
   }
   ```

### Common Events in React:
- `onClick` – triggered when an element is clicked.
- `onChange` – triggered when an input changes.
- `onSubmit` – triggered when a form is submitted.
- `onMouseEnter`, `onMouseLeave` – triggered on mouse hover events.
- `onKeyPress`, `onKeyDown`, `onKeyUp` – triggered on keyboard events.

### In Short:
- React handles events using **camelCase** syntax and **functions** as handlers.
- Event handling is similar to JavaScript but provides cross-browser compatibility through **synthetic events**.
- Event handlers receive an event object and can manipulate it to control behavior (e.g., `event.preventDefault()`).

[Back to top](#table-of-contents)

### 8. What are hooks in React?
**Hooks** in React are special functions that allow you to use state and other React features in functional components, without needing to write class components. Introduced in React 16.8, hooks provide a more functional approach to managing state, side effects, and component lifecycle.

### Commonly Used Hooks:

1. **`useState`**: Allows you to add state to functional components.
   - Example:
     ```jsx
     import React, { useState } from 'react';

     function Counter() {
       const [count, setCount] = useState(0);

       return (
         <div>
           <p>You clicked {count} times</p>
           <button onClick={() => setCount(count + 1)}>Click me</button>
         </div>
       );
     }
     ```

2. **`useEffect`**: Handles side effects in functional components (similar to lifecycle methods in class components, like `componentDidMount` and `componentDidUpdate`).
   - Example:
     ```jsx
     import React, { useEffect, useState } from 'react';

     function Timer() {
       const [seconds, setSeconds] = useState(0);

       useEffect(() => {
         const interval = setInterval(() => {
           setSeconds((prev) => prev + 1);
         }, 1000);
         
         // Cleanup interval on component unmount
         return () => clearInterval(interval);
       }, []);

       return <p>{seconds} seconds have passed.</p>;
     }
     ```

3. **`useContext`**: Allows you to use context to manage global state without prop drilling.
   - Example:
     ```jsx
     const UserContext = React.createContext();

     function User() {
       const user = useContext(UserContext);
       return <p>{user.name}</p>;
     }

     function App() {
       const user = { name: "Shweta" };
       return (
         <UserContext.Provider value={user}>
           <User />
         </UserContext.Provider>
       );
     }
     ```

4. **`useReducer`**: A more advanced hook for handling complex state logic, similar to `redux`.
   - Example:
     ```jsx
     const initialState = { count: 0 };

     function reducer(state, action) {
       switch (action.type) {
         case 'increment':
           return { count: state.count + 1 };
         case 'decrement':
           return { count: state.count - 1 };
         default:
           return state;
       }
     }

     function Counter() {
       const [state, dispatch] = useReducer(reducer, initialState);

       return (
         <div>
           <p>Count: {state.count}</p>
           <button onClick={() => dispatch({ type: 'increment' })}>+</button>
           <button onClick={() => dispatch({ type: 'decrement' })}>-</button>
         </div>
       );
     }
     ```

5. **`useRef`**: Provides a way to access DOM elements directly or persist values across renders without causing a re-render.
   - Example:
     ```jsx
     import React, { useRef } from 'react';

     function FocusInput() {
       const inputRef = useRef(null);

       const focusInput = () => {
         inputRef.current.focus();
       };

       return (
         <div>
           <input ref={inputRef} type="text" />
           <button onClick={focusInput}>Focus Input</button>
         </div>
       );
     }
     ```

### Key Benefits of Hooks:
1. **Simpler Code**: Hooks eliminate the need for class components, reducing the complexity of code while retaining powerful functionality.
2. **Reusability**: Hooks enable you to extract and reuse logic (through custom hooks), making your components more modular.
3. **Functional Components**: Hooks allow functional components to manage state and side effects, which were previously only possible with class components.

### In Short:
- **Hooks** enable state and other React features in **functional components**.
- Common hooks include `useState`, `useEffect`, `useContext`, `useReducer`, and `useRef`.
- Hooks simplify code, enhance reusability, and make managing state and lifecycle easier in functional components.

[Back to top](#table-of-contents)

### 9. What is the purpose of `useEffect`?
The purpose of `**useEffect**` in React is to manage **side effects** in functional components. Side effects are anything that affects something outside the scope of the component, such as data fetching, manually updating the DOM, setting up subscriptions, or timers. 

In class components, these side effects were handled using lifecycle methods like `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`. The `useEffect` hook simplifies this by combining all of these behaviors into one function.

### Key Use Cases for `useEffect`:
1. **Data fetching**: Fetching data from APIs after the component renders.
2. **Subscriptions**: Setting up subscriptions like WebSockets or event listeners.
3. **Timers**: Setting and clearing intervals or timeouts.
4. **DOM manipulation**: Manually updating the DOM, such as updating the document title.

### How `useEffect` Works:
- `useEffect` runs after the component renders, ensuring the DOM is updated before any side effects occur.
- By default, it runs after every render, but you can control this behavior using the **dependency array**.

### Syntax:
```jsx
useEffect(() => {
  // Your side effect code here

  // Optionally return a cleanup function to be called when the component unmounts
  return () => {
    // Cleanup code here
  };
}, [dependencies]); // Optional dependency array
```

### Example 1: Data Fetching with `useEffect`:
```jsx
import React, { useEffect, useState } from 'react';

function DataFetchingComponent() {
  const [data, setData] = useState(null);

  useEffect(() => {
    // Fetch data after component renders
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => setData(data));
  }, []); // Empty dependency array ensures the effect runs only once, like componentDidMount

  return <div>{data ? <p>{data.name}</p> : <p>Loading...</p>}</div>;
}
```

### Example 2: Timer with Cleanup:
```jsx
import React, { useState, useEffect } from 'react';

function Timer() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    const timer = setInterval(() => {
      setCount(prevCount => prevCount + 1);
    }, 1000);

    // Cleanup when the component unmounts
    return () => clearInterval(timer);
  }, []); // Runs only once, setting up the timer on mount

  return <p>Timer: {count}</p>;
}
```

### Dependency Array:
- The second argument to `useEffect` is the **dependency array**, which controls when the effect runs.
  - **Empty array (`[]`)**: Runs the effect only once after the initial render, like `componentDidMount`.
  - **Specific dependencies**: Runs the effect only when the specified dependencies change.
  - **No array**: Runs the effect after every render, which can lead to performance issues if not used carefully.

### Cleanup:
- `useEffect` can return a **cleanup function** that runs when the component unmounts or before re-running the effect. This is useful for cleaning up subscriptions, timers, or other side effects.
  
### In Short:
- `useEffect` manages **side effects** in functional components.
- It handles tasks like data fetching, subscriptions, and DOM updates after rendering.
- You can control when it runs using the **dependency array** and clean up resources using the **cleanup function**.

[Back to top](#table-of-contents)

### 10. What is context in React?
Context provides a way to pass data through the component tree without having to pass props manually at every level.

[Back to top](#table-of-contents)

### 11. How do you manage state in large applications?
For large applications, you can use state management libraries like Redux, MobX, or React's Context API combined with `useReducer`.

[Back to top](#table-of-contents)

### 12. What are higher-order components (HOCs)?
Higher-Order Components (HOCs) are a pattern in React for reusing component logic. An HOC is a function that takes a component and returns a new component with enhanced or additional functionality. This pattern is useful for code reuse, separation of concerns, and managing cross-cutting concerns such as authentication, data fetching, or logging.

Key Characteristics of HOCs:
Enhancement of Components: HOCs are used to wrap a component and provide it with additional props or behavior.

Function Signature: An HOC is a function that accepts a component and returns a new component.

jsx
Copy code
const withEnhancements = (WrappedComponent) => {
  return class extends React.Component {
    // Additional functionality or props
    render() {
      return <WrappedComponent {...this.props} />;
    }
  };
};


[Back to top](#table-of-contents)

### 13. What are render props?
Render props is a technique for sharing code between React components using a prop whose value is a function.

[Back to top](#table-of-contents)

### 14. What is code splitting?
Code splitting allows you to split your code into smaller bundles, which can be loaded on-demand. This can improve the performance of your React application.

[Back to top](#table-of-contents)

### 15. How can you optimize performance in a React app?
You can optimize performance by using techniques like memoization (`React.memo`), lazy loading, and avoiding unnecessary re-renders.

[Back to top](#table-of-contents)

### 16. What are some common performance issues in React?
Common issues include unnecessary re-renders, inefficient code updates, large bundle sizes, and poor state management.

[Back to top](#table-of-contents)

### 17. How do you handle forms in React?
Forms in React are typically handled using controlled components, where form data is managed by the state, or uncontrolled components with refs.

[Back to top](#table-of-contents)

### 18. What is the difference between controlled and uncontrolled components?
In controlled components, form data is managed by React state, while in uncontrolled components, the form data is handled by the DOM.

[Back to top](#table-of-contents)

### 19. How do you test React components?
You can test React components using libraries like Jest, React Testing Library, and Enzyme for unit and integration testing.

[Back to top](#table-of-contents)

### 20. What are some common debugging techniques in React?
Common techniques include using React Developer Tools, logging with `console.log()`, and leveraging error boundaries.

[Back to top](#table-of-contents)

### 21. What are error boundaries?
Error boundaries are components that catch JavaScript errors in their child component tree and display a fallback UI instead of crashing the app.

[Back to top](#table-of-contents)

### 22. How do you implement routing in a React app?
Routing in React is typically handled using the `react-router-dom` library, which allows you to define routes for different components.

[Back to top](#table-of-contents)

### 23. What is the significance of keys in lists?
Keys help React identify which items have changed, are added, or removed. Keys should be unique and consistent.

[Back to top](#table-of-contents)

### 24. How do you perform API calls in React?
You can perform API calls using `fetch`, `axios`, or other HTTP clients, usually within `useEffect` to handle side effects.

[Back to top](#table-of-contents)

### 25. What are some lifecycle methods in React?
Lifecycle methods in React class components include `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`. In functional components, these can be handled with the `useEffect` hook.

[Back to top](#table-of-contents)
