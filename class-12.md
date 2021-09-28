## Chart.js and Canvas

Chart.js is a JavaScript pluging that uses HTML5's canvas elements to draw charts. We have to install Charts.js to use it. Using Charts.js we can create:

- Bar chars
- Line charts
- Pie charts
  
Features of charts:

- Charts are used to display data and they are better than tables.
- Charts are easier to undertand.
- But might be harder to create

To use Chart.js we have to download the plugin/script. Then we link the script to our html file.
To draw a line

- We first create a canvas element in HTML such as: `<canvas id="buyers" width="600" height="400"></canvas>`.
- Write script that will retrieve the context of the convas
- Create the data inside the script tag

### Canvas
Canvas is an HTML elements that is used to draw graphs. Canvas has a width and height attribute to define the size of your chart  `<canvas id="myCanvas" width="200" height="100"></canvas>`
The canvas element has a `getContext()` methoded to render the context of its drawing.
- Canvas only supports rectangles and list of points. `fillRect(x, y, width, height)`
- Other shapes are defined using lists of points connect with a line.

#### Reference:
[EASILY CREATE STUNNING ANIMATED CHARTS WITH CHART.JS](https://www.webdesignerdepot.com/2013/11/easily-create-stunning-animated-charts-with-chart-js/)

[Basic usage of canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_usage)


[go to home](README.md)