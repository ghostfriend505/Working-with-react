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


  A comtrolled component is a form element (input, textarea, select) whose value is controlled
  by React state insted of DOM.

  In simple words:

  React controls the input, not the browser.

### Why Controlled Components are Needed 
  
  1. React always knows the input values
  2. Data is stored in state (single source of truth)
  3. Easy to validate input
  4. East to reset input
  5. East to submid form data
  6. East to debug
  7. Works well with React logic
  8. Ui always matches data etc..


#### Example of Controled Component (Vite)

    import {useState} from 'react'

    function App () {
      const [name, setName] = useState('')

      return (
        <div>
          <h2> Controlled Input </h2>

          <input 
            type="text"
            value={name}
            onChange={(e) => setName{e.target.value}}
          />

          <p> You Tyoed: {name} </p>
        </div>
      )
    }

    export default App


  ### What's happning 

  - value={name} -> React controls input
  - onChange -> updates state
  - state ipdates -> UI updates


## Uncontrolled Conponent 

    <input type="text" />

React does not control this input.

We avoid this in real apps.


## Component Lifecycle 

### What is Component Lifecycle?

The lifecycle of a component is the seires of steps a component goes through:

1. Created
2. Rendered
3. Updated
4. Removed

   Every React component has a lifecycle.

### Lifecycle Phases 

#### 1. Mounting (Component appears)

- Component is created
- Rendered on screen
- useEffect(() => {}, []) runs here

#### Updating (Component changes)

- State changes
- Props change
- Re-render happens
- useEffect runs again

#### Unmounting (component removed)

- Component is destroyed
- Cleanup happens
- Memory is clered

### Lifecycle in Functional Components 

In functional components, we use useEffect to control lifecycle.


#### Example: Lifecycle with useEffect

    import { useEffect, useState} from 'react'

    function App () {
      const [count, setCount] = useState(0)

      useEffect (() => {
        console.log('Component mounted')

        retur () => {
          console.log ('Component unmounted')
        }
       }, [])
    }

    return (
      <div>
        <h2> Count: {count} </h2>
        <button onClick={() => setCount(count+1)}> + </button>
      </div>
    )
    
    export default App

## How useEffect works

    | Code                           | Meaning                 |
    | ------------------------------ | ----------------------- |
    | `useEffect(() => {})`          | Runs on every render    |
    | `useEffect(() => {}, [])`      | Runs once (mount)       |
    | `useEffect(() => {}, [count])` | Runs when count changes |
    | `return () => {}`              | Cleanup (unmount)       |

Think of a component like a person:

- Born -> Mounting
- Grows -> Updating
- Dies -> Unmounting

  #### Why Lifecycle is Important

  - Fetch API data
  - Add event listeners
  - Clean up memory
  - Stop timers
  - Handle side effects

## Summary 

#### Controlled Component

  An input element controlled by React state.

#### Lifecycle

  The stages of a component goes through from creation to removal.

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

## What is KEY in React?

A key is a special attribute used by React to uniquely identify elements in a list.

It helps React understand:

- which items changed
- which items were added
- which items were removed

  Keys make React fast and efficient


## Why React Needs Keys

When you render a list, React creates many similar components:

    <li>Apple</li>
    <li>Banana</li>
    <li>Mango</li>

if the list changes, React gets confused

- Which one moved?
- Which one changed?
- Which one should be removed?

  So fo that reason React used key as IDs to track each item.

### Example without key

        {items.map(item => (
          <li> {item} </li>
        ))}

  React will show a warning

  And performance will be poor.
  
### Example with key

      {item.map(item => (
      <li key={item.id}> {item.name} </li>
      ))}
      
Now React knows exactly which item is which

## What Happens Internally

React compares old list vs new list

    key=1 → same item
    key=2 → same item
    key=3 → removed
    key=4 → added

  React updates only what changed insted of re-rendering everything.

  ## Key Rules 

  1. Keys must be unique
  2. Keys must be stable should not change
  3. Use id from data, not index
  4. Keys are used by React, not passed as props
  5. Only needed in lists


 ## Wrong key (index - avoid) 

     items.map((item, index) => (
     <li key={index}>{item}</li>
     ))

This causes bugs when list order changes.

## Best key (id)

    items.map(item => (
    <li key={item.id}>{item.text}</li>
    ))

## Full Example (Vite)

    function App () {
      const user = [
        {id: 1, name: 'Ujjwal'}.
        {id: 2, name: 'Amit'}.
        {id: 3, name: 'Rahul'}
      ]

      return (
        <ul>
            {user.map (user => (
              <li key={user.id}> {user.name} </li>
            ))}
        </ul>
      )
    }

    export default App


## Why Key is Important 

  Key help React identify elements uniquely so it can update only the changed item effciently.

## One-line Summary

  A key is a unique identifier that helps React update lists efficiently.



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

## Final Exercise 

### Question 

#### Create a User List App using Vite + React that:

Requirements:

1. Use functional components only
2. Create a UserList component
3. Create a Useritem nested component
4. Use props to pass user data
5. Use state to manage users
6. Add a controlled input to add new users
7. Use key when rendering list
8. Use useEffect to lof when component mounts
9. Keep code clean and reusable


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

## Code Answer

### Project Structure

    components/
     └── src/
      ├── main.jsx
      ├── App.jsx
      └── components/
           ├── UserList.jsx
           └── UserItem.jsx

 #### - main.jsx 
        
        import React from 'react'
        import ReactDOM from 'react-dom/client'
        import App from './App.jsx'

        ReactDOM.createRoot(document.getElementById('root')).render(
        <React.StrictMode>
          <App />
        </React.StrictMode>
        )

#### - App.jsx

    import { useState } from 'react'
    import UserList from './components/UserList.jsx'

    function App() {
      const [users, setUsers] = useState([
        { id: 1, name: 'Ujjwal' },
        { id: 2, name: 'Rahul' }
      ])

      const [newUser, setNewUser] = useState('')

      const addUser = () => {
        if (newUser.trim() === '') return

        setUsers([
          ...users,
          { id: Date.now(), name: newUser }
        ])
        setNewUser('')
      }

      return (
        <div>
          <h1>User List App</h1>

          <input
            type="text"
            value={newUser}
            onChange={(e) => setNewUser(e.target.value)}
            placeholder="Enter name"
          />

          <button onClick={addUser}>Add User</button>

          <UserList users={users} />
        </div>
      )
    }

    export default App

#### UserList.jsx

    import UserItem from './UserItem.jsx'
    import { useEffect } from 'react'

    function UserList({ users }) {
      useEffect(() => {
        console.log('UserList component mounted')
      }, [])

      return (
        <ul>
          {users.map(user => (
            <UserItem key={user.id} name={user.name} />
          ))}
        </ul>
      )
    }

    export default UserList

#### UserItem.jsx

    function UserItem({ name }) {
      return <li>{name}</li>
    }

    export default UserItem

## Concepts used

    | Concept              | Used  |
    | -------------------- | ----  |
    | Component            | ✅    |
    | Functional component | ✅    |
    | Nested component     | ✅    |
    | Props                | ✅    |
    | State                | ✅    |
    | Controlled component | ✅    |
    | useEffect lifecycle  | ✅    |
    | key                  | ✅    |
    | Vite structure       | ✅    |

 ### Explanation (What This Proves)

  This app shows:

   - how data flows from parent to child

   - how state controls UI

  - how controlled inputs work

  - how React tracks list items using keys

  - how lifecycle works with useEffect

how small components build big apps
