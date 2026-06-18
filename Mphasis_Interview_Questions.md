# Senior React & Frontend Interview Questions

A collection of advanced React, TypeScript, JavaScript, frontend architecture, and system design interview questions.

---

# React

## 1. How does React's reconciliation algorithm work?

* What problem does reconciliation solve?
* How does React compare virtual DOM trees?
* How does React use keys during reconciliation?
* What happens when keys are missing or unstable?

---

## 2. What are React Fiber and Concurrent Rendering?

* Why was React Fiber introduced?
* How does Fiber improve rendering performance?
* What is interruptible rendering?
* What are concurrent features in React 18?

Topics:

* Fiber Architecture
* Time Slicing
* Suspense
* Concurrent Rendering
* Transitions

---

## 3. Difference Between CSR, SSR, and SSG

Compare:

### Client-Side Rendering (CSR)

* Rendering happens in the browser
* Fast navigation after initial load
* Poor SEO without additional optimization

### Server-Side Rendering (SSR)

* HTML generated on the server
* Better SEO
* Faster first contentful paint

### Static Site Generation (SSG)

* HTML generated at build time
* Extremely fast delivery
* Best for content-driven websites

Discuss:

* Performance trade-offs
* SEO implications
* Use cases for each approach

---

## 4. When Would You Use `useRef` Instead of `useState`?

Discuss:

* Mutable values
* Avoiding re-renders
* DOM references
* Storing previous values
* Timers and intervals

Examples:

* Input focus management
* Tracking previous props
* Caching values between renders

---

## 5. Explain `React.memo` and Scenarios Where It Can Hurt Performance

Topics:

* Memoization
* Shallow comparison
* Preventing unnecessary re-renders

Potential drawbacks:

* Additional comparison cost
* Ineffective with frequently changing props
* Over-optimization

---

## 6. How Do Custom Hooks Improve Code Reusability and Maintainability?

Benefits:

* Separation of concerns
* Reusable business logic
* Cleaner components
* Better testing

Examples:

* Authentication hooks
* Data-fetching hooks
* Form management hooks

---

## 7. What Causes Unnecessary Re-renders in React and How Can They Be Prevented?

Common causes:

* Parent re-renders
* Inline functions
* Object and array recreation
* Context updates
* Unstable references

Optimization techniques:

* React.memo
* useMemo
* useCallback
* State colocation
* Component splitting

---

## 8. How Would You Implement Role-Based Access Control (RBAC) in a React Application?

Discuss:

### Authentication

* JWT
* OAuth
* Session-based auth

### Authorization

* Roles
* Permissions
* Route protection

Example roles:

* Admin
* Manager
* User

Topics:

* Protected routes
* Permission-based UI rendering
* Backend authorization validation

---

## 9. Difference Between Redux Toolkit, Context API, and TanStack Query

### Context API

Best for:

* Theme
* Authentication
* Small global state

Pros:

* Built into React
* Simple setup

Cons:

* Frequent re-renders
* Not optimized for server state

---

### Redux Toolkit

Best for:

* Complex application state
* Predictable state management

Pros:

* Centralized store
* Powerful developer tools

Cons:

* Additional complexity

---

### TanStack Query

Best for:

* Server state management

Features:

* Caching
* Retries
* Background refetching
* Pagination
* Optimistic updates

---

## 10. How Does TypeScript Generics Help in Large-Scale Applications?

Benefits:

* Reusable components
* Type safety
* Better maintainability

Examples:

```typescript
function identity<T>(value: T): T {
  return value;
}
```

Use cases:

* API clients
* Data tables
* Form libraries
* Reusable hooks

---

## 11. Explain Utility Types: Partial, Pick, Omit, and Record

### Partial

```typescript
type UserUpdate = Partial<User>;
```

Makes all properties optional.

---

### Pick

```typescript
type UserSummary = Pick<User, "id" | "name">;
```

Select specific properties.

---

### Omit

```typescript
type UserWithoutPassword = Omit<User, "password">;
```

Remove properties.

---

### Record

```typescript
type UserRoles = Record<string, string>;
```

Create key-value object types.

---

# JavaScript

## 12. What Is the JavaScript Event Loop?

Explain:

* Call Stack
* Web APIs
* Callback Queue
* Event Loop

---

### Microtasks

Examples:

```javascript
Promise.resolve().then(() => {
  console.log("Microtask");
});
```

Includes:

* Promise.then
* Promise.catch
* Promise.finally
* queueMicrotask

---

### Macrotasks

Examples:

```javascript
setTimeout(() => {
  console.log("Macrotask");
}, 0);
```

Includes:

* setTimeout
* setInterval
* DOM Events
* MessageChannel

---

### Important Rule

> All microtasks are executed before macrotasks.

---

# Frontend Architecture

## 13. How Would You Handle API Caching, Retries, and Background Synchronization?

Topics:

### Caching

* TanStack Query
* SWR
* Browser Cache
* Service Workers

### Retries

* Exponential backoff
* Retry limits
* Error classification

### Background Synchronization

* Background refetching
* Stale-while-revalidate
* Offline support

Considerations:

* User experience
* Performance
* Network reliability

---

## 14. Design a Scalable Notification System for a React Application Handling 1,000+ Users

Requirements:

* Real-time updates
* Notification history
* Read/unread status
* Scalability

Possible architecture:

```text
React Client
      ↓
WebSocket Connection
      ↓
Notification Service
      ↓
Database
```

Topics:

* WebSockets
* Push notifications
* Event-driven architecture
* Notification persistence
* Retry mechanisms

---

# System Design Discussion

## Real-Time Dashboard Displaying Live Data Updates

Design a scalable dashboard that receives and displays real-time updates.

---

### Topics To Discuss

#### WebSockets vs Polling

WebSockets:

* Persistent connection
* Real-time updates
* Lower latency

Polling:

* Simpler implementation
* Higher network overhead

---

#### State Management Strategy

Options:

* Redux Toolkit
* Zustand
* Context API
* TanStack Query

Discuss:

* Global state
* Data normalization
* Update frequency

---

#### Data Caching

Consider:

* In-memory cache
* Query caching
* Stale data management

Tools:

* TanStack Query
* Redis
* Browser Cache

---

#### Component Optimization

Techniques:

* React.memo
* useMemo
* useCallback
* Virtualization
* Lazy loading

---

#### Error Handling and Reconnection Logic

Handle:

* Connection failures
* Network interruptions
* Retry strategies

Techniques:

* Exponential backoff
* Automatic reconnection
* Fallback polling

---

# Interview Preparation Tips

Focus on:

* React internals
* Rendering lifecycle
* State management
* TypeScript fundamentals
* Performance optimization
* System design
* Scalability
* Real-world architecture decisions

Remember:

> Interviewers are often more interested in your reasoning and trade-off analysis than in a single "correct" answer.
