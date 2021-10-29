## React lifecycle

1.  Based off the diagram, what happens first, the ‘render’ or the ‘componentDidMount’?
     - componentDidMount happens first.
  
2.  What is the very first thing to happen in the lifecycle of React?
      - The very first thing to happen in the React lifecycle is constructor.
  
3.  Put the following things in the order that they happen: `componentDidMount, render, constructor, componentWillUnmount, React Updates`
    - constructor, redner, componentDidMount, React Updates, componentWillUnmount
4.  What does componentDidMount do?
      - Invoked immediately after a component is mounted.
      - Used to initialize the DOM or load network request.
      - Used to set up subscriptions.
  Example of how to connect to the YouTube API use componentDidMount()
  ```
  componentDidMount() {
 console.log(‘got videos’);
 this.getVideos(‘cats’);
 }
  getVideos(query) {
 var options = {
 key: this.props.YOUTUBE_API_KEY,
  query: query
  };
```

## React State Vs Props
 Props are like arguments to a function.
1.  What types of things can you pass in the props?
   We can pass an initialization or what we want to display something to the user. 
2.  What is the big difference between props and state?
     You pass Props into a component and state is handled inside that component while props are handled outside that component and must be updated outside the component.
3.  When do we re-render our application?
    When state is changed inside the application.
4.  What are some examples of things that we could store in state?
   When we want to change some data on the application we store that in state.

## Things I want to know more about
  - Virtual DOM
  - useState


#### References:

[React: Component Lifecycle Events](https://medium.com/@joshuablankenshipnola/react-component-lifecycle-events-cb77e670a093)


[React State Vs Props](https://www.youtube.com/watch?v=IYvD9oBCuJI)


[go to home](README.md)