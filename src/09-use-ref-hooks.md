## useRef

* returns a mutable object
* value persists component lifetime
* does NOT cause rerender

```js
const refContainer = React.useRef(initialValue);
// refContainer.current contains value
refContainer.current = newValue
```

Note:
Basically, useRef is like a “box” that can hold a mutable value in its .current property. Unlike variables, its value will remain even when the component rerenders.

Unline mutating state, mutating the `.current` property does NOT cause a component to rerender

---

## useRef example

```js
export const Counter = () => {
    const counter = React.useRef(0);

    // Just a state so we can trigger a rerender.
    const [state, setState] = React.useState<number>(0);

    const handleRefButtonClick = () => {
        counter.current = counter.current + 1;
    }

    const handleStateButtonClick = () => {
        setState(prev => prev + 1);
    }

    return (
        <Center>
          <Stack spacing="16px">
            <Box>
              <Button onClick={handleRefButtonClick}>Increment Ref</Button>
            </Box>
            <Box>
              <Button onClick={handleStateButtonClick}>Trigger State</Button>
            </Box>
            <Box>
              <Box>
                  Ref: {counter.current}
              </Box>
              <Box>
                  State: {state}
              </Box>
            </Box>
          </Stack>
        </Center>
      );
}
```