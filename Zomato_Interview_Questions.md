# Frontend Interview Questions

## 🟢 Round 1 – Technical

### 1. What is the difference between `var`, `let`, and `const`?

* **var**

  * Function-scoped
  * Can be re-declared and reassigned
  * Hoisted and initialized with `undefined`

* **let**

  * Block-scoped
  * Can be reassigned but not re-declared in the same scope
  * Hoisted but not initialized (Temporal Dead Zone)

* **const**

  * Block-scoped
  * Cannot be reassigned
  * Must be initialized during declaration
  * Objects and arrays can still have their contents modified

---

### 2. Explain closures with a practical example.

A closure is created when a function remembers variables from its outer scope even after the outer function has finished execution.

```javascript
function createCounter() {
  let count = 0;

  return function () {
    count++;
    return count;
  };
}

const counter = createCounter();

console.log(counter()); // 1
console.log(counter()); // 2
console.log(counter()); // 3
```

**Use Cases:**

* Data privacy
* Function factories
* Event handlers
* React hooks

---

### 3. Build a custom React hook for data fetching.

```jsx
import { useState, useEffect } from "react";

export function useFetch(url) {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    let cancelled = false;

    async function fetchData() {
      try {
        setLoading(true);

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

---

### 4. How does React reconciliation work?

React reconciliation is the process React uses to compare the previous Virtual DOM with the new Virtual DOM and determine the minimum number of updates needed in the real DOM.

**Steps:**

1. State or props change.
2. React creates a new Virtual DOM tree.
3. React compares it with the previous tree.
4. Differences are identified using the diffing algorithm.
5. Only changed elements are updated in the browser.

**Benefits:**

* Efficient rendering
* Improved performance
* Reduced DOM manipulations

---

### 5. Why are keys important in React lists?

Keys help React uniquely identify list items during reconciliation.

```jsx
{
  users.map(user => (
    <UserCard key={user.id} user={user} />
  ));
}
```

**Benefits:**

* Efficient DOM updates
* Preserves component state
* Prevents unnecessary re-renders

**Bad Example:**

```jsx
users.map((user, index) => (
  <UserCard key={index} user={user} />
));
```

Using indexes can cause UI bugs when items are reordered, inserted, or removed.

---

# 🟡 Round 2 – Advanced Technical / System Design

### 1. How would you design a scalable frontend architecture for a large-scale application?

**Key Principles:**

* Feature-based folder structure
* Modular components
* Shared design system
* API abstraction layer
* State management strategy
* CI/CD automation
* Monitoring and observability

**Example Structure:**

```text
src/
├── app/
├── features/
├── components/
├── hooks/
├── services/
├── utils/
├── store/
└── shared/
```

---

### 2. Explain React Server Components and their advantages.

React Server Components (RSC) render on the server and send serialized UI to the client.

**Advantages:**

* Smaller JavaScript bundles
* Faster initial page load
* Better SEO
* Direct server-side data fetching
* Reduced client-side processing

**Ideal For:**

* Product pages
* Dashboards
* Content-heavy applications

---

### 3. How would you implement infinite scrolling efficiently?

**Approach:**

* Use Intersection Observer
* Paginated API requests
* Virtualization for large lists
* Request deduplication
* Loading states and error handling

```javascript
const observer = new IntersectionObserver(entries => {
  if (entries[0].isIntersecting) {
    loadMore();
  }
});
```

**Optimization:**

* React Query / TanStack Query
* react-window
* react-virtualized

---

### 4. What techniques would you use to improve Core Web Vitals?

#### Largest Contentful Paint (LCP)

* Optimize images
* Use CDN
* Server-side rendering
* Preload critical assets

#### Interaction to Next Paint (INP)

* Reduce JavaScript execution
* Code splitting
* Debouncing/throttling

#### Cumulative Layout Shift (CLS)

* Reserve image dimensions
* Avoid dynamic content shifts
* Use skeleton loaders

---

### 5. How do you manage state in large React applications?

**State Layers:**

| Type            | Solution                |
| --------------- | ----------------------- |
| Local State     | useState                |
| Component Logic | useReducer              |
| Server State    | React Query             |
| Global State    | Redux Toolkit / Zustand |
| Forms           | React Hook Form         |

**Best Practices:**

* Keep state close to usage
* Avoid unnecessary global state
* Normalize complex data

---

### 6. Explain frontend caching strategies.

**Browser Cache**

* Cache-Control headers
* ETags

**CDN Cache**

* Static assets
* Images

**Application Cache**

* React Query
* SWR

**Service Workers**

* Offline support
* Progressive Web Apps

**Benefits**

* Reduced API requests
* Faster page loads
* Better user experience

---

### 7. How would you design a frontend system serving millions of users daily?

**Architecture Components:**

1. CDN for static assets
2. Edge caching
3. Server-side rendering (SSR)
4. Incremental Static Regeneration (ISR)
5. Code splitting
6. Image optimization
7. Monitoring and analytics
8. Error tracking
9. Feature flags
10. Load balancing

**Tech Stack Example**

* Next.js
* React
* CDN (Cloudflare/Akamai)
* Redis caching
* Kubernetes
* Observability tools

---

# 🔵 Round 3 – Managerial / Behavioral

### 1. Tell us about a challenging project you worked on.

**STAR Format**

**Situation:** Legacy dashboard suffered from slow performance and poor user experience.

**Task:** Improve performance while maintaining feature parity.

**Action:**

* Profiled bottlenecks
* Implemented code splitting
* Introduced caching
* Optimized API calls
* Reduced bundle size

**Result:**

* 60% faster page loads
* Improved Core Web Vitals
* Reduced infrastructure costs

---

### 2. How did you handle a critical production issue?

**Approach:**

1. Assess impact
2. Communicate with stakeholders
3. Roll back or hotfix
4. Identify root cause
5. Monitor system recovery
6. Conduct postmortem

**Key Focus:**

* Transparency
* Fast mitigation
* Long-term prevention

---

### 3. Describe a disagreement within your team and how you resolved it.

**Example Answer**

A team member and I disagreed on adopting a new state management library. Rather than debating opinions, we created a proof of concept, compared performance, maintainability, and developer experience, and presented findings to the team. The data-driven approach helped us reach consensus and improved team collaboration.

---

### 4. How do you mentor junior developers and review code?

**Mentoring Approach**

* Pair programming
* Knowledge-sharing sessions
* Clear feedback
* Encourage ownership

**Code Review Principles**

* Focus on maintainability
* Check correctness and edge cases
* Encourage best practices
* Explain reasoning behind suggestions
* Praise good solutions

**Goal**
Build confidence, improve engineering quality, and help developers grow independently.
