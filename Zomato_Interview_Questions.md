# Frontend Interview Questions

## 🟢 Round 1 – Technical

<details>
<summary><strong>1. What is the difference between var, let, and const?</strong></summary>

### var

* Function-scoped
* Can be re-declared and reassigned
* Hoisted and initialized with `undefined`

### let

* Block-scoped
* Can be reassigned but not re-declared in the same scope
* Hoisted but not initialized (Temporal Dead Zone)

### const

* Block-scoped
* Cannot be reassigned
* Must be initialized during declaration
* Objects and arrays can still have their contents modified

</details>

<details>
<summary><strong>2. Explain closures with a practical example.</strong></summary>

A closure is created when a function remembers variables from its outer scope even after the outer function has finished execution.

```javascript
function createCounter() {
  let count = 0;

  return function () {
    return ++count;
  };
}

const counter = createCounter();

console.log(counter()); // 1
console.log(counter()); // 2
console.log(counter()); // 3
```

**Use Cases**

* Data privacy
* Function factories
* Event handlers
* React hooks

</details>

<details>
<summary><strong>3. Build a custom React hook for data fetching.</strong></summary>

```jsx
import { useEffect, useState } from "react";

export function useFetch(url) {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    let cancelled = false;

    async function fetchData() {
      try {
        const response = await fetch(url);

        if (!response.ok) {
          throw new Error("Request failed");
        }

        const result = await response.json();

        if (!cancelled) {
          setData(result);
        }
      } catch (err) {
        if (!cancelled) {
          setError(err);
        }
      } finally {
        if (!cancelled) {
          setLoading(false);
        }
      }
    }

    fetchData();

    return () => {
      cancelled = true;
    };
  }, [url]);

  return { data, loading, error };
}
```

</details>

<details>
<summary><strong>4. How does React reconciliation work?</strong></summary>

React reconciliation is React's process of comparing the previous Virtual DOM with the new Virtual DOM.

### Flow

1. State/props change
2. New Virtual DOM generated
3. Diffing algorithm compares trees
4. Changed nodes identified
5. Real DOM updated minimally

### Benefits

* Faster rendering
* Reduced DOM operations
* Better performance

</details>

<details>
<summary><strong>5. Why are keys important in React lists?</strong></summary>

Keys help React uniquely identify list items during reconciliation.

```jsx
users.map(user => (
  <UserCard key={user.id} user={user} />
))
```

### Benefits

* Preserves component state
* Efficient updates
* Prevents unnecessary re-renders

### Avoid

```jsx
users.map((user, index) => (
  <UserCard key={index} user={user} />
))
```

Using indexes can introduce bugs when items are reordered.

</details>

---

## 🟡 Round 2 – Advanced Technical / System Design

<details>
<summary><strong>1. How would you design a scalable frontend architecture for a large-scale application?</strong></summary>

### Key Principles

* Feature-based architecture
* Shared component library
* API abstraction layer
* Centralized state strategy
* CI/CD automation
* Monitoring and observability

```text
src/
├── app/
├── features/
├── shared/
├── services/
├── store/
├── hooks/
└── utils/
```

</details>

<details>
<summary><strong>2. Explain React Server Components and their advantages.</strong></summary>

React Server Components render on the server and send serialized UI to the client.

### Advantages

* Smaller JavaScript bundles
* Faster page loads
* Better SEO
* Direct server-side data access
* Reduced client-side work

### Ideal Use Cases

* E-commerce
* Dashboards
* Content-heavy pages

</details>

<details>
<summary><strong>3. How would you implement infinite scrolling efficiently?</strong></summary>

### Recommended Approach

* Intersection Observer
* Cursor/Pagination APIs
* Request deduplication
* Virtualized rendering

```javascript
const observer = new IntersectionObserver(entries => {
  if (entries[0].isIntersecting) {
    loadMore();
  }
});
```

### Optimization Libraries

* TanStack Query
* react-window
* react-virtualized

</details>

<details>
<summary><strong>4. What techniques would you use to improve Core Web Vitals?</strong></summary>

### LCP

* Optimize images
* CDN delivery
* SSR/SSG
* Asset preloading

### INP

* Reduce JS execution
* Code splitting
* Debouncing

### CLS

* Fixed image dimensions
* Skeleton loaders
* Avoid layout shifts

</details>

<details>
<summary><strong>5. How do you manage state in large React applications?</strong></summary>

| State Type    | Solution                |
| ------------- | ----------------------- |
| Local State   | useState                |
| Complex State | useReducer              |
| Server State  | TanStack Query          |
| Global State  | Redux Toolkit / Zustand |
| Forms         | React Hook Form         |

### Best Practices

* Keep state local when possible
* Normalize data
* Avoid overusing global state

</details>

<details>
<summary><strong>6. Explain frontend caching strategies.</strong></summary>

### Browser Cache

* Cache-Control
* ETags

### CDN Cache

* Static assets
* Images

### Application Cache

* React Query
* SWR

### Service Workers

* Offline support
* PWA capabilities

### Benefits

* Faster load times
* Reduced server traffic

</details>

<details>
<summary><strong>7. How would you design a frontend system serving millions of users daily?</strong></summary>

### Architecture

1. CDN
2. Edge caching
3. SSR/ISR
4. Code splitting
5. Image optimization
6. Monitoring
7. Feature flags
8. Load balancing

### Example Stack

* Next.js
* React
* Cloudflare
* Redis
* Kubernetes

</details>

---

## 🔵 Round 3 – Managerial / Behavioral

<details>
<summary><strong>1. Tell us about a challenging project you worked on.</strong></summary>

### STAR Answer

**Situation:** Legacy dashboard had poor performance.

**Task:** Improve performance without affecting functionality.

**Action:**

* Profiled bottlenecks
* Added code splitting
* Optimized API requests
* Introduced caching

**Result:**

* 60% faster load times
* Better Core Web Vitals
* Improved user satisfaction

</details>

<details>
<summary><strong>2. How did you handle a critical production issue?</strong></summary>

### Process

1. Assess impact
2. Communicate status
3. Rollback or hotfix
4. Identify root cause
5. Monitor recovery
6. Conduct postmortem

### Focus Areas

* Fast mitigation
* Clear communication
* Prevention measures

</details>

<details>
<summary><strong>3. Describe a disagreement within your team and how you resolved it.</strong></summary>

A teammate and I disagreed on adopting a new state management solution.

Instead of debating opinions, we built a proof of concept, measured performance and maintainability, and presented findings to the team.

The decision became data-driven, resulting in alignment and stronger collaboration.

</details>

<details>
<summary><strong>4. How do you mentor junior developers and review code?</strong></summary>

### Mentoring

* Pair programming
* Knowledge-sharing sessions
* Constructive feedback
* Ownership encouragement

### Code Reviews

* Verify correctness
* Check edge cases
* Improve maintainability
* Explain reasoning behind suggestions

### Goal

Help developers grow while maintaining high engineering standards.

</details>
