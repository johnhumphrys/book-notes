# Code with Mosh - Mastering React

# Introduction

See [react-app](projects/react-app) for a very basic setup using create-react-app.

- Components are small, independent building blocks in React.

### State and rendering within a Component

- Each component has a state and render method.

  - The State contains the data we want to display when the component is rendered.

  - The Render method is used to describe what the component should look like.

- Babel is used to convert jsx into browser understandable code.

# ES6

- A function inside of an object is a method

### Variable Scopes

| Type  | Visibility | Preference |
| ----- | ---------- | ---------- |
| var   | function   |            |
| let   | block      | ✔️         |
| const | block      | ✔️         |

### Arrow Function Examples

Original

```javascript
const square = function(number) {
  return number * number;
};
```

Arrow Function with multiple parameters

```javascript
const sum = (number1, number2) => {
  return number1 + number2;
};
```

Arrow Function with one parameter

```javascript
const square = number => {
  return number * number;
};
```

Arrow Function that contains one line

```javascript
const square = number => number * number;
```

A template literal is a String surrounded by backticks and is a cleaner way than traditionally concatenating strings.

```javascript
const colors = ["red", "green", "blue"];

const items = colors.map(color => `<li>${color}</>`);
```

The Array.map method is useful for creating a new array from an existing one and modifiying the contents.

```javascript
const colors = ["red", "green", "blue"];

const items = colors.map(color => `<li>${color}</>`);
```

### Object destructuring

Accessing one or multiple values within an object cleanly.

```javascript
const address = {
  street: "",
  city: "",
  country: ""
};

const { street, city, country } = address;
// These three variables have now been assigned the values from the address object.

const { street: st } = address;
// The st variable now contains the value of address.street
```

### Spread Operator

Spreading arrays

```javascript
const first = [1, 2, 3];
const second = [4, 5, 6];

// Traditional combine
const tradCombined = first.concat(second);

// Using the spread operator
const combined = [...first, ...second];
```

Spreading objects

```javascript
const first = { name: "Mosh" };
const second = { job: "Instructor" };

const objCombine = { ...first, ...second, location: "Australia" };
```

Cloning objects using spreading

```javascript
const first = { name: "Mosh" };
const clone = { ...first };
```

- The default keyword on an export is declaring that it is the main thing we are exporting from a class.

# Components

See [counter-app](projects/counter-app) for most of the basics

### Render method

A component must return a single object in its render method. This can be done by surrounding multiple values within a single div.

To reduce the amount of unnecessary empty divs, the React.Fragment component can be used to surround the values within a render method.

### Lists

In a `<li>` tag each element needs a unique key within the list.

```javascript
  renderTags() {
    return (
      <ul>
        {this.state.products.map(product => (
          <li key={product.id}>{product}</li>
        ))}
      </ul>
    );
  }
```

### Implementing Components

Functions are required to be passed as a reference to a method instead of passing the method itself to another component.

```javascript
handleIncrement = () => console.log("Incremented");

<button onClick={this.handleIncrement} />;
```

### _'this'_ keyword in javascript

Using _'this'_ can return different results depending on its context

```javascript
obj.method(); // 'this' in the method() will return the obj
function(); // 'this' in the function will return the window object or undef if strict mode is not enabled.
```

### Bind

Can use the bind method to solve the problem of the _'this'_ returning unexpected results by assigning it within a function (usually the constructor of a class).

```javascript
constructor() {
    super();
    this.handleIncrement = this.handleIncrement.bind(this);
}

handleIncrement() {
    console.log("Incremented", this);
}
```

Arrow functions do not need rebinding of _'this'_ as they inherit it.

```javascript
handleIncrement = () => console.log("Incremented", this);
```

### State

Use setState function when modifiying the state so that React is aware of the new changes. It will then be able to update the virtual DOM and the browser DOM. Attempting to change the state manually will mean React will not know changes have occurred.
