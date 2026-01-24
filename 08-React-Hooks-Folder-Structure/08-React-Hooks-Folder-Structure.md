<img src = "https://github.com/ghostfriend505/Working-with-React/blob/main/React%20Intro.png">


# React Hook & Folder Structure 

## 1. Analysis of Folder Structure (Why It Matters)

A clean folder structure makes your project:

- easy to understand
- easy to scale
- easy to debug
- professional

Recommended Vite structure:

    src/
     ├── components/
     ├── hooks/
     ├── pages/
     ├── App.jsx
     └── main.jsx

Why this is important:

- Components stay reusable
- Hooks stay reusable
- Pages stay clean
- Logic is separated from UI
- Team work becomes easy

## 2. What are React Hooks?

Hooks are special functions provided by REact that let you see:

- state
- lifecycle
- side effects
- content

inside functional conponents

Before hooks, only class components could do this.

Now functional components can do everything - and better

### Why Hooks Exist 

- Remoce class components
- Reduse code
- Shara logic easily
- Make code readable
- Avoid complex lifecycle methods
- Reuse logic
- Avoid this keyword
- Easier testing
- Better performance
- Modern standard


## 3. Types of Hooks in React

1. Basic Hooks

- useState -> manage state
- useEffect -> lifecycle & side effects
- useContext -> share data globally
   
2. Additional Hooks

- useRef -> reference DOM
- useMemo -> optimize performance
- useCallback -> optimize functions
- useReducer -> complex state
  
3. Custom Hooks

- your own reusable hooks
- start with use

## 4. useState Example

``` bash

const [count, setCount] = useState(0)

```

- stores data
- updates UI
- re-renders component

## 5. useEffect (Lifecycle Hook)

``` bash

useEffect (() => {
  console.log('Component mounted')
}, [])

```

Used for:

- API calls
- subscriptions
- timers
- cleanup

## 6. useRef (Access DOM)

``` bash

import {useRef} from 'react'

function App() {
  const inputRef = useRef()

  return (
    <>
      <input ref={inputRef} />
      <button onClick={() => inputRef.current.focus()}>
        Focus
      </button>
    </>
  )
}

```

## 7. Custom Hooks (Very Important)

Custome hooks let you reuse logic.

#### hooks/useCounter.js

``` bash

import {useState} from 'react'

export function useCounter() {
  const [count, setCount] = useState(0)

  const inc = () => setCount(c => c + 1)
  const dec = () => setCount(c => c - 1)

return {count, inc, dec}

}

```

Use it:

``` bash

const {count, inc, dec} = useCounter()

```

## 8. React Rendering

React re-renders when:

- state changes
- props changes
- parent re-renders

React uses Virtual DOM to update only what changed.

## 9. Data Passing in React

Parent -> Child (props)

``` bash

<Child name="Ujjwal" />

```

Child -> Parent (callBack)

``` bash

<Child onClick - {handleClick} />

```
## Short Questions

Q1. What will happen if you render an input element with disabled = {false}

Q2. What is used to pass data to a component from outside n React?

Q3. Why hooks are better than classes?

Q4. What is custom hook?

Q5. Which hook handles lifecycle?

## Long Question 

Q1. Why React hooks was introduced?

## Short Answers

A1. It will be rendered as enabled.

A2. Props

A3. Less code, no this, easier logic reuse.

A4. A reusable hook made by developers

A5. useEffect

## Long Ansewer

A1. One reason to introduce hooks as the complexity in dealing with this keywaord inside class
conponents. If not handled properly, this will take some other value. That will result in 
breaking lines like this.setState() and other event handlers. Using hooks, we avoid that
complexity when working with functional components. 
