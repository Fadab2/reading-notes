# Passing Functions as Props

What does .map() return?
  - .map() returns a new array of the same length as the original.

If I want to loop through an array and display each value in JSX, how do I do that in React?
  - We can use .map()

Each list item needs a unique __key__.

What is the purpose of a key?
  - Helps React identify items that are changed, added, or removed.

## The Spread Operator

What is the spread operator?
  - It is three dots  `(...)` that is used to expand iterable object into list of arguments.
  
List 4 things that the spread operator can do.
  - Copying an array
  - Concatenating or combining arrays
  - Using Math functions
  - Using an array as arguments
  
Give an example of using the spread operator to combine two arrays.
```
const numbers = [1, 2, 3, 4];
onst letters = ['a', 'b', 'c', 'd'];
const numAndLetters = [...numbers, ...letters];
```
Give an example of using the spread operator to add a new item to an array.
```
const numbers = [1, 2, 3, 4];
const addItem = [0, ...numbers,5]
```
Give an example of using the spread operator to combine two objects into one.
```
const objectOne = {x: 10}
const objectTwo = {y: 20}
const objectThree = {...objectOne, ...objectTwo}
```

## Videos

How to Pass Functions Between Components
In the video, what is the first step that the developer does to pass functions between components?
 - created a function where the update is needed.

In your own words, what does the increment function do?
 - updates the state of an object at the parent level when a button is clicked, the matching element is incremented by 1

How can you pass a method from a parent component into a child component?
 - pass it just like any props.

How does the child component invoke a method that was passed to it from a parent component?
  - it calls the method that was passed to it using props that needs to be update.

## Things I want to know more about
 - passing functions between component
  


#### References:

[List and Keys](https://reactjs.org/docs/lists-and-keys.html)

[How to Use the Spread Operator](https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab)
[How to Pass Functions between Components](https://www.youtube.com/watch?v=c05OL7XbwXU)

[go to home](README.md)