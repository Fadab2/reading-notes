# What is CSS?

CSS is a styling language that makes website looks great.  Because HTML is very limited and doesn’t give us a lot of control on designing the look of our website/pages we use CSS to engineer the layout the way we want it. It helps us to make our website user friendly and pleasant as much as possible.
Using CSS we are able to divide our document into sections that help us to manage sections with similar style under one class or ID. Then we can apply specific style like changing the text color, background color or size of the text etc. For example we can change the color and text size of our HTML h1 using the h1 {
	Color: somecolor;
	Font-size: somesize
}
This will change the style of all h1 present in that document if there are more than one.
## CSS Syntax:
The way write CSS is different from HTML and we have to follow certain rules. Some of these rules are that we have use a selector like the h1 above from our HTML file document then we use opening
Curly braces { 
	And closing curly braces 
	Then we put everything we want to apply to this selector inside these braces using property and        a value separated by a colon and a closed with semicolor.
}
Example:
h1 {
    color: red;
    font-size: 5em;
}

p {
    color: black;
}
# How does it work?
Browsers find the related style sheet if there is one and apply the styling to the website/app.
We can use CSS externally meaning the style sheet reside outside the HTML, but has a reference to it.
Internal CSS meaning the style sheet is present inside the HTML document within the style element inside the head element.
And lastly we have the inline CSS which is using inside and HTML element to apply specific styling.


[Back to Home](README.md)