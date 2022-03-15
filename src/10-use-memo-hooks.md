## useMemo

* Only recompute value if dependencies changed
* Avoid expensive calculations
* No side effects allowed
* "a performance optimization, not a semantic guarantee"

Notes:
The last point is a quote from the docs site. Basically, don't write code that depends on it only being run once, because React may choose to forget some values in order to free memory for offscreen components. 

---

## useMemo

```js
const memoizedValue = React.useMemo(() => {
    return value * 1000;
}, [value]);
```

Notes:
if no array is provided, a new value will be computed on every render.

