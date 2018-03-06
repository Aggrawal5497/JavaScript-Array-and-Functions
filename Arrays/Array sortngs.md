# Sorting Arrays

## sort()
The ```sort()``` method sorts the Array **Alphabetically**.
### Example
```JavaScript
var num = ["Hello", "Apple", "Dog", 100, 20];
console.log(num.sort());
```
### Result
```
Apple,Dog,Hello,100,20
```

The problem with the ```sort()``` method is that it sorts Array **Alphabetically** i.e. for the ```sort()``` method 100 is less than 20 as ```1``` comes before ```2```. Thus for ```String``` values in Array the Sort function will work fine but to sort numeric values in Array a **Compare** function is to be provided to the ```sort()``` method. as shown below.
### Example
```JavaScript
var num = [100, 34, 21, -45, 8, 60];
console.log(num.sort());
console.log(num.sort(function(a, b){return a - b}))
```
### Result
```
-45,100,21,34,60,8  <-- result of only sort method
-45,8,21,34,60,100   <-- result after using compare function
```
The purpose of the compare function is to define an alternative sort order.The compare function should return a negative, zero, or positive value, depending on the arguments.When the ```sort()``` function compares two values, it sends the values to the compare function, and sorts the values according to the returned ```(negative, zero, positive)``` value.
