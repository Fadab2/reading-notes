## CSS Layout

#### CSS treats HTML elements as it in a box in either:

block-level: 
  Starts on a new line and takes the available width
 Some example of block-level elements are: 
 `<p> <li> <h1> <header> <hr> <li> <main> <nav>`

Inline box:
  Flow between surrounding text and only takes the width that is enough for it.
Some examples of inline elements are:
`<a> <b> <br> <i> <img> <span `
  
We can control the size of the boxes by giving it a specific width.
We control spaces between boxes we use `borders, margins, padding and background colors.

### Controlling position of elements
To control the flow CSS uses:
- Normal flow
 - Every element appears in a new line
 - Elements will not appear next to each other
 - it is the default setting and doesn’t require commands.
- Relative position
 - This shifts elements to top, right, bottom, or left.
 - Does not affect surrounding elements.
 - Set using the `position: relative` command.
- Absolute position
 - Elements are placed according to their containing elements.
 - Does not affect position of surrounding elements.
 - is set using the `position: absolute;` command
- Fixed position
 - fixed element positioned according to the browser and do not move with scrolling.
 - is set using the `position: fixed;` command.

`<div>` is used to group elements in a container.
The float property moves elements to the left or right of the page.
Grid is used to create professional designs.
We can include multiple CSS files in a single page.
Overlapping can occur when we move boxes from their normal position.

#### References:

- JAVASCRIPT & JQUERY by Jon Duckett 
- HTML&CSS by Jon Duckett

[go to home](README.md)