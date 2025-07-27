# React & JavaScript Interview Questions

## 🧠 React Core Concepts

1. **Why is React called a Single Page Application (SPA)?**
2. **How does React update views without full page reloads?**
3. **Write a custom hook for debounce function.**
   *Use case: In a search input, delay the API call until the user stops typing for a set time (like 500 ms).*
4. **Throttling vs Debounce (with examples)**

   * **Debounce**: Wait for a pause before firing a function. (✏️ *e.g. search suggestions*)
   * **Throttle**: Allow a function to run at most once in a fixed time window. (🖱️ *e.g. scroll/resize event handler*)
5. **Why is a `key` required in React lists?**
   *Keys help React identify which items changed, are added, or removed during reconciliation.*
6. **Why is using `index` as a key not recommended?**
7. **What is a Promise and why do we use it?**
8. **How do you handle errors in Promises without `try/catch`, `async/await`, or `.catch()`?**
9. **What is reconciliation in React?**
10. **Output‑based JavaScript questions**
    *Closures, scope, and hoisting fundamentals.*
11. **Callback questions**
    *How callbacks work in async flows and their value even with Promises/async-await.*
12. **React Hooks (useState, etc.)**
    *How `useState` works and why hooks are preferred in function components.*
13. **Form Libraries in React**
    *Formik vs React Hook Form, and how they simplify validation/state handling.*

---

## ⚙️ JavaScript Fundamentals

1. **Why do closures exist in JavaScript?**
2. **How does the event loop actually work?**
3. **What's the difference between `null` and `undefined`?**
4. **Why does `this` behave differently in arrow functions?**
5. **What happens when you compare objects with `==` vs `===`?**
6. **Why can you call a function before it's declared?**
7. **What's the difference between `call`, `apply`, and `bind`?**

---

## ⚛️ React Internals

8. **Why does React need a virtual DOM?**
9. **When does React batch state updates?**
10. **Why do we need keys in lists?**
11. **What's the difference between `useEffect` and `useLayoutEffect`?**
12. **How does React decide when to re-render?**
13. **Why might `useState` not update immediately?**
14. **What happens during React's reconciliation process?**

---

## 🏗️ Architectural Decisions

15. **Why did you choose Redux over Context API?**
16. **When would you use a CDN vs hosting assets locally?**
17. **Why implement lazy loading for images?**
18. **What's the difference between SSR and CSR?**
19. **Why choose TypeScript over vanilla JavaScript?**
20. **How do you decide between REST and GraphQL?**
