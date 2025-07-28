# React & JavaScript Interview Questions

## 🧠 React Core Concepts

### 1. **Why is React called a Single Page Application (SPA)?**
  Ans- React is called a Single Page Application (SPA) framework because it dynamically updates the content on a single HTML page withoutreloading the entire page from the server.

In a traditional multi-page application (MPA), every time a user navigates to a new page, the browser requests a new HTML file from the server — this causes a full page reload.

In contrast, React loads a single index.html file once, and then uses JavaScript (specifically React's Virtual DOM and client-side routing) to update just the parts of the page that change. This makes the application faster and more responsive.

For example, when using React Router, the URL changes, but React intercepts that change and renders the appropriate component instead of fetching a new HTML page from the server. This creates the illusion of multiple pages, but under the hood, it's still one page — hence, 'Single Page Application'.

So in summary, React enables SPA behavior by:

Loading a single HTML file.

Using client-side routing.

Dynamically updating content without full reloads.
This improves performance, user experience, and feels more like a native app."**

### 2. **How does React update views without full page reloads?**
Ans- It compares the current Virtual DOM with the previous one (diffing), calculates the minimal changes, and updates only those parts in the real DOM — all done dynamically via JavaScript without refreshing the entire page.
### 3. **What is diffing algorithm in react js**
Ans- Diffing in React is the process of comparing the new Virtual DOM with the previous Virtual DOM to find the smallest set of changes needed to update the real DOM efficiently.
React uses this process to:
Detect what has changed.
Avoid re-rendering the entire UI.
Only update parts of the DOM that actually changed.

### 4. **Write a custom hook for debounce function.**
   *Use case: In a search input, delay the API call until the user stops typing for a set time (like 500 ms).*
### 5. **Throttling vs Debounce (with examples)**

   * **Debounce**: Wait for a pause before firing a function. (✏️ *e.g. search suggestions*)
   * **Throttle**: Allow a function to run at most once in a fixed time window. (🖱️ *e.g. scroll/resize event handler*)
### 6. **Why is a `key` required in React lists?**
   *Keys help React identify which items changed, are added, or removed during reconciliation.*
### 7. **Why is using `index` as a key not recommended?**
### 8. **What is a Promise and why do we use it?**
### 9. **How do you handle errors in Promises without `try/catch`, `async/await`, or `.catch()`?**
### 10. **What is reconciliation in React?**
### 11. **Output‑based JavaScript questions**
    *Closures, scope, and hoisting fundamentals.*
### 12. **Callback questions**
    *How callbacks work in async flows and their value even with Promises/async-await.*
### 13. **React Hooks (useState, etc.)**
    *How `useState` works and why hooks are preferred in function components.*
### 14. **Form Libraries in React**
    *Formik vs React Hook Form, and how they simplify validation/state handling.*

---

## ⚙️ JavaScript Fundamentals

### 1. **Why do closures exist in JavaScript?**
### 2. **How does the event loop actually work?**
### 3. **What's the difference between `null` and `undefined`?**
### 4. **Why does `this` behave differently in arrow functions?**
### 5. **What happens when you compare objects with `==` vs `===`?**
### 6. **Why can you call a function before it's declared?**
### 7. **What's the difference between `call`, `apply`, and `bind`?**

---

## ⚛️ React Internals

### 8. **Why does React need a virtual DOM?**
### 9. **When does React batch state updates?**
### 10. **Why do we need keys in lists?**
### 11. **What's the difference between `useEffect` and `useLayoutEffect`?**
### 12. **How does React decide when to re-render?**
### 13. **Why might `useState` not update immediately?**
### 14. **What happens during React's reconciliation process?**

---

## 🏗️ Architectural Decisions

15. **Why did you choose Redux over Context API?**
16. **When would you use a CDN vs hosting assets locally?**
17. **Why implement lazy loading for images?**
18. **What's the difference between SSR and CSR?**
19. **Why choose TypeScript over vanilla JavaScript?**
20. **How do you decide between REST and GraphQL?**

---

## 🧪 Coding Problems

### 👩‍💻 Beginner to Intermediate Scenarios

1. Display dynamic HTML content in React
2. Pass data from Parent ➡️ Child
3. Call Parent method from Child
4. Access the DOM using useRef
5. Bind arrays/objects to Dropdowns
6. Create Lazy Loaded Component
7. Show user input in another Textbox
8. Loop through Arrays/Objects
9. Conditional Rendering 🟢🔴
10. Change styles based on conditions
11. Show/Hide data conditionally
12. Bind array to Radio Buttons
13. Display selected radio value
14. Call method on initial render
15. Loop through object keys & values
16. Re-render component on value change
17. Trigger function on every render
18. Add items to useState array
19. Create a Search Filter
20. Counter using useState
21. Counter using useReducer

### 🧩 Advanced Component Scenarios

22. Control child textbox (focus/enable/disable) from Parent
23. Implement Debouncing
24. Fetch API data in component
25. Force Re-render without useState
26. Run method after state update or re-render
27. Show characters remaining in textarea using useRef
28. Dynamic dropdowns (e.g., State by Country)
29. Type check props with prop-types
30. Share data using Context API
31. Optimization using useMemo 💡
32. Optimization using useCallback 💡
33. Create an Error Boundary
34. Display selected dropdown value in textbox
35. Create a PureComponent
36. Controlled vs Uncontrolled components
37. Build a Custom Hook
38. Create a Popup using Portal
39. Class lifecycle hooks vs useEffect
40. Build a Pagination Component
41. Safeguard your React app (Security) 🔐
What security features should be taken while designing API's?
💠 What is API throttling?
💠 How to improve the performance in React Application?
💠 What is debouncing in React?
💠 What if in a react app we need to develop a feature of auto save the inputs of a form?
💠 Which react library is used to represent JSON data into charts, graphs, etc for better visualization and performance?
💠 If you have to inform the backend developers about some API's are failing how will you do that?
💠 Which tool is used to improve code standards in react application to show warnings for developers?
💠 What are the unit testing tools used in React Application?
💠 How do you handle API test case scenarios in React Application?
💠 Give me a estimation of completing a auto save functionality with unit testing including?
💠 Which cloud is used in your app development?
