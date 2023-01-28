# 30 Days of JS

## Day - 3

## What is JSX?

### ✨3.1 What is JSX?✨

JSX is an syntax extension for JavaScript. It was written to be used with react. JSX looks a lot like HTML.

**Q. What does syntax extension mean?**
-> In this case, it means that JSX is not valid JavaScript. Web Browsers can't read it.

If a JavaScript file contains JSX code, then that file will have to be compiled. That means that before the file reaches the web browser, a JSX compiler which will translate any JSX into regular JavaScript.

### 🔥JSX Elements 🔥

A Basic Unit of JSX is called as JSX Element.

E.g -> `<h1>Hello World</h1>`

This JSX Element looks like HTML! The only noticeable difference is that if you would find it in a JavaScript File, instead of HTML File.

### 🪖JSX Elements And Their Surroundings 🪖

JSX Elements are treated as JavaScript Expressions. They can go anywhere that you would find it in a Javascript expressions can go.

That means that JSX Element can be saved in a variable, passed to a function, stored in a Object or Array .. you name it.

Here's a example of a JSX Element being saved in a state variable ->

`const navbar = <nav>I am a nav bar</nav>`

Here's an example of se several JSX elements being stored in an object ->

```javascript
const myTeam = {
	center: <li>Benzo Walli</li>,
	powerForward: <li>Rasha Loa</li>,
	smallForward: <li>Tayshun Dasmoto</li>,
	shootingGuard: <li>Colmar Cumberbatch</li>,
	pointGuard: <li>Femi Billion</li>,
};
```

### 🎖️JSX elements can have attributes, just like HTML elements can. 🎖️

A JSX attribute is written using HTML-like Syntax: a name, followed by an equals sign, followed by a value. The value shuld be wrapped in quotes, like this: `my-attribute-name="my-attribute-value"`

Here are some JSX elements with attributes:
`<a href='http://www.example.com'>Welcome to the Web</a>;`
`const title = <h1 id='title'>Introduction to React.js: Part I</h1>;`

A single JSX element can have many attributes, just like in HTML: 🐼
`const panda = <img src='images/panda.jpg' alt='panda' width='500px' height='500px' />;`

### 🧃You can nest JSX elements inside of other JSX elements, just like in HTML🧃

Here’s an example of a JSX `<h1>` element, nested inside of a JSX `<a>` element:
`<a href="https://www.example.com"><h1>Click me!</h1></a>`

To make this more readable, you can use HTML-style line breaks and indentation:
`<a href="https://www.example.com">  <h1>    Click me!  </h1></a>`

If a JSX expression takes up more than one line, then you must wrap the multi-line JSX expression in parentheses. This looks strange at first, but you get used to it:

```html
(
<a href="https://www.example.com">
	<h1>Click me!</h1>
</a>
)
```

Nested JSX expressions can be saved as variables, passed to functions, etc., just like non-nested JSX expressions can! Here’s an example of a nested JSX expression being saved as a variable:

```javascript
const theExample = (
	<a href='https://www.example.com'>
		<h1>Click me!</h1>
	</a>
);
```

### 🤖JSX Outer Elements🤖

There’s a rule that we haven’t mentioned: a JSX expression must have exactly one outermost element.
E.g:-
`const paragraphs = ( <div id="i-am-the-outermost-element"> <p>I am a paragraph.</p>`

`<p>I, too, am a paragraph.</p>  </div>);`

But the above code will not work:

`const paragraphs = (  <p>I am a paragraph.</p>   <p>I, too, am a paragraph.</p>);`

The first opening tag and the final closing tag of a JSX expression must belong to the same JSX element!

It’s easy to forget about this rule, and end up with errors that are tough to diagnose.

If you notice that a JSX expression has multiple outer elements, the solution is usually simple: wrap the JSX expression in a

.

### 🧳Rendering JSX🧳

You’ve learned how to write JSX elements! Now it’s time to learn how to render them.

To render a JSX expression means to make it appear onscreen.

## ReactDOM.render()

### 🥏 3.2 ReactDOM.render() 🥏

Let’s examine the code that you just wrote in the last exercise.

`ReactDOM.render(<h1>Render me!</h1>, document.getElementById('app'));`

You can see something called ReactDOM. What’s that? ReactDOM is the name of a JavaScript library. This library contains several React-specific methods, all of which deal with [the DOM](https://codedamn.com/news/javascript/dom-model-in-javascript-complete-guide) in some way or another. We’ll talk more later about how ReactDOM got into your file. For now, just understand that it’s yours to use.

Move slightly to the right, and you can see one of ReactDOM‘s methods: ReactDOM.render(). ReactDOM.render() is the most common way to render JSX. It takes a JSX expression, creates a corresponding tree of DOM nodes, and adds that tree to the DOM. That is the way to make a JSX expression appear onscreen. Move to the right a little more, and you come to this expression:

`<h1>Hello world</h1>`

This is the first argument being passed to ReactDOM.render(). ReactDOM.render()‘s first argument should be a JSX expression, and it will be rendered to the screen. We’ll discuss the second argument in the next exercise!

### 🪂Further readings 🪂 Move to the right a little more, and you will see this expression

`document.getElementById('app')`

You just learned that `ReactDOM.render()` makes its first argument appear onscreen. But where on the screen should that first argument appear?

The first argument is appended to whatever element is selected by the second argument. In the code editor, select index.html. See if you can find an element that would be selected by `document.getElementById('app')`.

That element acted as a container for ReactDOM.render()‘s first argument! At the end of the previous exercise, this appeared on the screen:

```HTML
<main id="app">
    <h1>Render me!</h1>
</main>
```

### 😶‍🌫️Passing a variable to DOM😶‍🌫️

ReactDOM.render()‘s first argument should evaluate to a JSX expression, it doesn’t have to literally be a JSX expression.

The first argument could also be a variable, so long as that variable evaluates to a JSX expression. In this example, we save a JSX expression as a variable named toDoList. We then pass toDoList as the first argument to ReactDOM.render():

const toDoList = (

 <ol>
<li>Learn React</li>
<li>Become a Developer</li>  
 </ol>
);

ReactDOM.render( toDoList, document.getElementById('app'));
🍱The Virtual DOM🍱
One special thing about ReactDOM.render() is that it only updates DOM elements that have changed. That means that if you render the exact same thing twice in a row, the second render will do nothing:

const hello = <h1>Hello world</h1>;

// This will add "Hello world" to the screen:
ReactDOM.render(hello, document.getElementById('app'));

// This won't do anything at all:
ReactDOM.render(hello, document.getElementById('app'));
This is significant! Only updating the necessary DOM elements is a large part of what makes React so successful. React accomplishes this thanks to something called the virtual DOM. Before moving on to the end of the lesson, read [this article about the Virtual DOM](https://codedamn.com/news/reactjs/how-react-works).

### 🥊JSX Recap 🥊

Congratulations! You’ve learned to create and render JSX elements! This is the first step towards becoming fluent in React. In the next lesson, you’ll learn some powerful things that you can do with JSX, as well as some common JSX issues and how to avoid them.

## Import React

### 🗿3.3 Import React🗿

Wooo! Your first React component!

In the last exercise, we started by importing from react. The line that did this is:

`import React from 'react';`

This creates an object named React which contains methods necessary to use the React library.

Later, we’ll go over where the React library is imported from, and how the importing process works. For now, just know that this is how we import the React library.

You’ve already seen one of the methods contained in the React library: `React.createElement()`. Recall that when a JSX element is compiled, it transforms into a `React.createElement()` call.

For this reason, you have to import the React library, and save it in a variable named React, before you can use any JSX at all. React.createElement() must be available in order for JSX to work.

### 💽Import ReactDOM💽

In order to create our first component, we next imported the ReactDOM:

`import ReactDOM from 'react-dom';`

This line of code is very similar to line 1.

Both import JavaScript objects. In both lines, the imported object contains React-related methods.

However, there is a difference!

The methods imported from 'react-dom' are meant for interacting with the DOM. You are already familiar with one of them: ReactDOM.render().

The methods imported from 'react' don’t deal with the DOM at all. They don’t engage directly with anything that isn’t part of React.

To clarify: the DOM is used in React applications, but it isn’t part of React. After all, the DOM is also used in countless non-React applications. Methods imported from 'react' are only for pure React purposes, such as creating components or writing JSX elements.

### 🧿The Render Function🧿

A component class is like a factory that builds components. It builds these components by consulting a set of instructions, which you must provide. Let’s talk about these instructions!

For starters, these instructions should take the form of a class declaration body. That means that they will be delimited by curly braces, like this:

```javascript
class ComponentFactory extends React.Component {
	// instructions go here, between the curly braces
}
```

The instructions should be written in typical JavaScript ES2015 class syntax.

There is only one property that you have to include in your instructions: a render method.

A render method is a property whose name is render, and whose value is a function. The term “render method” can refer to the entire property, or to just the function part.

`class ComponentFactory extends React.Component {  render() {}}`

A render method must contain a return statement. Usually, this return statement returns a JSX expression:

`class ComponentFactory extends React.Component {  render() {    return <h1>Hello world</h1>;  }}`

Of course, none of this explains the point of a render method. All you know so far is that its name is render, it needs a return statement for some reason, and you have to include it in the body of your component class declaration. We’ll get to the ‘why’ of it soon!
