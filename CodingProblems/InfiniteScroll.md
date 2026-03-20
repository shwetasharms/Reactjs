
## 📌 What is Infinite Scroll?

Infinite Scroll is a technique where more data loads automatically as the user scrolls down the page.

👉 Example: Instagram feed, Twitter timeline

---

## 🧠 Simple Explanation (For Beginners)

Think of it like this:

* You open a page → some data loads
* You scroll down → more data loads automatically
* No "Next" button needed

---

## ⚙️ How It Works (Basic Flow)

1. Load initial data
2. Listen to scroll event
3. Check if user reached bottom
4. Fetch more data
5. Append new data to existing list

---

## 🏗️ Basic Implementation (Step by Step)

### Step 1: Setup State

```js
const [data, setData] = useState([]);
const [page, setPage] = useState(1);
const [loading, setLoading] = useState(false);
```

---

### Step 2: Fetch Data Function

```js
const fetchData = async () => {
  setLoading(true);
  const res = await fetch(`https://api.example.com/items?page=${page}`);
  const newData = await res.json();

  setData((prev) => [...prev, ...newData]);
  setLoading(false);
};
```

---

### Step 3: Handle Scroll

```js
const handleScroll = () => {
  if (
    window.innerHeight + document.documentElement.scrollTop >=
    document.documentElement.offsetHeight - 100
  ) {
    setPage((prev) => prev + 1);
  }
};
```

---

### Step 4: useEffect

```js
useEffect(() => {
  fetchData();
}, [page]);

useEffect(() => {
  window.addEventListener("scroll", handleScroll);
  return () => window.removeEventListener("scroll", handleScroll);
}, []);
```

---

## ⚡ Optimized Approach (Best Practice)

Use **Intersection Observer API** instead of scroll events.

### Why?

* Better performance
* No continuous event firing

### Example:

```js
const observer = useRef();

const lastElementRef = (node) => {
  if (loading) return;

  if (observer.current) observer.current.disconnect();

  observer.current = new IntersectionObserver((entries) => {
    if (entries[0].isIntersecting) {
      setPage((prev) => prev + 1);
    }
  });

  if (node) observer.current.observe(node);
};
```
## Full Code With Scroll Event 
```
import React, { useEffect, useState } from "react";

function InfiniteScroll() {
  const [data, setData] = useState([]);
  const [page, setPage] = useState(1);
  const [loading, setLoading] = useState(false);
  const [hasMore, setHasMore] = useState(true);

  const fetchData = async () => {
    if (!hasMore) return;

    setLoading(true);

    const response = await fetch(
      `https://jsonplaceholder.typicode.com/posts?_page=${page}&_limit=10`
    );
    const result = await response.json();

    if (result.length === 0) {
      setHasMore(false);
    } else {
      setData((prev) => [...prev, ...result]);
    }

    setLoading(false);
  };

  const handleScroll = () => {
    if (
      window.innerHeight + document.documentElement.scrollTop >=
        document.documentElement.offsetHeight - 100 &&
      !loading
    ) {
      setPage((prev) => prev + 1);
    }
  };

  useEffect(() => {
    fetchData();
  }, [page]);

  useEffect(() => {
    window.addEventListener("scroll", handleScroll);
    return () => window.removeEventListener("scroll", handleScroll);
  }, [loading]);

  return (
    <div>
      <h1>Infinite Scroll</h1>

      {data.map((item) => (
        <div
          key={item.id}
          style={{
            border: "1px solid #ccc",
            margin: "10px",
            padding: "10px",
          }}
        >
          <h3>{item.title}</h3>
          <p>{item.body}</p>
        </div>
      ))}

      {loading && <p>Loading...</p>}
      {!hasMore && <p>No more data</p>}
    </div>
  );
}

export default InfiniteScroll;
```

## 💡 Follow-up Interview Questions

* How do you prevent multiple API calls?
* How do you handle loading & error states?
* Why is Intersection Observer better?
* How do you implement pagination with infinite scroll?

---
