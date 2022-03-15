## React Component Lifecycles

* Mounting
* Updating
* Unmounting

notes:
don't worry about these too much, its mostly to set context as to the benefits of hooks.

---

<img src="/src/images/pre-hooks-lifecyles-full.JPG" width="500px">


---

<img src="/src/images/pre-hooks-lifecyles-simplified.JPG" width="800px">

---

## Mounting (Class)

first time component is displayed.

* constructor()
* getDerivedStateFromProps()
* render()
* componentDidMount()

notes: 
constructor is called when component is initialized. Here you can setup initial state, 
although as we'll see there is another place it can be initialized

getDerivedStateFromProps is where state can be set based on initial props

render() is the only one required. Its where your component tells React what to display. (later we'll talk about render vs commit phase).

componentDidMount() is called after the component updated to the DOM

`getDerivedStateFromProps` is rarely used.

---

## Updating (Class)

Happens when a component is updating (`state` or `props` have been changed).

* getDerivedStateFromProps()
* shouldComponentUpdate()
* render()
* getSnapshotBeforeUpdate()
* componentDidUpdate

notes: 
shouldComponentUpdate - here you can specify whether React should continue rendering

getSnapshotBeforeUpdate - gives you a chance to see what props or state are before the atual update.

componentDidUpdate - like componentDidMount, its called after the component is updated to the DOM

---

## Unmounting (Class)

* componentWillUnmount

notes:
this is the only phase.

called when component is about to be removed from DOM

Good place to do garbage collection tasks like unsubscribing from events, etc.