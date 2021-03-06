# Javascript

- is the scripting language of the web
- behaves according to its runtime environment
  - like the browser
  - or Node.JS

## Browser

- JS Runtime Engine
  - V8 in Chrome
  - is synchronous
  - maintains a single Stack to run code
- Web APIs
  - allow async. callbacks to be registered
  - when async. event triggers,
    pushes callback onto Task Queue
  - e.g.
    - setTimeout
    - XHR (XML HTTP Request)
    - Fetch
- Task Queue
  - queues up callbacks to be called when stack empty
- Event Loop
  - when stack is empty, pushes next task
    on Task Queue onto it

## Features

### Variables

- `const`
  - is immutable
- `let`
  - replaces the old `var`
- are scoped within their block
- are dynamically typed
- Operators
  - Equality: `===`
    - preferred over `==`
      (automatic type conversion)

### Data types

- Primitives
- Strings
  - are objects
  - Template Strings
    - ```js
      const name = "Jon";
      const greeting = `Hello, ${name}!`;
      // greeting: "Hello, Jon!"
      ```
- Arrays
  - are declared like so: `const arr = [2, 5, 3]`
  - can be destructured:
    `const [first, second, ...rest] = arr`
  - can be copied (array spread syntax):
    `copy = [ ...arr ]`
  - in FP, prefer copying over mutating arrays
    - e.g. `arr.concat` > `arr.push`
- Objects
  - are declared like so:
    `const obj = { key1: "value 1", key2: "value 2" }`
  - can access properties
    - `obj.key1`
    - `obj["secret number"] = 123`
  - can hold functions called "methods"
    - `this`
      - is a keyword that can be accessed in a method
      - refers to the object itself
      - when calling a method through a reference
        - `this` loses the original object
          and instead refers to the global object
  - can be destructured:
    `const { key1, key2, ...rest } = obj`
  - can be copied (via object spread syntax):
    `copy = { ...obj, key1: newValue }`
- Functions
  - are objects
  - function definitions
    - `function myFunc(x, y) { return x + y }`
    - functions are named
  - function references
    - `const myFunc = function(x, y) { return x + y }`
    - references be named, or _anonymous_
    - arrow syntax
      - `() => { return "Hello" }`
      - `(x, y) => { return x + y }`
      - `x => x * x`

## Object-Oriented Programming

- is a programming paradigm

### Classes

- not really, but class-like
- are objects based on
  _prototypal inheritance_
- ```js
  class Person {
    constructor(name, age) {
      this.name = name;
      this.age = age;
    }
    greet() {
      console.log("Hello, I'm ", name);
    }
  }
  ```

## Functional Programming

- is a programming paradigm
  - which has benefits:
    - less bugs
    - less time
  - functions are values
  - data structures are immutable
- Higher-Order Functions
  - are functions that
    - accept functions
      - and call them, i.e. callback functions
        - which enables _composition_
          - e.g. `arr.filter(x => { x > 5 })`
          - ```js
            var isPositive = (x) => x > 0;
            const positives = arr.filter(isPositive);
            const nonPositives = arr.reject(isPositive);
            ```
    - or return functions
  - `map`
  - `filter`
  - `reduce`
    - ```js
      arr.reduce(
        (accum, current, idx, arr) => nxtAccum,
        initAccum)
      )
      ```
- Closures
- Currying
  - ```js
    const makeAdder = (x) => (y) => {
      x + y;
    };
    const addFive = makeAdder(5);
    console.log(addFive(2)); // 7
    ```
- Recursion
- Promises
  - represents an async. operation
  - has one of three states
    - pending
    - fulfilled
    - rejected
  - to access the (eventual) result of promise,
    register an event handler
  - can be chained with `.then(...)`
- Functors
- Streams
- Monad

## Logging

- always keep developer console open in browser
- `console.log("obj is ", obj)`
  - use commas, not `+`
- `debugger;` statements
- Chrome Developer Tools:
  - `cmd + opt + i` to open
  - keep Console tab open most of the time
  - Sources tab for stepping through code
  - Recommended: React developer tools
    Chrome extension
