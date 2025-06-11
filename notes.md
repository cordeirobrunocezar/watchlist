[Getting Started](https://nextjs.org/docs/app/getting-started)
->
[Essential JavaScript for React](https://nextjs.org/learn/react-foundations/getting-started-with-react#essential-javascript-for-react)

# React core concepts
- Components
- Props
- State

## Components
- Smaller building blocks

    allows to build self-contained, reusable snippets of code

```
function Header() {
    return <h1>Develop. Preview. Ship.</h1>;
}
```

- should be capitalized to distinguish them from plain HTML and JavaScript
- angle brackets <>

    `root.render(<Header />)`


### Nesting Components

```
function HomePage() {
    return (
        <div>
            <Header />
        </div>
    )
}
```

## Props
- custom arguments

    that changes the component's behavior or what is visibly shown when it's rendered to the screen

    you can pass down theses props from parent components to child components

*data flows down the component tree (one-way data flow)*

- [Desestructuring](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Operators/Destructuring) to explicitly name the values of props inside your function parameters

```
function Header({ title }) {
    console.log(title)
    return (<h1>title</h1>)
}
```

*to write regular JavaScript directly inside your JSX markup add **curly braces** {}* : JavaScript expression (something that evaluates to a single value) = 
- object property with dot notation
- template literal
- returned value of a function
- ternary operators

# Iterating through lists
- array methods

*React needs something to uniquely identify items in an array so it knows which elements to update in the DOM* : it's recommended to use something guaranteed to be unique, like an item ID.

*arrow function*

# State and event handlers

## Listening to events
- event names are camelCased
onClick

## States and hooks
- set of functions called **hooks**

    allows to add additional logic such as **state** to your components

*state as in any information in your UI that changes over time, usually triggered by user interaction*

[State and hooks](https://nextjs.org/learn/react-foundations/updating-state#state-and-hooks)

[Managing state](https://nextjs.org/learn/react-foundations/updating-state#managing-state)

    learn more about managing state and data flow in React applications

*Props are read-only information that's passed to components. State is information that can change over time, usually triggered by user interaction.*

[From React to Next.js](https://nextjs.org/learn/react-foundations/from-react-to-nextjs#from-react-to-nextjs)

export default : help Next.js distinguish which component to render as the main component of the page

*npx next telemetry disable*

*npm run dev*

# Differences between Server and Client Components
[Server and client components](https://nextjs.org/learn/react-foundations/server-and-client-components)
- environments (where the application code can be executed in - server and client)
- network boundary (that separates server and client code)

![alt text](learn-client-and-server-environments.avif)

- client: browser on a user's device

    sends a request to a server for your application code then turns the response it receives from the server into an interface the user can interact with

- server: computer in a data center that stores your application code

    receives requests from a client and sends back an appropriate response after computation

certain operations (data fetching or managing user state) are better suited for one environment over the other

# Network Boundary
- conceptual line that separates the different environments

    you choose where to place the network boundary in your component tree in React

![alt text](learn-client-server-modules.avif)

the components are split into two module graphs
- **server module graph** (or tree): contains all the Server Components that are rendered on the server
- **client module graph** (or tree): contains all Client Components

after server components are rendered

React Server Component Payload (RSC) is sent to the client:
a special data format that contains:
- the rendered result of Server Components
- placeholders (or holes) for where Client Components should be rendered and references to their JavaScript files

*React uses this information to consolidate the Server and Client Components and update the DOM on the client*

# [Using Client Components](https://nextjs.org/learn/react-foundations/server-and-client-components#using-client-components)

*Next.js uses Server Components by default - this is to improve your application's performance and means you don't have to take additional steps to adopt them.*

- 'use client'; directive at the top of the file

- [Summary and additional reading](https://nextjs.org/learn/react-foundations/server-and-client-components#summary)

# [App Router](https://nextjs.org/learn/dashboard-app)
- https://nextjs.org/learn/dashboard-app/getting-started

# [CSS Styling](https://nextjs.org/learn/dashboard-app/css-styling)
- add a global CSS file to your application
- Tailwind and CSS modules
- conditionally add class names with the clsx utility package

    https://nextjs.org/docs/app/getting-started/css
