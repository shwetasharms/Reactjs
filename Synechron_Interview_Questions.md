# Frontend Interview Questions — Synechron

## 🟢 Round 1 – JavaScript Fundamentals

<details>
<summary><strong>1. What is hoisting?</strong></summary>

Explain how JavaScript moves variable and function declarations to the top of their scope during compilation.

</details>

<details>
<summary><strong>2. What are closures?</strong></summary>

Explain lexical scoping and how functions retain access to variables from their outer scope.

</details>

<details>
<summary><strong>3. Explain prototypal inheritance.</strong></summary>

Describe how JavaScript objects inherit properties and methods through the prototype chain.

</details>

<details>
<summary><strong>4. Difference between shallow copy and deep copy?</strong></summary>

Compare copying references vs creating fully independent object copies.

</details>

<details>
<summary><strong>5. Explain debounce and throttle with examples.</strong></summary>

Discuss controlling function execution frequency for events like scrolling and searching.

</details>

<details>
<summary><strong>6. Difference between localStorage and sessionStorage?</strong></summary>

Compare persistence, lifecycle, storage limits, and use cases.

</details>

---

## 🟡 Round 2 – React Fundamentals

<details>
<summary><strong>1. Explain React Fiber.</strong></summary>

Discuss React's reconciliation engine and how it enables interruptible rendering.

</details>

<details>
<summary><strong>2. Explain lazy loading.</strong></summary>

Describe loading components only when needed to improve performance.

</details>

<details>
<summary><strong>3. What are stale closures in React?</strong></summary>

Explain stale state references inside hooks and callbacks.

</details>

<details>
<summary><strong>4. Explain optimistic UI updates.</strong></summary>

Describe updating the UI before server confirmation to improve perceived performance.

</details>

<details>
<summary><strong>5. How does React batching improve rendering?</strong></summary>

Explain how React groups state updates to reduce re-renders.

</details>

<details>
<summary><strong>6. How do you avoid unnecessary re-renders?</strong></summary>

Discuss memoization, React.memo, useMemo, useCallback, and state management strategies.

</details>

<details>
<summary><strong>7. Explain controlled vs uncontrolled components.</strong></summary>

Compare React-managed form state versus DOM-managed form state.

</details>

<details>
<summary><strong>8. How do you cancel ongoing API requests in React?</strong></summary>

Explain AbortController and cleanup inside useEffect.

</details>

<details>
<summary><strong>9. How does React reconciliation work internally?</strong></summary>

Describe Virtual DOM diffing, Fiber nodes, and update prioritization.

</details>

---

## 🟠 Round 3 – Browser & Performance

<details>
<summary><strong>1. What is code splitting?</strong></summary>

Explain breaking bundles into smaller chunks that load on demand.

</details>

<details>
<summary><strong>2. What is tree shaking?</strong></summary>

Describe removal of unused code during the build process.

</details>

<details>
<summary><strong>3. Explain CORS in simple terms.</strong></summary>

Describe browser security restrictions for cross-origin requests.

</details>

<details>
<summary><strong>4. What causes UI jank?</strong></summary>

Discuss main-thread blocking, excessive rendering, layout shifts, and large JavaScript tasks.

</details>

<details>
<summary><strong>5. What causes memory leaks in React apps?</strong></summary>

Explain uncleaned subscriptions, timers, event listeners, and pending async operations.

</details>

<details>
<summary><strong>6. Explain repaint vs reflow vs compositing.</strong></summary>

Compare browser rendering stages and their performance impact.

</details>

<details>
<summary><strong>7. How does browser rendering work internally?</strong></summary>

Cover parsing, DOM, CSSOM, render tree, layout, paint, and compositing.

</details>

<details>
<summary><strong>8. How do you optimize bundle size in React?</strong></summary>

Discuss code splitting, tree shaking, lazy loading, dependency analysis, and compression.

</details>

<details>
<summary><strong>9. Explain browser caching strategies with examples.</strong></summary>

Cover Cache-Control, ETag, CDN caching, service workers, and cache invalidation.

</details>

<details>
<summary><strong>10. How do you debug frontend performance bottlenecks?</strong></summary>

Explain DevTools Performance tab, Lighthouse, React Profiler, and Web Vitals.

</details>

---

## 🔴 Round 4 – Authentication & Security

<details>
<summary><strong>1. Explain authentication vs authorization.</strong></summary>

Compare verifying identity versus controlling access permissions.

</details>

<details>
<summary><strong>2. How do refresh tokens work internally?</strong></summary>

Describe access token renewal flows and token rotation.

</details>

<details>
<summary><strong>3. How do you securely store tokens in frontend apps?</strong></summary>

Compare HttpOnly cookies, localStorage, sessionStorage, and security implications.

</details>

---

## 🔵 Round 5 – Advanced Frontend Architecture

<details>
<summary><strong>1. Difference between CSR and SSR?</strong></summary>

Compare rendering on the client versus rendering on the server.

</details>

<details>
<summary><strong>2. Explain hydration mismatch and why it happens.</strong></summary>

Discuss differences between server-rendered HTML and client-rendered output.

</details>

<details>
<summary><strong>3. Explain race conditions in frontend applications.</strong></summary>

Describe concurrent async operations producing inconsistent results.

</details>

</details>

---

## ⭐ Expert-Level Questions Frequently Asked in Staff/Senior Frontend Interviews

<details>
<summary><strong>1. Design a frontend architecture serving millions of users.</strong></summary>

Topics:

* CDN
* Edge caching
* SSR
* ISR
* Monitoring
* Feature flags
* Micro-frontends

</details>

<details>
<summary><strong>2. Design a scalable state management strategy.</strong></summary>

Topics:

* Local state
* Global state
* Server state
* Caching layers
* Data synchronization

</details>

<details>
<summary><strong>3. Design a real-time collaborative application.</strong></summary>

Topics:

* WebSockets
* Optimistic updates
* Conflict resolution
* Presence indicators

</details>

<details>
<summary><strong>4. Design an infinitely scrolling feed used by millions.</strong></summary>

Topics:

* Virtualization
* Pagination
* Caching
* Prefetching
* Analytics

</details>
