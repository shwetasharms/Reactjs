# React.js Comprehensive Guide

## Table of Contents
1. [Components](#components)
   - [Functional Components](#functional-components)
   - [Class Components](#class-components)
   - [JSX Syntax](#jsx-javascript-xml-syntax)

2. [Props (Properties)](#props-properties)
   - [Passing Props](#passing-props)
   - [Default Props](#default-props)
   - [Prop Types](#prop-types)

3. [State](#state)
   - [useState Hook](#usestate-hook)
   - [Class Component State](#class-component-state)
   - [Immutable State](#immutable-state)

4. [Lifecycle Methods (Class Components)](#lifecycle-methods-class-components)
   - [componentDidMount](#componentdidmount)
   - [componentDidUpdate](#componentdidupdate)
   - [componentWillUnmount](#componentwillunmount)

5. [Hooks (Functional Components)](#hooks-functional-components)
   - [useState](#usestate)
   - [useEffect](#useeffect)
   - [useContext](#usecontext)
   - [useReducer](#usereducer)
   - [useCallback](#usecallback)
   - [useMemo](#usememo)
   - [useRef](#useref)
   - [useImperativeHandle](#useimperativehandle)
   - [useLayoutEffect](#uselayouteffect)

6. [Event Handling](#event-handling)
   - [Handling Events in Functional Components](#handling-events-in-functional-components)
   - [Handling Events in Class Components](#handling-events-in-class-components)

7. [Conditional Rendering](#conditional-rendering)
   - [if Statements](#if-statements)
   - [Ternary Operators](#ternary-operators)
   - [Logical && Operator](#logical--operator)

8. [Lists and Keys](#lists-and-keys)
   - [Rendering Lists](#rendering-lists)
   - [Keys in React Lists](#keys-in-react-lists)

9. [Component Composition](#component-composition)
   - [Reusing Components](#reusing-components)
   - [Children Props](#children-props)
   - [Composition vs Inheritance](#composition-vs-inheritance)

10. [Higher-Order Components (HOC)](#higher-order-components-hoc)
    - [Creating HOCs](#creating-hocs)
    - [Using HOCs for Reusability](#using-hocs-for-reusability)

11. [Render Props](#render-props)
    - [Using Render Props Pattern](#using-render-props-pattern)

12. [React Router](#react-router)
    - [`<BrowserRouter>`](#browserrouter)
    - [`<Route>`](#route)
    - [`<Link>`](#link)
    - [`<Switch>`](#switch)
    - [Route Parameters](#route-parameters)

13. [Navigation](#navigation)
    - [useHistory Hook](#usehistory-hook)
    - [useLocation Hook](#uselocation-hook)

14. [Context API](#context-api)
    - [Creating Context](#creating-context)
    - [useContext Hook](#usecontext-hook)

15. [Redux](#redux)
    - [Actions](#actions)
    - [Reducers](#reducers)
    - [Store](#store)
    - [connect Function (React-Redux)](#connect-function-react-redux)

16. [Forms](#forms)
    - [Handling Form Data](#handling-form-data)
    - [Controlled Components](#controlled-components)
    - [Uncontrolled Components](#uncontrolled-components)

17. [Side Effects](#side-effects)
    - [useEffect for Data Fetching](#useeffect-for-data-fetching)
    - [useEffect Cleanup](#useeffect-cleanup)

18. [AJAX Requests](#ajax-requests)
    - [Fetch API](#fetch-api)
    - [Axios Library](#axios-library)

19. [Error Handling](#error-handling)
    - [Error Boundaries](#error-boundaries)
    - [componentDidCatch (Class Components)](#componentdidcatch-class-components)
    - [ErrorBoundary Component (Functional Components)](#errorboundary-component-functional-components)

20. [Testing](#testing)
    - [Jest Testing Framework](#jest-testing-framework)
    - [React Testing Library](#react-testing-library)

21. [Optimization](#optimization)
    - [Memoization](#memoization)
    - [Profiling and Performance Monitoring](#profiling-and-performance-monitoring)

22. [Build and Deployment](#build-and-deployment)
    - [Create React App (CRA)](#create-react-app-cra)
    - [Production Builds](#production-builds)
    - [Deployment Strategies](#deployment-strategies)

23. [Styling Libraries](#styling-libraries)
    - [Styled-components](#styled-components)
    - [CSS Modules](#css-modules)

24. [State Management Libraries](#state-management-libraries)
    - [Redux](#redux)
    - [MobX](#mobx)

25. [Routing Libraries](#routing-libraries)
    - [React Router](#react-router)
    - [Reach Router](#reach-router)

---

## Components
A React component is basically a building block of a React application. Think of it as a small piece or unit of code that defines a part of the user interface (UI) of your web page or app.

Imagine you're creating a website. The website can have different parts, like a header, a footer, buttons, or a list of items. Each of these parts can be thought of as a React component.

Here’s a simple way to understand it:

Reusable: A component is like a template. You can use it many times in different places without having to rewrite the code. For example, if you create a button component, you can reuse it all over your app wherever you need a button.

Self-contained: Each component takes care of its own job. For example, a button component knows how to look (its appearance) and what to do (its behavior when clicked). It doesn't need to know anything about the rest of the app, just what it's supposed to do.

Component types: There are mainly two types of React components:

Functional Components: These are simple JavaScript functions that return the UI (HTML).
Class Components: These are a bit more complex and use classes to define the component, but in modern React, functional components are more commonly used.

### Functional Components
Functional components are...

### Class Components
Class components are...

### JSX (JavaScript XML) Syntax
JSX allows...

## Props (Properties)
Props are...
