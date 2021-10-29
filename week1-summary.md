# Putting it all together

What is the `single responsibility principle` and how does it apply to components?
  - A component should ideally only do one thing

What does it mean to build a ‘static’ version of your application?
  - static version is that data doesnot change and doesn't require a state
  
Once you have a static application, what do you need to add?
  - render()
  
What are the three questions you can ask to determine if something is state?
1. Is it passed in from a parent via props? If so, it probably isn’t state.
2. Does it remain unchanged over time? If so, it probably isn’t state
3. Can you compute it based on any other state or props in your component? If so, it isn’t state
 
How can you identify where state needs to live?
  - Either the common owner or another component higher up in the hierarchy should own the state.

## Higher-Order Functions

What is a “higher-order function”?
  - It is a function that operate on other functions by taking them as an arguments or returning them.
  
Explore the `greaterThan` function as defined in the reading. In your own words, what is line 2 of this function doing?
  - creating a new function

Explain how either `map` or `reduce` operates, with regards to higher-order functions.
 - `reduce` is used to reduce the value of an array.

## Things I want to know more about

#### References:

[Thinking in React](https://reactjs.org/docs/thinking-in-react.html)


[Higher-order functions](https://eloquentjavascript.net/05_higher_order.html#h_xxCc98lOBK)


[go to home](README.md)