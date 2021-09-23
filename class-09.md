## Forms and JS Events

### Forms
1. Forms are used for collecting information from visitors. 
2. information are sent using a name/value pairs.
3. Form controls are given a name and anything the user types in the text area etc is sent to the server.
   
## HTML5 form controls
There are several of form controls for gathering information from visitors. Some form controls are `Text input (single-line text)` `Password input (masked single line text area)`, `Text area input (allows for multi-line text input)`

Other contros include `Radio buttons, Checkboxes, drop-dwon boxes, submit button, upload file`
Datat collected using forms are sent to servers for processing using a name and a value. 
### How to create forms:
Example below show how to  create a form to collect a first and last name and a submit button. 
```
<form action="/example.php">
  <label for="first-name">First name:</label><br>
  <input type="text" id="first-name" name="fname" value="Adam"><br>
  <label for="last-name">Last name:</label><br>
  <input type="text" id="last-name" name="lname" value="Peter"><br><br>
  <input type="submit" value="Submit">
</form> 
```
## CSS Lists, Tables and forms

- CSS has specific elements to control lists, tables, and forms such as `list-style-type` which allows controlling the shape/style of bullet points.
-  `list-style image` allows to use an image as a bullet points.

## Events
There several everal types of event that triger JS code.
### UI Events
   Examples of UI event are:
- `load` web page has finished loading
- `error` browser encoutered JS error etc.
- `resize` browser window has been
### Keyboard Events
   
   Examples of Keyboard events are:
- `keydown` key pressed
- `keyup` key released
- `keypress` character been inserted 
  
### Mouse Event
Examples of mouse events are:
- `click` mouse press/release
- `mousedown` mouse pressed while over an element
- `mouseover` mouse moved over an element 
 
 #### References:

- JAVASCRIPT & JQUERY by Jon Duckett 
- HTML&CSS by Jon Duckett

[go to home](README.md)