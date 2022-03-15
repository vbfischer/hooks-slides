## Custom Hooks

* Extract reusable logic

Note:
Notice in our Reducer example, there was a lot of code related to the reducer, and dispatching stuff. Wouldn't it be great to extract that out of the component and provide it an API that doesn't depend on the Reducer stuff? We can do this using a custom hook.

Show example

```js
import { HooksFlow as Component } from "./examples/hooks-flow";
```