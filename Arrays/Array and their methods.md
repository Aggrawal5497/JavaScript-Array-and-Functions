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

# Accessing Array Elements
## Accessing Single Element at a time
Elements in an Array are accessed via the indexes. Arrays in JavaScript are zero-indexed, so the first element of the array have index 0 and last element of Array is at index ```|Array| - 1```, i.e. one less than total length of Array.
```JavaScript
var names = ["Ram", "Tyler", "Cody", "Anwar"];
var first_name = names[0];
var last_name = names[3];
```
In the above example, the value of variable ```first_name``` will be "Ram" and variable ```last_name``` will be "Anwar".

## Looping through the Array
Apart from accessing individual elements of Array by using constant indexes, one can also loop through the elements of the array using a ```for``` or a ```while``` loop. The for loop method is shown below, reader is suggested to try the same example using while loop.
```JavaScript
var numbers = [23, 2, 98, 75, -34];
var i;
for(i = 0; i < numbers.length; i++){
    console.log(number[i]);
}
```
The output of ```console.log``` can be found in the Inspect Web page option of the browser.

# Changing Elements in a Array
To change the value of any element in the are simply use the index of the element to be changed to access that location in array and assign new value to it as illustrated by the following example.
### Example
```JavaScript
var fruits = ["Apple", "Peach", "Banana", "Guava"];
console.log(fruits);
fruits[1] = "Orange";
console.log(fruits);
```
### Result
```
Apple,Peach,Banana,Guava
Apple,Orange,Banana,Guava
```

# Deleting Elements in Array
The elements of the Array can be deleted by using the ```delete``` keyword.
### Example
```JavaScript
var fruits = ["Apple", "Peach", "Banana", "Guava"];
console.log(fruits);
delete fruits[1];
console.log(fruits);
```
### Result
```
Apple,Peach,Banana,Guava
Apple,empty,Banana,Guava
```
Using ```delete``` creates undefined holes in the Array as can be seen in above example, an ```empty``` spot is created in the Array. Thus, use of Array methods ```pop``` and ```shift``` is recommended.

# Array Methods
JavaScript has provided a number of methods for specific tasks to be done using Arrays. Some of these are Discussed Below

## length
The ```.length``` returns the legth of the array i.e. the number elements in the Array at present.
### Example
```JavaScript
var fruits = ["Apple", "Peach", "Banana", "Guava"];
console.log(fruits.length);
```
### Result
```
4
```

## toString()
The ```toString()``` method is used to convert the Array to a String of comma seperated values.
#### Example
```JavaScript
var fruits = ["Apple", "Peach", "Banana", "Guava"];
console.log(fruits.toString());
```
#### Result
```
Apple,Peach,Banana,Guava
```

## join(seperator)
The ```join()``` method behaves same as ```toString()``` i.e. it joins all array elements into a String. The ```join()``` method in addition allow you to define a specific seperator other than ```,```.
#### Example
```JavaScript
var fruits = ["Apple", "Peach", "Banana", "Guava"];
console.log(fruits.join(" -> "));
```
#### Result
```
Apple -> Peach -> Banana -> Guava
```

## Push and Pop
When working with Arrays we often find a need to add new elements to the Array as well as remove certain elements from the Array. To achieve this, ```push``` and ```pop``` are used.

### push(element1, ..., elementN)
The push method adds one or more elements to the **end of the Array**.
#### Example
```JavaScript
var fruits = ["Apple", "Peach", "Banana", "Guava"];
console.log(fruits);
fruits.push("Orange");
console.log(fruits);
```
#### Result
```
Apple,Peach,Banana,Guava
Apple,Peach,Banana,Guava,Orange
```

### pop()
The pop method removes the last element from the Array.
#### Example
```JavaScript
var fruits = ["Apple", "Peach", "Banana", "Guava"];
console.log(fruits);
fruits.pop();
console.log(fruits);
```
#### Result
```
Apple,Peach,Banana,Guava
Apple,Peach,Banana
```

## Shifting Elements
Shifting is equivalent to popping or pushing elements the difference is that now we are working on the first element instead of the last.

### shift()
The ```shift()``` method removes the **first** element of the Array as can be seen in following example.
#### Example
```JavaScript
var fruits = ["Apple", "Peach", "Banana", "Guava"];
console.log(fruits);
fruits.shift();
console.log(fruits);
```
#### Result
```
Apple,Peach,Banana,Guava
Peach,Banana,Guava
```

### unshift(elements1, ..., elementN)
The ```unshift()``` methods adds one or more new elements to the front of the Array.
#### Example
```JavaScript
var fruits = ["Apple", "Peach", "Banana", "Guava"];
console.log(fruits);
fruits.unshift("orange", "kiwi");
console.log(fruits);
```
#### Result
```
Apple,Peach,Banana,Guava
orange,kiwi,Apple,Peach,Banana,Guava
```

## splice(index, howMany, [element1, ....elementN])
The ```splice()``` method changes the content of an array, adding new elements while removing old elements. The first argument ```index``` specify where to start adding/removing elements, ```howMany``` denotes the number of elements to be removed, and last argument is the list of elements to be added. If the list of elements to be added is not given the splice will only remove elements.
#### Example
```JavaScript
var fruits = ["Apple", "Peach", "Banana", "Guava"];
console.log(fruits);
fruits.splice(2, 1, ["Orange", "Kiwi"]);
console.log(fruits);
```
#### Result
```
Apple,Peach,Banana,Guava
Apple,Peach,Orange,Kiwi,Guava
```

## concat(value1, ..., valueN)
The ```concat()``` method creates a new Array merging the existing array with the values specified as arguments.
#### Example
```JavaScript
var fruits = ["Apple", "Peach", "Banana", "Guava"];
var numbers = [23, 13, 56];
var fruits_numbers = fruits.concat(numbers);
console.log(fruits_numbers)
```
#### Result
```
Apple,Peach,Banana,Guava,23,13,56
```

## slice(range)
The ```slice()``` method slices out a piece of an array into a new array. It does not remove any element from the Array instead creates a new Array.
#### Example
```JavaScript
var fruits = ["Apple", "Peach", "Banana", "Guava", "Orange", "Kiwi"];
var fruits_slice = fruits.slice(2,5);
console.log(fruits_slice)
```
#### Result
```
Banana,Guava,Orange
```

