# Class Component

## 🤖5.1 Create a Component Class🤖

You’ve learned that a React component is a small, reusable chunk of code that is responsible for one job, which often involves rendering HTML.

Here’s another fact about components: we can use a JavaScript class to define a new React component. We can also define components with JavaScript functions, but we’ll focus on class components first.

All class components will have some methods and properties in common (more on this later). Rather than rewriting those same properties over and over again every time, we extend the Component class from the React library. This way, we can use code that we import from the React library, without having to write it over and over again ourselves.

After we define our class component, we can use it to render as many instances of that component as we want.

**Q. What is `React.Component`, and how do you use it to make a component class?**
-> React.Component is a JavaScript class. To create your own component class, you must subclass React.Component. You can do this by using the syntax class YourComponentNameGoesHere extends React.Component {}.

JavaScript classes and subclassing are a complex topic beyond the scope of this course. If you aren’t comfortable with them, here are some good resources to consult:

Take another look at the code from the first exercise:

```jsx
import React from 'react';
import ReactDOM from 'react-dom';

class MyComponentClass extends React.Component {
	render() {
		return <h1>Hello world</h1>;
	}
}

ReactDOM.render(<MyComponentClass />, document.getElementById('app'));
```

A lot of it is still unfamiliar, but you can understand more than you could before!

On line 4, you know that you are declaring a new component class, which is like a factory for building React components. You know that React.Component is a class, which you must subclass in order to create a component class of your own. You also know that React.Component is a property on the object which was returned by import React from 'react' on line 1.

### 🪐Name a Component Class

Good! Subclassing React. Component is the way to declare a new component class. When you declare a new component class, you need to give that component class a name. On our finished component, our component class’s name was MyComponentClass:

```jsx
class MyComponentClass extends React.Component {
	render() {
		return <h1>Hello world</h1>;
	}
}
```

Component class variable names must begin with capital letters! This adheres to JavaScript’s class syntax. This naming convention is also seen in other languages that write [class names in UpperCamelCase, like Java](<https://en.wikipedia.org/wiki/Naming_convention_(programming)#Java>).

In addition, there is a React-specific reason why component class names must always be capitalized. We’ll get to that soon!

### 🦦Component Class Instructions🦦

Something that we haven’t talked about yet is the body of your component class: the pair of curly braces after React.Component, and all of the code between those curly braces.

Like all JavaScript classes, this one needs a body. The body will act as a set of instructions, explaining to your component class how it should build a React component.

Here’s what your class body would look like on its own, without the rest of the class declaration syntax. Find it in `app.js`:

```jsx
{
  render() {
    return <h1>Hello world</h1>;
  }
}
```
That doesn’t look like a set of instructions explaining how to build a React component! Yet that’s exactly what it is. Click Next, and we’ll go into how these instructions work.

### 🍀Create a Component Instance🍀

MyComponentClass is now a working component class! It’s ready to follow its instructions and make some React components. So, let’s make a React component! It only takes one more line:

`<MyComponentClass />`

To make a React component, you write a JSX element. Instead of naming your JSX element something like h1 or div like you’ve done before, give it the same name as a component class. Voilà, there’s your component instance!

JSX elements can be either HTML-like, or component instances. JSX uses capitalization to distinguish between the two! That is the React-specific reason why component class names must begin with capital letters. In a JSX element, that capitalized first letter says, “I will be a component instance and not an HTML tag.”

### 🌞Render A Component🌞

You have learned that a component class needs a set of instructions, which tell the component class how to build components.

When you make a new component class, these instructions are the body of your class declaration:

```jsx
class MyComponentClass extends React.Component{ 
// everything in between these curly-braces is instructions for how to build components   
    render() {    
       return <h1>Hello world</h1>;  
    }
}
```

This class declaration results in a new component class, in this case named MyComponentClass. MyComponentClass has one method, named render. This all happens via standard JavaScript class syntax.

You haven’t learned how these instructions actually work to make components! When you make a component by using the expression `<MyComponentClass />`, what do these instructions do?

Whenever you make a component, that component inherits all of the methods of its component class. MyComponentClass has one method: MyComponentClass.render(). Therefore, `<MyComponentClass />` also has a method named `render`.

You could make a million different `<MyComponentClass />` instances, and each one would inherit this same exact render method.

This lesson’s final exercise is to render your component. In order to render a component, that component needs to have a method named render. Your component has this! It inherited a method named render from MyComponentClass.

Since your component has a render method, all that’s left to do is call it. This happens in a slightly unusual way.

To call a component’s render method, you pass that component to `ReactDOM.render()`.

Notice your component, being passed as ReactDOM.render()‘s first argument:

`ReactDOM.render( <MyComponentClass />,  document.getElementById('app'));`

`ReactDOM.render()` will tell `<MyComponentClass />` to call its render method.

`<MyComponentClass />` will call its render method, which will return the JSX element `<h1>Hello world</h1>`.

`ReactDOM.render()` will then take that resulting JSX element, and add it to the virtual DOM. This will make “Hello world” appear on the screen.