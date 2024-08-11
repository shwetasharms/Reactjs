##Currently, React doesn't automatically re-render on state change. A way to optimise these re-renders is to manually use useMemo(), useCallback(), and memo APIs. As per React's team, this was a "reasonable manual compromise". Their vision was to let React manage these re-renders.

But the React team realized that manual optimisation is cumbersome, and the feedback from the community encouraged them to solve this issue.

And so the React Team has created the "React compiler". The React compiler will now manage these re-renders. React will decide automatically how and when to change the state and update the UI.

With this, we developers don't need to do this manually anymore. It also means no need to use useMemo(), useCallback(), and memo.