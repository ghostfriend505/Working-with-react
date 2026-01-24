<img src = "https://github.com/ghostfriend505/Working-with-React/blob/main/React%20Intro.png">


# Events in ReactJS 

  - Note: In this course, we are using Vite.


## 1. What are Events in React?

  Events in React are actions that happen when a user interacts with the application.

  Examples of events:

  - clicking a button
  - typing in an input
  - submitting a form
  - hovering over and element
  - pressing a key

  In simple words:

  |  Events allow users to communicate with your React application.

  ##### Without events:

  - buttons do nothing
  - forms don't work
  - UI is not interactive
  - apps feel dead


## 2. Why Events are Important

Events are important because they:

 - Make UI interactive
 - Connect user actions to logic
 - Allow state changes
 - Control application behavior
 - Trigger re-renders
 - Handle forms
 - Handle validation
 - Handle animations
 - Make apps feel alive

   React without Events is just HTML with style.

## 3. How Events Work in React

React uses Synthetic Events.

That means:

- events work same on all browsers
- React wraps native events
- better performance
- consistent behavior

  Syntax:

      <button onCick={handleClick}> Click </button>

  Notice:
  - cameCase (onClick)
  - function, not string
  - no parentheses


## 4. Basic Event Eample

  App.jsx

      function App () {
        const handleClick= () =>
          alert ('Button Clicked')
      }

      return (
          <button onClick= {handleClick}>
            Click Me
          </button>
        )
      )
      export default App

## 5.Event with State (Common use)

      import {useState} from 'react'

      function App () {
       const [count, setCoutn] = useState (0)
  
        return (
           <div>
           <p>Count: {count}</p>
           <button onClick={() => setCount(count + 1)}>+</button>
         </div>
           )
         }

Event + State = Interactive React App

## 6.Passing Events as Props (Important)

  This allows child components to talk to parent.

  Button.jsx

    function Button ({onClick, text }) {
      return <button onClick={onClick}> {text} </button>
    }

    export default Button


  App.jsx

    import {useState} from 'react'
    import Button from './Button.jsx'

    function App() {
      const [msg, setMsg] = useState('')

      return (
        <div>
          <Button text="Login" onClick={() => setMsg('Login clicked')}  />
          <p> {msg} </p>
        </div>
      )
    }

## 7. Event Object (e)

  React automatically passes event object:

    function handleChage(e) {
     console.log(e.target.value)
    }

Used mostly in forms.

#### What is (e) in React Events?

In React. (e) is the event object.

It contains information about what just happned in the browser.

When a user interact with the UI (click,type,submit) React automatically creates and event
object and sends it to your function.

#### What does (e) contain

The event object has:

- which element was clicked
- what key was pressed
- input value
- mouse position
- event type
- and much more

But the most common thing we use is:

    e.target.value

#### Why (e.target.value) is used

Example:

    <input 
      value = {name}
      onChange={(e) => setName(e.taget.value)}
      />
here:

- e.target -> the input element
- value -> what the user typed

  So React reads :

  "When input changes, store what the user typed in state"


#### Summary 

    | Code             | Meaning                      |
    | ---------------- | ---------------------------- |
    | `e`              | event object                 |
    | `e.target`       | element that triggered event |
    | `e.target.value` | value of input               |
    | `onChange`       | input event                  |

#### one line

(e) is the event object that gives React information about user interaction.

I have explained about (e) in detail because I used to struggle with it a lot. 
  
## 8. Controlled Input Event Example

    import {useState} from 'react'

    functiono App () {
     const [name, setName] = useState('')

     return (
       <input
         value = {name}
         onChange= {(e) => setName(e.target.value)}
        />
     )
    }

 React fully controls the input

 ## 9. Form Submit Event

     function handleSubmit(e) {
      e.preventDefault ()
      console.log('Form submitted')
     }

     <form onSubmit={handleSubmit}>
       <button type="submit"> Submit </button>
    </form>
       

## 10. Common Events in React

    | Event       | Use           |
    | ----------- | ------------- |
    | onClick     | button clicks |
    | onChange    | input change  |
    | onSubmit    | form submit   |
    | onMouseOver | hover         |
    | onKeyDown   | keyboard      |
    | onFocus     | input focus   |
    | onBlur      | input blur    |


### Common Mistakes

Wrong

    onClick={handleClick()}

Correct

    onClick={handleClick}


# Full Example 


#### App.jsx

    import {useState} from 'react'

    function App() {
      const [text, setText] = useState('')
      const [list, setList] = useState([])

      const addItem = () => {
        setList ([...list, text])
        setText('')
      }
  
      return (
        <div>
          <input
            value={text}
            onChange={(e) => setText(e.target/value)}
          />

          <button onClick= {addItem}> Add </button>

          <ul>
              {list.map((item, i) => (
                <li key={i}> {item} </li>
              ))}
          </u>
        </div>
      )
    }

    export default App

    
## Exercise

Q1. What is an event in React?

Q2. Why do we use events?

Q3. What are Event Handlers in React.js? 

Q4. What is the onClick handler in React?

Q5. Write a button click event

Q6. Write a controlled input

## 1 line answer

Q1. In React, which is the object on which the event occurred or with which the event is 
    associated?  

Q2. When will the browser invoke the handler in React? 

Q3. In JavaScript, the process by which the browser decides which objects to trigger event 
    handlers on is?      

Q4. In React, the high-level events among the following events are ___________ 


## Answer

A1. An event is an action triggered by user interaction like click, type, or submit.

A2. To make UI interactive and connect user actions to logic.

A3.  Event handlers determine what action is to be taken whenever an
     event is fired. This could be a button click or a change in a text input.
     Essentially, event handlers are what make it possible for users to interact with
     your React app

A4.  The React onClick event handler enables you to call a function and
     trigger an action when a user clicks an element, such as a button, in your app.

A5. <button onClick={() => alert('Clicked')}>Click</button>

A6. <input value={name} onChange={(e) => setName(e.target.value)} />


## 1 line Answer

A1.   Event target

A2.   Specified event occurs

A3.   Event propagation

A4.   User Interface Event


