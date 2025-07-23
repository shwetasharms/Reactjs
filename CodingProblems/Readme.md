# React.js Coding Interview Questions

This repository contains a list of frequently asked React.js interview questions to help you prepare for your next interview. Each question is categorized based on topics, covering both fundamental and advanced concepts of React.js.

## Table of Contents

1. [Simple Counter Component](#introduction-to-reactjs)
2. [Create a To-Do list](#component-lifecycle)
3. [Implement React Routers](#state-and-props)
4. [Implement Redux in a React application](#hooks)
5. [Implement pagination ](#react-router)
6. [Create a photo gallery](#redux)
7. [Build a multi-step form](#performance-optimization)
8. [Build a React hook to debounce user input](#testing-in-react)
9. [Nested Checkbox ](#nested-checbox)





#nested-checbox
Here’s the challenge in simple terms 👇

🔹 Part 1: Build a checkbox structure that can nest recursively based on a config object.
🔹 Part 2: When all child checkboxes are selected, the parent should be auto-checked.
🔹 Part 3: Selecting the parent checkbox should auto-select all of its children.

It may seem UI-focused at first, but solving it requires solid understanding of:

→ DFS traversal,
→ Event handling, and
→ DOM state management.

I used two DFS passes to handle the interactions cleanly,

``` Javascript 

import React, { useState, useEffect } from "react";

// Example config tree
const config = [
  {
    id: "1",
    label: "Fruits",
    children: [
      { id: "1.1", label: "Apple" },
      { id: "1.2", label: "Banana" },
    ],
  },
  {
    id: "2",
    label: "Vegetables",
    children: [
      {
        id: "2.1",
        label: "Leafy",
        children: [
          { id: "2.1.1", label: "Spinach" },
          { id: "2.1.2", label: "Lettuce" },
        ],
      },
      { id: "2.2", label: "Carrot" },
    ],
  },
];

function CheckboxTree({ treeData }) {
  const [checkedMap, setCheckedMap] = useState({});

  useEffect(() => {
    const initial = {};
    const initDFS = (nodes) => {
      for (const node of nodes) {
        initial[node.id] = false;
        if (node.children) initDFS(node.children);
      }
    };
    initDFS(treeData);
    setCheckedMap(initial);
  }, [treeData]);

  const handleToggle = (id, node, isChecked) => {
    const newChecked = { ...checkedMap };

    const topDownDFS = (node, checked) => {
      newChecked[node.id] = checked;
      if (node.children) {
        for (const child of node.children) topDownDFS(child, checked);
      }
    };

    const bottomUpDFS = (parent) => {
      if (!parent) return;
      const allChecked = parent.children.every((child) => newChecked[child.id]);
      newChecked[parent.id] = allChecked;
    };

    topDownDFS(node, isChecked);

    const updateParents = (currentNode, rootNodes) => {
      const dfs = (node, parent = null) => {
        if (node.id === currentNode.id) return parent;
        if (node.children) {
          for (const child of node.children) {
            const found = dfs(child, node);
            if (found) return found;
          }
        }
        return null;
      };

      let parent = dfsTree(currentNode, rootNodes);
      while (parent) {
        bottomUpDFS(parent);
        parent = dfsTree(parent, rootNodes);
      }
    };

    const dfsTree = (targetNode, nodes) => {
      for (const node of nodes) {
        if (node.children?.some((child) => child.id === targetNode.id)) return node;
        const deeper = dfsTree(targetNode, node.children || []);
        if (deeper) return deeper;
      }
      return null;
    };

    updateParents(node, treeData);
    setCheckedMap(newChecked);
  };

  const renderTree = (nodes) => {
    return nodes.map((node) => (
      <div key={node.id} style={{ paddingLeft: 20 }}>
        <label>
          <input
            type="checkbox"
            checked={!!checkedMap[node.id]}
            onChange={(e) => handleToggle(node.id, node, e.target.checked)}
          />
          {node.label}
        </label>
        {node.children && renderTree(node.children)}
      </div>
    ));
  };

  const topParentChecked = (nodes) => {
    return nodes.every((node) => {
      if (node.children) return topParentChecked(node.children);
      return checkedMap[node.id];
    });
  };

  const handleTopParentChange = (e) => {
    const isChecked = e.target.checked;
    const newChecked = { ...checkedMap };

    const topDownDFS = (node, checked) => {
      newChecked[node.id] = checked;
      if (node.children) {
        for (const child of node.children) topDownDFS(child, checked);
      }
    };

    for (const node of treeData) {
      topDownDFS(node, isChecked);
    }

    setCheckedMap(newChecked);
  };

  return (
    <div>
      <label>
        <input
          type="checkbox"
          checked={topParentChecked(treeData)}
          onChange={handleTopParentChange}
        />
        Select All
      </label>
      {renderTree(treeData)}
    </div>
  );
}

export default function App() {
  return (
    <div className="p-4">
      <h1 className="text-xl font-bold mb-2">Recursive Checkbox Tree</h1>
      <CheckboxTree treeData={config} />
    </div>
  );
}
```
