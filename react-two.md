# React 2

### Conditional Rendering

* In React you can render only some behavior you need, depending on the state of your application.
For example the below code shows how conditional rendering is implemented depending on whether the user has an account or not
```
function UserGreeting(props) {
  return <h1>Welcome back!</h1>;
}

function GuestGreeting(props) {
  return <h1>Please sign up.</h1>;
}
```
Create a component to handle either of the above conditions:
```
function Greeting(props) {
  const isLoggedIn = props.isLoggedIn;
  if (isLoggedIn) {
    return <UserGreeting />;
  }
  return <GuestGreeting />;
}

ReactDOM.render(
  // Try changing to isLoggedIn={true}:
  <Greeting isLoggedIn={false} />,
  document.getElementById('root')
);
```

### Element Variables

* Variables can be used to store elements to help you conditionally render a part of the component while the rest of the output doesn’t change.

Example:
```
function LoginButton(props) {
  return (
    <button onClick={props.onClick}>
      Login
    </button>
  );
}

function LogoutButton(props) {
  return (
    <button onClick={props.onClick}>
      Logout
    </button>
  );
}
```

Inline If with Logical && Operator
```
 <div>
      <h1>Hello!</h1>
      {unreadMessages.length > 0 &&
        <h2>
          You have {unreadMessages.length} unread messages.
        </h2>
      }
```

Inline If-Else with Conditional Operator
` condition ? true : false `

* In rare cases you might want a component to hide itself even though it was rendered by another component. To do this `return null` instead of its render output.

## Lists and Keys
Rendering Multiple Components
```
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((numbers) =>
  <li>{numbers}</li>
);

ReactDOM.render(
  <ul>{listItems}</ul>,
  document.getElementById('root')
);
```

* We can refactor an array of numbers and outputs a list of elements.

* Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity:

```
const listItems = numbers.map((number) =>
  <li key={number.toString()}>
    {number}
  </li>
);
```

## Forms

* controlled components technique is used to handle React forms.
* HTML forms elements maitain their onw state.
* In React setState() is used.
### textarea tag
* HTML defines its text by its children.
* React textarea uses value attribute.

### select Tag
* In HTML `<select>` creates a drop-down list
* In React uses value attribute is used in place of selected tag as well.

The state is first added to the component that needs it for rendering. Then, if other components also need it, you can lift it up to their closest common ancestor.

<br />

### References

[Conditional Rendering](https://reactjs.org/docs/conditional-rendering.html)

[Lists and Keys](https://reactjs.org/docs/lists-and-keys.html)

[Forms](https://reactjs.org/docs/forms.html)

<br />

## [<-- Back](README.md)
