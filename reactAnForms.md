# React and Forms

What is a ‘Controlled Component’?
  - controlled component is a JS function that handles the submission of the form and has access to data entered into the form.
  
Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.
  - We should update as soon as they enter them because this way we can validate the data instantly while entered.
  
How do we target what the user is entering if we have an event handler on an input field?

  - the input event listener will update continuously as data is entered.

Why would we use a ternary operator?
  - It takes 3 arguments including the condition. It is more compact than the if statement 
Rewrite the following statement using a ternary statement
```
  if(x===y){
 console.log(true);
  } else {
 console.log(false);
  }

  ```
  
  ```
  x === y ? console.log(true) : console.log(false);

  ```

## Things I want to know more about

#### References:

[Forms](https://reactjs.org/docs/forms.html)

[JavaScript — The Conditional (Ternary) Operator Explained](https://codeburst.io/javascript-the-conditional-ternary-operator-explained-cac7218beeff)


[go to home](README.md)