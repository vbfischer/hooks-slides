
## useEffect (Hooks)

* perform side effects in functions

Notes:
Side effects are basically anything that affects something outside the scope of the current function that is being executed

examples are:

* fetch requests
* Manipulating DOM directly
* timer functions

---

## useEffect (Hooks)

accepts 2 parameters:

* function to call
* optional array of dependencies

```js
React.useEffect(() => {
    function to call
}, [optional dependencies]);
```

Notes:
The hook will use the dependencies array to determine if the function should be called. If any item in the dependency array is updated, then it will call.

If no dependencies are provided, it will be called on every render.;

if dependency is an empty array, it will ONLY be called on the initial render.

---

## useEffect (Hooks)

```js[5-7|13-15]
import React from "react";
import { Box, Button, Center, Stack } from "@chakra-ui/react";

export const Counter = () => {
  const [count, setCount] = React.useState<number>(() =>
    parseInt(window.localStorage.getItem("count") ?? "0")
  );

  const handleClick = () => {
    setCount((prev) => prev + 1);
  };

  React.useEffect(() => {
      window.localStorage.setItem("count", count.toString());
  }, [count]);

  return (
    <Center>
      <Stack spacing="16px">
        <Box>
          <Button onClick={handleClick}>Increment State</Button>
        </Box>
        <Box>
          <CounterDisplay count={count}/>
        </Box>
      </Stack>
    </Center>
  );
};


const CounterDisplay = ({ count }: {count: number}) => {
  return <Box>Click Count: {count}</Box>;
};
```

Notes:
Ok, so lets say we want to store the count in local storage so that if we leave the page and come back, we can start where we left off.

