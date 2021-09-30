##  CSS Transforms, Transitions, and Animations

### Transforms

Transforms provides us with another way to modify size, position and change element.
Two different setting to transform elements:
#### 2D setting
  Works on the y and x axes (length & width) to rotate elements clockwise/counterclockwise.
  We can rotate an elements certain degrees using the rotate value:
  ```
  .box-1 {
  transform: rotate(20deg);
}
.box-2 {
  transform: rotate(-55deg);
}
```
We can resize element using the scale value:
```
.box-1 {
  transform: scale(.75);
}
.box-2 {
  transform: scale(1.25);
}
```
Other transform values include `skew, translate, transform-origin`

#### 3D setting
 Works on the y, x and z axes (length, width, depth) rotates elements in any direction using values for each of the 3 axes:
 ```
 .box-1 {
  transform: perspective(200px) scaleZ(1.75) rotateX(45deg);
}
```

### Transitions
Transition allows us to change the behavior of an element for one state to another.Such as changing the color of a button upon a hover:
```
.box:hover {
  background: #ff7b29;
}
```
Transition has many properties. For example:
`transition-timing-function` defines the speed of the transition.
`transition-delay` defines delay time before the transition.

### Animations
Transition allows us to change the behavior of an element.
The `@keyframes` rule is used to set point of transition.
```
@keyframes slide {
  0% {
    left: 0;
    top: 0;
  }
  50% {
    left: 244px;
    top: 100px;
  }
  100% {
    left: 488px;
    top: 0;
  }
}
```
Animation properties include `animation-duration, animation-timing-function, and animation-delay`

#### References:
[Transforms](https://learn.shayhowe.com/advanced-html-css/css-transforms/)

[Transitions & Animations](https://learn.shayhowe.com/advanced-html-css/transitions-animations/)

[go to home](README.md)