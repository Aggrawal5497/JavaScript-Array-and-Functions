# Creating an Array
## Using an Array Literal
The most simplest and straightforward way of creating an array in JavaScript is using an array literal as show below
```JavaScript
var number_array = [23, 12, 56, -23, 3, 45];
var to_do_list = [
                  "Pick up grocery", 
                  "Pay electricity bill", 
                  "Complete Assignments"
                 ];
```
Note that spaces and line breaks are not important, thus both arrays are valid.

## Using "new" Keyword
To create an Array, one could also use the **new** JavaScript keyword as shown below
```JavaScript
var number_array = new Array(23, 12, 45, -3, -67);
```

The above two methods do exactly the same thing i.e. declare an Array variable. For readability, simplicity and execution time avoid using the latter method.

