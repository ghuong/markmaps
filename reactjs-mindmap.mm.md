# ReactJS

## React Components

- are the functional entities of React
  - independent & reusable
  - define own HTML content, CSS styling, and JS functionality
  - opposite of traditional paradigm that split
    HTML, CSS, JS into separate files
  - much more scalable for larger applications
- are declared with a function:
  `const MyComponent = () => {...}`
  - with a capitalized name
  - must return an element
    with a root component
    - e.g. `return <div><img /><img /></div>`
    - or a fragment: `return <><img /><img /></>`
    - or an array: `return [<img />, <img />, ...]`
  - never defined within another component
- can be used elsewhere as
  `<MyComponent />`
  - by importing:
    `import MyComponent from "./components/MyComponent"`
    - where `components/MyComponent.js` exists
      (relative path from importing file)
      - and it exports: `export default MyComponent`
- conditional rendering
  - is when what a component renders
    depends on the state

### JSX

- Is HTML-like javascript syntax for defining layout
- can evaluate embedded expressions
  `<div>{"name is " + person.name}</div>`

### Props

- are data passed to components
  `const MyComp = (props) => {...}`
  - which can be accessed in the component's function definition
    - via `props.myData`
    - or accessed directly with destructuring
      `const MyComp = ({ myData, moreData }) => {...}`
  - like so: `<MyComp myData="my value" />`

### Hooks

- are the modern way to add state
  to functional components

  - classes were the old way

- State Hooks

  - `import React, { useState } from 'react'`
  - Add state to component:
    `const [ myState, setMyState ] = useState(myValue)`
  - Set state: `setMyState(newValue)`
    - Will re-render component
      (function body re-executed)
    - Never mutate previous state directly
  - can be shared between components
    - by "lifting the state up"
      to the parent
      - which then passes the state to child components
      - and also passes any event handlers
        that change the state to children
  - must adhere to rules
    - `useState` must not be called in a
      loop, conditional, or anywhere else
      than a component's function definition
      - to ensure that hooks always
        called in the same order

- Effect Hooks
  - perform side effects
    - data fetching
    - setting up subscription
    - manually changing DOM
  - `useEffect(hook, [])`
    - optional 2nd argument specifies how often to run;
      default runs after every render
    - ```js
      const hook = () => {
        // runs after render
      };
      useEffect(hook);
      ```

### When Used in Arrays / Iterators

- must have unique "key" attribute
  - helps React track which components have changed
    - so re-render is more efficient
  - but not globally unique,
    only unique amongst siblings
  - Anti-Pattern: array indices as keys (BAD)
    because indices might change
  - "key" does not get passed
    to child as a prop

### Controlled Components

- A component's behavior is _controlled_ by its parent
  when it's assigned its parent's state
- Must be assigned `onChange` handler,
  or else it's read-only

## Event Handlers

- are functions
  - which are called when an async. event occurs
  - can also be function references
  - but NOT function calls
- can be registered
  - e.g. buttons handle "click" mouse events:
    - ```jsx
      <button onClick={() => console.log("clicked")}>{text}</button>
      ```

## Create-React-App

- creates new app via CLI
- configures project to ~~compile~~ transpile automatically
  - using the transpiler Babel
  - to translate to pure javascript
