## Kinds of React Components

* Class
* Functional

Notes:
There are two ways of creating components in React. Since the introduction of hooks, there is no real substantial difference between using classes or functional components. Going to briefly discuss what the difference between the two are and then how hooks makes it such that you don't have to write classes anymore (if you don't want to).

---

## Class Components

```js
class AnyComponent extends React.Component {
    constructor(props) {
        super(props);

        this.state = {
            message: "Hello"
        }
    }

    render() {
        return {
            <div>
                <h1>{this.state.message}: {this.props.name}</h1>
            </div>
        }
    }
}

```

Notes:
Traditionally if you wanted to have state and handle lifecyles, you'd have to use a class. 

Here we define state as an object with property "Message". And it is accessed via `this.state.message`. Props have to be passed
down through the constructor, and are accessed via `this.props.name`.

---

## Functional Components

```js
const AnyComponent = (props) => {
    return <div><h1>Hello: {props.name}</div>
}
```

Notes:
Functional components offer a simplifed way of creating components. The body of the the component is basically just the `render` function from the class component, and since props is part of the scope of the function, they are accessed as `props.name`

---

## Presentational vs Container Components

aka Smart vs Dumb Components

* Presentational - (how things look)
* Container - (how things work)

Notes: again, this distinction is not as important anymore. Basically, it this pattern lets you separate complex stateful logic from other aspects of the components. As we'll see later, hooks gives us this ability without enforcing this artificial distinction between components

Presentational components:

* the display
* rarely has state, so usually functional components
* data passed as props
* No dependencies on rest of the app

Container components

* The logic
* Provide data and behavior
* Often stateful and serve as data sources.

---