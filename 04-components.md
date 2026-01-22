<img src = "https://github.com/ghostfriend505/Working-with-React/blob/main/React%20Intro.png">

# Components in ReactJS (Vite Based)

  - Note: in this course we are using Vite.

      You should use it too, because it is faster, cleaner and is the modern standards for React
      apps.


## What is a Component in React?

A component is a reusable piece of UI in React.

Insted of writting HTML in one big file, React lets us divide the UI into small parts which we 
call Components.

Each component:

- has it's own responsibility
- can be used as many times as we want
- makes code easier to read
- makes large apps easy to manage

For example, in a website

- Navbar is a component
- Button is a component
- Card is a component
- Footer is a component

React apps are build by joinning small components togther.
This makes the app easier to maintain. update, and debug.

## Why Components are Used

#### Components are used becase they:

1. Break big UI into small pieces
2. Make code reusable (we can use as many times as we want)
3. Reduce repetition (DRY principle)
4. Make code easier to understand
5. Make testing easier
6. Improve readability
7. Make UI logic separate from business logics
8. Allow faster development
9. Make apps scalable

Without components. React app would become messy very quickly.

## Types of Components in React

There are two main types of Components in React.

1. Functional Component
2. Class base Component

### 1. Functional Components (Modern & Recommended)

Functional components are simple JSS functions that return JSX (UI).

They are:

- easy to write
- easy to learn
- easy to read
- widely used in mordern apps
- support hooks(state, lifecycle, etc.)

#### Example

      function Welcome() {
      return <h1> Hello React </h1>
      }

### 2. Class Components (Old Style)

Class coponents are JSS classes that extends React.component.

They were used before hook existed.

Now they are mostly found in old projects.

#### Example

      class Welcome extends React.Component {
      render () {
      return <h1> Hello React </h1>
        }
      }

They are:

- harder to read
- longer
- confusing for beginners
- not recommended for new projects

  
## Class vs Functional Components Difference

    Functional Components                  Class Components

    Simple function                         JavaScript class
    Less code                               More code
    Uses hooks                              Uses lifecycle methods
    Easy to Learn                           Hard to learn
    Mordern standards                       Old approach
    Recommended                             Not recommended

Always use functional components for new projects


## What are Nested Components?

  Nested Components mean: Using one component inside another component.

  Example

        <App> 
          <Header>
            <Button />
          </Header>
        </App>

Here:

- Button is inside Header
- Header is inside App
- This creates a component tree

### Why nesting is important 

- Real apps are made of layers
- Makes UI organized
- Reuse smaller components indie bigger ones
- Improve readability

Every React app is a tree of nested components.


## Controlled Components

### What is a Controlled Component?





## How Components Work in Vite

In a Vite projects: 

        main.jsx → App.jsx → Components → UI

- main.jsx starts the app
- App.jsx is root component
- Other components are children
- React renders everything into browser

  ## What is Props?

  Props are used to pass data from parent components to child component.

  They make components dynamic and reusable.

  Without props, every component whould show the same data.

####  Example:

        <user name="Ujjwal" role = "Learner" />

  Props:

  - flow one way (parent to child)
  - are read-only
  - help reuse components
  - make UI flexible
 
  ## What is State?

  State is data that belongs to component and change over time.

  State is used for:

  - counters
  - form input
  - toggles
  - API data
  - UI changes

   #### Example

         const [count, setCount] = useState(0)

  When state changes:

  React re-renders the component automatically.

  State makes React interactive.


  ## Props vs State


        Props                                                State

        Passed from parent to child                           Owned by component
        Read-only                                             Can be edited
        Used for data                                         Used for interaction
        External                                              Internal



  ## Why All This Matters

  Components + Props + State together:

  - Build UI
  - Manage data
  - Handle interaction
  - Keep code clean
  - Make React powerful
    
This is core of React.

If you underestand this, everything else becomes easy.


# Project Structure 

##  All concepts have been explained above. The complete related code is provided below.

### Project Structure

    vite-react-course/
     ├── index.html
     └── src/
      ├── main.jsx
      ├── App.jsx
      └── components/
           ├── Header.jsx
           ├── Button.jsx
           ├── User.jsx
           ├── Counter.jsx
           └── Card.jsx


### 1. Entry File (Remeber all the code is in Vite)

#### src/main.jsx

      import React from 'react'
      import ReactDOM from 'react-dom/client'
      import App from '/.App.jsx'

      ReactDOM.createRoot(document.getElementById('root')).render (
      <React.StrictMode>
        <App />
      </React.StrictMode>
      )
      
### App.jsx

    import Header from './components/Header.jsx'
    import User from './components/User.jsx'
    import Counter from './components/Counter.jsx'
    import Card from './components/Card.jsx'

    function App () {
    return (
    <div>
      <Header />

      <user = "Ujjwal" role="React Learner" />

      <Counter />

      <Card title="React" desc="React is a component based library" />
      <Card title="Vite" desc="Vite makes React fast and clean" />
      
    </div>
    )
    }

    export default App


### Nested Components Example

#### components/Header.jsx

    import Button from './Button.jsx'

    function Header () {
      return (
        <header>
          <h1> React Course (Vite) </h1>
          <Button text ="Logout" />
        </header>
      )
    }      

    export default Header

 ### Reusable Component with Props

 #### components/Button.jsx

    function Button({ text }) {
          return <button>{text}</button>
    }

    export default Button

### Props  Example

#### components/User.jsx

    function User({ name, role }) {
    return (
      <div>
        <h2>Name: {name}</h2>
        <p>Role: {role}</p>
      </div>
      )
    }

    export default User

  
### State Example

#### components/Counter.jsx

    import { useState } from 'react'

    function Counter() {
      const [count, setCount] = useState(0)

      return (
        <div>
          <h2>Count: {count}</h2>
          <button onClick={() => setCount(count + 1)}>+</button>
          <button onClick={() => setCount(count - 1)}>-</button>
        </div>
      )
    }

    export default Counter

### Nested + Props Example

#### components/Card.jsx

    function Card({ title, desc }) {
      return (
        <div>
          <h3>{title}</h3>
          <p>{desc}</p>
        </div>
      )
    }

    export default Card


## What This Projext Shows

- Functional components
- Nested components
- Props usage
- State usage
- Reusable components
- Vite project structure
- Real React patterns


  ## Data Flow in This Code

      App (state/props)
              ↓
      Components (props)
              ↓
      User interaction
              ↓
      State update
              ↓
      UI refresh


  ## How to Run

      npm create vite@latest vite-react-course
      cd vite-react-course
      npm install
      npm run dev


## Concept Questions

Q1. What is a component in React?

Q2. Why do we use components?

Q3. What are props in React?

Q4. What is state in React?

Q5. What is the difference between props and state?

Q6. What are nested components?
      
Q7. Which component type is recommended today?

Q8.  How does component lifecycle works?
   

## Short Questions 

1. A State in React.Js is also known as... 
2. In React what is used to pass data to a component from outside? 
3. A valid react component can return only ......... element.  
4. What is the “key” prop in React?
5. How can you access the state of a component from inside of a member function in React? 
6. For controlled components in react: 



## Anwers 

A1. A component is a reusable piece of UI in React. It helps split the user interface into small, manageable parts so the code is clean, reusable, and easy to maintain.

A2. We use components to reuse code, organize UI, make apps scalable, and make development faster and easier to manage.

A3. Props are used to pass data from a parent component to a child component. They make components reusable and dynamic. Props are read-only.

A4. State is data that belongs to a component and can change over time. When state changes, React automatically updates the UI.

A5. Props are passed from parent to child and cannot be changed, while state is managed inside a component and can be updated.

A6. Nested components are components used inside other components. They help build complex UI by combining small components together.

A7. Functional components are recommended because they are simpler, cleaner, and work with hooks like useState and useEffect.

A8. It’s worth mentioning that React internally has a concept of phases when applying changes to the DOM, including Render, Pre-Commit, and Commit. componentDidMount(),componentDidUpdate(),
    componentWillUnmount() belongs to the “Commit” phase.

## Short Answers 

1. Internal Storage

2. props

3.  1

4.   “key” prop to identify any new item in a list when re-rendering. It’s for the purpose of higher performance and efficiency

5.   this.values

6.   Source of truth is component state for controlled components.




