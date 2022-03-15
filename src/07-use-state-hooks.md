## State (Hooks)

```js[4|5-7]
import React from "react";
import { Box, Button, Center, Stack } from "@chakra-ui/react";

export const Counter = () => {
  const [count, setCount] = React.useState<number>(0);

  const handleClick = () => {
    setCount((prev) => prev + 1);
  };

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

---

## State - Initialization

Initialized on mount

```js
const [count, setCount] = React.useState(0);
```

Notes:
State accepts an initial value, and returns an array containing two objects:

* The current state
* a dispatch method for updating state

An array is handy in that you can then name the variables whatever you want.

State is immutable, meaning that you cannot update the variable `count`. If you want to update it, you need to call `setCount`.



Use state is initialized only on mount. On subsequent renders, the parameters passed to `useState` are ignored.

---

## State - Initialization

```js
const initialCount = someExpensiveFunction()

const [count, setCount] = React.useState(initialCount);
```

Notes:
Suppose you needed to do some expensive calculation for the initial count. the expensive method would be executed every time the component renders, even though it won't use that value. 

Remember, whatever is passed to useState is ignored if its not in the initial mount

---

## State - Lazy Initialization

```js
const [count, setCount] = React.useState(() => someExpensiveFunction());
```

Notes:
`useState` will accept a function known as a "Lazy Initializer".

The value that is passed to useState is a function. On the initial mount, it will use it whether its an object or a function. If its a function, it will execute it to get the initial value. On subsequent renders, the function is still passed to useState, but it will be ignored (i.e., not executed)
