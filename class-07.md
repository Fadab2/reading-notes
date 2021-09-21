## Object-Oriented Programming, HTML Tables

### HTML tables

There are many reasons we need to use table for better visual/display representation. Such reasons include displaying financial reports, TV schedles and sport results. Tables are made up of a grid made up of rows and columns.

#### Table structure:
To create a table we use the `<table> </table>` element. Then we write the `<tr> </tr>` tag which statnds for __table row__  to indicate the start of the table. Followed by `<td> </td>` tag to represents a cell of table.
The `<th> </th>` is used to represent the table heading for a column/row.
the `colspan` and `rowspan` attributes are used to indicate many columns/rows the cell span respectively.

```
<table>
  <tr>
    <th></th>
    <th></th>
  </tr>
  <tr>
    <td></td>
    <td></td>
  </tr>
</table>
```

### JS functions, Methods and Objects:

#### Constructor notation
__Creating an object__
- the `new` keyword is used to create a blank object.
- let car = new Object(); creates a new blank object.
  
__Updating an object__
- Dot notation is used to update a value of an object
- `car.brand = 'Toyota` will update the car brand value.
- We can also use square brackets to update a property of an object, but we can't update its method `car[`brand`] = 'Toyota`.

To create a fuction to use template for creating objects.
``` 
function car(make, model, condition) {
    this.make = make;
    this.model = model;
    this.condition = condition;
}
```

and to create an instance of that object using the above function we use
```
let camry = new car('toyota', 'camry', 'new');

```

### Arrays are objects
- arrays hold sets of a key and a value pairs with the index been the key.
- We can combine arrays and objects to create complex data structures by storing a series of objects.

### Built-in objects
- browsers' built-in objects that represents things like browser window and the active page help us write scripts for web pages.

#### References:

- JAVASCRIPT & JQUERY by Jon Duckett 
- HTML&CSS by Jon Duckett
  

[Go to home](README.md)