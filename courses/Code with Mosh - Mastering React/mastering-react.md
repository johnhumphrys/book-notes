# Code with Mosh - Mastering React

## Introduction

* Components are small, independent building blocks in React.

### State and rendering within a Component

* Each component has a state and render method.

    * The State contains the data we want to display when the component is rendered.

    * The Render method is used to describe what the component should look like.

* Babel is used to convert jsx into browser understandable code.

## ES6

* A function inside of an object is a method

### Variable Scopes
|Type|Visibility|Preference|
|---|---|---|
|var|function||
|let|block|✔️|
|const|block|✔️|

### Arrow Function Examples
Original

```javascript
const square = function(number) {
    return number * number;
}
```

Arrow Function with multiple parameters
```javascript
const sum = (number1, number2) => {
    return number1 + number2;
}
```

Arrow Function with one parameter
```javascript
const square = number => {
    return number * number;
}
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
    street: '',
    city: '',
    country: ''
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
const first = { name: "Mosh" };;
const second = { job: "Instructor" };

const objCombine = {...first, ...second, location: "Australia"};
```

Cloning objects using spreading
```javascript
const first = {name: "Mosh"};
const clone = {...first};
```

* The default keyword on an export is declaring that it is the main thing we are exporting from a class.