# React 

### ES6 Syntax and Feature Overview

* Variable declaration
  * const x = 0
  * var x = 0  
  * let x = 0
* Arrow functions
  * let func = (a) => {}
  * let func = (a, b, c) => {}
* Concatenation/string interpolation
  * let str = `Release Date: ${date}`
* Multi-line strings
  * let str = `This text
            is on
            multiple lines`
* mplicit returns
  * let func = (a, b, c) => a + b + c
* Object matching
  * let {a, b, c} = obj
* looping
  * for (let i of arr) {
  console.log(i)
}
* Default parameters
* let func = (a, b = 2) => {
  return a + b
}
* spread syntax:
  * let arr3 = [...arr1, ...arr2]
* classes and constructors
```
class Func {
  constructor(a, b) {
    this.a = a
    this.b = b
  }

  getSum() {
    return this.a + this.b
  }
}

let x = new Func(3, 4)
```

* Inheritance
```
class Inheritance extends Func {
  constructor(a, b, c) {
    super(a, b)

    this.c = c
  }

  getProduct() {
    return this.a * this.b * this.c
  }
}

let y = new Inheritance(3, 4, 5)
```
* promises/callbacks
```
let doSecond = () => {
  console.log('Do second.')
}

let doFirst = new Promise((resolve, reject) => {
  setTimeout(() => {
    console.log('Do first.')

    resolve()
  }, 500)
})

doFirst.then(doSecond)
```

### React hellow word
```
ReactDOM
  .createRoot(document.getElementById('root'))
  .render(<h1>Hello, world!</h1>);
  ```

### JSX
* Is a syntax exention for JavaScript that describes what the UI should look like
```
const element = <h1>Hello, world!</h1>

```
* embedding expressions in JSX
```
const name = 'Josh Perez';
const element = <h1>Hello, {name}</h1>;

```
* JSX prevents injection attacks
```
const title = response.potentiallyMaliciousInput;
// This is safe:
const element = <h1>{title}</h1>;
```

### Rendering Elements into DOM
* Elements are the smallest building blocks of React apps and they describe what will be seen on screen
    * `<div id="root"></div>` 
pass the DOM element to ReactDOM.createRoot(), then pass the React element to root.render() as below:

```
const element = <h1>Hello, world</h1>;
const root = ReactDOM.createRoot(
  document.getElementById('root')
);
root.render(element);
```

* React elements are immutable. Once you create an element, you can’t change its children or attributes. An element is like a single frame in a movie: it represents the UI at a certain point in time.
    * We create a new element and pass it to root.render() in order to update it.
```
const root = ReactDOM.createRoot(
  document.getElementById('root')
);

function tick() {
  const element = (
    <div>
      <h1>Hello, world!</h1>
      <h2>It is {new Date().toLocaleTimeString()}.</h2>
    </div>
  );
  root.render(element);
}

setInterval(tick, 1000);

```

### Components and Props
* components help us divide the UI into independent reusable pieces. They accept props and return React elements.
```
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

### State and Lifecycle
* Each component in React has a lifecycle which you can update

```
const root = ReactDOM.createRoot(document.getElementById('root'));

function Clock(props) {
  return (
    <div>
      <h1>Hello, world!</h1>
      <h2>It is {props.date.toLocaleTimeString()}.</h2>
    </div>
  );
}

function tick() {
  root.render(<Clock date={new Date()} />);
}

setInterval(tick, 1000);
```

### Handling events

* React events are named using camelCase, rather than lowercase.
* With JSX you pass a function as the event handler, rather than a string.

```
class Toggle extends React.Component {
  constructor(props) {
    super(props);
    this.state = {isToggleOn: true};

    // This binding is necessary to make `this` work in the callback
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    this.setState(prevState => ({
      isToggleOn: !prevState.isToggleOn
    }));
  }

  render() {
    return (
      <button onClick={this.handleClick}>
        {this.state.isToggleOn ? 'ON' : 'OFF'}
      </button>
    );
  }
}
```

<br />

### References

[ES6 Syntax and Feature Overview](https://reactjs.org/docs/introducing-jsx.html)

[Introducing JSX](https://medium.com/@steve_45636/6-tips-to-ace-a-whiteboard-programming-interview-f06c1b378bc6)

[Rendering Elements](<https://reactjs.org/docs/rendering-elements.html>)

[Adding Local State to a Class](https://reactjs.org/docs/state-and-lifecycle.html)

[Handling Events](https://reactjs.org/docs/handling-events.html)

<br />

## [<-- Back](README.md)
