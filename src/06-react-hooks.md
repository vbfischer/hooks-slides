## Basic Hooks

* `useState`
* `useEffect`
* `useContext`

Notes:
These are the basic hooks that you'll likely use on a daily basis. 

---

## Additional Hooks

- `useReducer`
- `useCallback`
- `useMemo`
- `useRef`
- `useImperativeHandle`
- `useLayoutEffect`
- `useDebugValue`


notes:
I have yet to use `useImperativeHandle`, `useLayoutEffect` and `useDebugValue` hooks, and they have limited use cases. 

By far the most used ones will be `useState` and `useEffect`. `useContext` can be a bit complex so I'll probabl save that one for a later date. I'll prpobably cover `useState`, `useEffect`, `useRef` and `useMemo` today depending on time

---

## Rules of Hooks

* Only call hooks at top level
* Only call hooks from React Components

Notes:
Never call hooks inside a loop, conditional statement or nested functions (this includes any early returns). React depends on hooks being called in the same order each time a component is rendered.

Only call hooks from either your functional component or within a custom hook (keeping in mind the custom hook has to follow these same rules)