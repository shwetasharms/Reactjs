
### ✅ 1. What is Automatic Batching?

Automatic batching means React combines multiple setState / state updates into a single re-render.

Example (React 18)
```
function App() {
  const [count, setCount] = React.useState(0);
  const [flag, setFlag] = React.useState(false);

  function handleClick() {
    setCount(c => c + 1);
    setFlag(f => !f);
  }

  return <button onClick={handleClick}>Click</button>;
}
```
👉 Both updates → 1 render only

❌ Before React 18

Batching worked only inside React event handlers

setTimeout(() => {
  setCount(c => c + 1);
  setFlag(f => !f);
}, 1000);

👉 React 17:

❌ 2 renders

👉 React 18:

✅ 1 render (automatic batching everywhere)

🧠 3. Why is it important?
Fewer renders → better performance
Avoid unnecessary DOM updates
Cleaner mental model
⚡ 4. How to disable batching?

Use flushSync when you need immediate update:

import { flushSync } from "react-dom";

flushSync(() => {
  setCount(c => c + 1);
});

👉 Forces synchronous render
