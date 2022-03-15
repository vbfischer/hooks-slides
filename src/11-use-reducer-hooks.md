## useReducer

* alternative to `useState`
* Uses Redux style reducers to calculate state
* Preferable to `useState` with complex state logic

---

## useReducer

```js
const initialState = {count: 0};

const reducer = (state, action) => {
    switch(action.type) {
        case 'increment':
            return {count: state.count + 1};
        case 'decrement':
            return {count: state.count -1};
        default:
            throw new Eerror();
    }
}

const Counter = () => {
    const [state, dispatch] = React.useReducer(reducer, initialState);

    return (
        <>
            Count: {state.count}
            <button onClick={() => dispatch({type: 'decrement'})}></button>
            <button onClick={() => dispatch({type: 'increment'})}></button>
        </>
    )
}
```