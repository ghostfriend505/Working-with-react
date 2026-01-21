<img src = "https://github.com/ghostfriend505/Working-with-React/blob/main/React%20Intro.png">


<h1> Let's Learn React Js</h1>

<h3>What is React Js? </h3>

  React.js is an open-source JavaScript library that is used for building user interfaces specifically
  for single-page applications. It's used for handling the view layer for web and mobile apps.
  React also allows us to create reusable UI components, React was first created by Jordan Walke, 
  who was a software engineer working for Facebook. 

  React allows developers to create large web applications that can change data without reloading the page.
  The primary purpose of React is to be fast, and straightforward.

  React Js is also called simply React or React.Js

<h3> What are the React.js Features? </h3>

  Let us take a closer look at features of React.

  React.Js is Easy to Learn, Simple, Component-bases, declarative. extensive, fast etc..

<h3>JSX </h3>

  In React, insted of using regular JavaScript, it uses JSX. JSX is a simple JavaScript that 
  allows HTML  quoting and uses HTML tags syntax to render components. HTML syntax 
  is processed into JavaScript calls of React FrameWork.

<h3>React Native </h3>

  React-native is a mobile apps building framework using Javascript, It uses the same desing 
  as React, letting you include a rich mobile UI library comoponents. The best part of using
  react-native is to allow components written in Objective-C,java or Swift etc...

<h3>Single-Way data flow</h3>

In React, one-way data flow refers to the movement of data from parent components to child 
components through props. This one way data flow ensures that state and logic are
centralized in parent components, while child components focus on rendering and presentation.
Any update from child to parent components are achived using callback functions.
  
<h3> Virtual Document Object Model </h3>

React creates an in-memory data structure cache that computes the changes made and then 
update the browser. This is a unique feature that allows programmers to code as if the whole 
page is rendered on each time, but react library only renders components that changes.

<h3> Why React Js is popular? </h3>

React is efficient and flexible open-source JavaScript library for building simple, fast and 
scalable fronted of web appications.

<strong> Key Benefits Of React JS as a front-end development application </strong>

🔹 Speed 

🔹 Flexibility 

🔹 Performance

🔹 Usability

🔹 Mobile app development

🔹 It helps to build rich user interfaces 

🔹 It offers fast rendering

🔹 Strong community support

<h3> How Does React Js Works </h3>

<h4> DOM </h4>

 <strong> The Document Object Model (DOM) </strong> 

  1. Represents web page structure
     
     🔹 DOM converts HTML into a tree structure

     🔹 Makes elements easy to access and modify

  3. Dynamic content update

     🔹 You can change text, images, styles without reloading page

  4. Langugae undependent

     🔹 DOM can be manipulated using JSS,Python,etc..

  5. Event handling

     🔹 Handle click, input, scroll, submit events

  6. Real-time interaction

     🔹 Enables interactive websites

  7. Platform independent

     🔹 Works on all browsers and devices

  8. Standardized API

     🔹 Same rules across browsers (W3C standar)


<h4> How DOM Works in React </h4>

1. React uses Virtual DOM

   🔹 React creates a lightweight copy of real DOM

2. State or props change

   🔹 When data changes, React updates Virtual DOM

3. Diffing algorithm

   🔹 React compares new Virtual DOM with old one

4. Find minimum changes

   🔹 Only changed part are identified

5. Efficient update

   🔹 React updates only required elements in real DOM

6. Faster performance

   🔹 Avoids full page re-rendering

7. Component-based updates

   🔹 Only affect components re-render


  <h4>Simple flow chart easy to remember </h4>

    State change
         ↓
    Virtual DOM updated
         ↓
    Diffing
         ↓
    Minimal DOM update

React improves performance by using Virtual DOM to update only changed parts of the real
DOM insted of reloading the entire page.


<h2> Installation Of React JS </h2>

  🔹 <h4> How to Downlode & Install Node.js

   First of all, you are going to need NPM (or YARN, alternative for NPM)
   but NPM is more popular so we will be using NPM for this example.

   If you don't have it installed on your system, then go official website of Node.js 
   [Download Node.js](https://nodejs.org/en/download) and install Node with default settings,
   which also includes NPM (Node Package Manager) 

   After you are done with your downlode and install, start your terminal/cmd prompt and run 
   node-v and npm-v to see versions of NPM and Node you have installed.

  <h4> Downlode VS code  </h4>

  VS code is one of the most popular if not most popular it is easy to install just press 
  on the given link downlode and install with recommended setting that's all 
  [Downlode VS Code](https://code.visualstudio.com/download)
  
  <h3>What is create-react-app? </h3>

  Since it is complicated to configure React manually. That is why we use create-react-app us
  a easier way which does all the things for you from installing necessary package to 
  starts a new React app locally, ready for development.

<h2> Npm Vs. Npx </h2>

<h4> Npm</h4>

  Npm = Node Package Manager 

  🔹 intall packages 
  
  🔹 manage dependencies 

  🔹 run scripts 

  🔹 update libraries 

  Example 
    
    npm install react

<h4>Npx </h4>

 Npx = Node Package Execute

  it is used to:
 
   🔹 run packages without installing them globally 

   🔹 execute CLI tools directly

   🔹 aboid version conflicts

   Example 

     npx create-react-app myapp

  <h4>Simple difference </h4>

        | npm                    | npx                |
      | ---------------------- | ------------------ |
      | Installs packages      | Executes packages  |
      | Needs install          | No install needed  |
      | Stored in node_modules | Temporary run      |
      | Used often             | Used for CLI tools |

<strong> In simple words Npm install packages, while Npx executes pacjages directly without 
installing them gobally. </strong>

<h2>Creating First React App </h2>

<h4> System Setup </h4>

  Once all the above steps are completed, we are ready to proceed.

<h3> Creating A First React Project From Scratch </h3>

  In code editor (Visual Studio), open terminal or press ctrl+shift+` and type 

      npx create-react-app first-app 

  It:

  🔹 creates a new React app

  🔹 names it first-app

  🔹 installs all dependencies

  🔹 sets up everything automatically

  After that: In same terminal type 

      cd first-app
      npm start

  Here you can see that the development web server has been started on
  port 3000. The browser is opened automatically, and URL
  http://localhost:3000 has opened automatically

Congratulations, You have successfully Made your First React App

      











  

  
