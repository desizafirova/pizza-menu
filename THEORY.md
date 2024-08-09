# React

## Strict Mode

- it will render all components twice in order to find certain bugs and if we are using outdated parts of the React API.

## Components

- React applications are entirely made out of components;
- They are the building blocks of User Interfaces in React.
- React renders a view for each component and all these views together make up the user interface.
- Piece of UI that has its own data, logic, and appearance(how it works and looks).
- We build complex UIs by building multiple components and combining them.
- Components can be reused, nested inside each other, an pass data between them.

### Building components in React

- In React we build new components using functions
- The function name should start with upper case letter
- The function needs to return some markup.

### Component trees

## JSX

- Declarative syntax to describe what components look like and how they work.
- It is all about appearance
- Components must return a block of JSX
- Extension of JS that allows us to embed JS, CSS and React components into HTML
- Each JSX element is converted to a React.createElement function call by transpiler/compiler. It is a must do, because browsers do not understand JSX, only HTML. Behind the scenes our JSX code is converted into many nested React.createElement function calls.

What is the difference between Imperative and Declarative syntax?

- Imperative:
  Manual DOM element selections and DOM traversing
  Step-by-step DOM mutations until we reach the desired UI
  Telling the browser exactly how to do things

- Declarative:
  Describe what UI should look like using JSX, based on current data.
  React is a huge abstraction away from DOM: we never touch the DOM
  Instead we thing of the UI as a reflection of the current data
  With this approach we use JSX to tell React what we want to see on the sreen, but not how to achieve it step-by-step. React can figure it out on its own.

### Rules of JSX

#### General rules

- JSX works essentially like HTML, but we can enter "JavaScript mode" by using {} (for text or attributes)
- We can place JS expressions inside {}. Examples: reference variables, create arrays or objects, [].map(), ternary operator;
- Statements are not allowed (if/else, for, switch)
- JSX produces JS expressions:
  We can place other pieces of JSX inside {}
  We can write JSX anywhere inside a component (in if/else, assign to variables, pass it into functions)
- A piece of JSX can only have one root element. If you need more, use <React.Fragment> (or the short <></>)

#### Differences between JSX and HTML

- classname istead of class
- htmlFor istead of for
- Every tag needs to be closed
- All event handlers and other properties need to be camelCased
- Exception: aria-_ and data-_ are written with dashes like in HTML
- CSS inline styles are written like this: {{style}}
- CSS property names are also camelCased
- Comments need to be in {}

## Separation in concerns

### One technology per file - Traditional Separation of Concerns

### One component per file - React

- Each component is concerned with one piece of the UI
- One concern per component

## Props

- How we pass data between parent and child components
- Essential ttool to configure and customize components(like function parameters)
- With props, parent components control how child components look and work
- Anything can be passed as props: single values, arrays, objects, functions, even other components.

### The DATA in the components is made by props and state

#### State is internal data that can be updated by the component's logic

- State is for data that will change over time

#### Props is data comming from the outside, and can only be updated by the parent component

- Props are immutable and read-only!!!
- if you need to mutate props, you actually need state
- Mutating props would affect parent, creating side effects(not pure). Components have to be pure functions in terms of props and state. This allows React to optimize apps, avoid bugs, make apps predictable.

#### React uses a so-called one-way data flow

- That means that data can only be passed from parents to child components, which happens by using props.

## React Fragment

- Allows us to group several elements together without leaving any trace in the HTML tree.
- <React.Fragment key="something"></React.Fragment> in cases when we render lists
- Shorthand syntax <></>
