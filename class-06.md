## Problem Domain, Objects, and the DOM

### Object Literals
* Objects are made up of variables and functions. It used to create/represent/model something in the real world such as a car a house.
    * when part of an object variables become properties
    * function become methods.
Example of creating an object using literal notation:
``` 
var car {
    make: 'Honda',
    model: 'Accord', 
    doors: 4,
    Condition: 'New',
    price: function() {
        return price;
    }
}
```
### Accessing an object:
The properties and methods of an object are accessed using the __dot notation__  so access the make of the car in the previous object we use:
```
var carMake = car.make; 
```

### Document Object Model (DOM)
DOM a separate set of rules implemented by browsers that specifies and helps JavaScript to create dynamic HTML by creating rules on how JS should access and manipulate web page contents.

### How it works:
* Browsers create DOM of the page as it loads.
* DOM is stored in the browsers' memory.
* Scripts access DOM without affecting the source HTML

## DOM tree has four types of nodes:
* document nodes
* element nodes
* attribute nodes
* text nodes
Nodes are selected by their id, class, tag, or using CSS selectors.
Nodes can be updated/accessed using textContent, innerHTML or DOM manipulation. 
for example to access the text in `<li id ="one"><em> fresh</em> figs</li>` we use
```
document.getElementById('one').textContent;

[Go to home](README.md)

`#### References:

- JAVASCRIPT & JQUERY by Jon Duckett 
- HTML&CSS by Jon Duckett