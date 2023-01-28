# Functional Component

## 🚨4.1 FUNCTIONAL COMPONENT🚨

### 🦠What’s a component?🦠

A component is a small, reusable chunk of code that is responsible for one job. That job is often to render some HTML.

Take a look at the code below. This code will create and render a new React component:

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

### 🕹Stateless Functional Components🕹

In React, we can also define components as JavaScript functions — we call them functional components to differentiate them from class components. In the latest versions of React, function components can do everything that class components can do. In most cases, however, functional components offer a more elegant, concise way of creating React component

### 🗽Functional Components and Props

Like any component, functional components can receive information via props. To access these props, give your function component a parameter named props. Within the function body, you can access the props using this pattern: props.propertyName. You don’t need to use the this keyword.

```jsx
export function YesNoQuestion (props) {
return (
    <div>
        <p>{props.prompt}</p>
        <input value="Yes" />
        <input value="No" />
    </div>
);}

ReactDOM.render(
    <YesNoQuestion prompt="Have you eaten an apple today?" />,  document.getElementById('app'););
```

In the above example, we pass a value of “Have you eaten an apple today?” as the prompt prop when rendering `YesNoQuestion`.
