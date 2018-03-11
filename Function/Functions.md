# Defining Functions
## Function declarations
A function definition (also called a function declaration, or function statement) consists of the function keyword, followed by:

- The name of the function.
- A list of parameters to the function, enclosed in parentheses and separated by commas.
- The JavaScript statements that define the function, enclosed in curly brackets, ```{ }```.

### Example
```JavaScript
function square(number) {
  return number * number;
}
console.log(square(5));
```
### Result
```
25
```
The function square takes one parameter, called number. The function consists of one statement that says to return the parameter 
of the function (that is, number) multiplied by itself. The return statement specifies the value returned by the function.

Primitive parameters (such as a number) are passed to functions by value; the value is passed to the function, 
but if the function changes the value of the parameter, this change is not reflected globally or in the calling function.
In case of object (i.e. a non-primitive value, such as Array or a user-defined object) as a parameter and 
the function changes the object's properties, that change is visible outside the function

## Function expressions
While the function declaration above is syntactically a statement, functions can also be created by a function expression. 
Such a function can be anonymous; it does not have to have a name. For example, the function square could have been defined as:
```JavaScript
var square = function(number) { return number * number; };
var x = square(4); // x gets the value 16
```

However, a name can be provided with a function expression and can be used inside the function to refer to itself, or in a 
debugger to identify the function in stack traces:
```JavaScript
var factorial = function fac(n) { return n < 2 ? 1 : n * fac(n - 1); };
console.log(factorial(3));
```
Function expressions are convenient when passing a function as an argument to another function.

## Function Scope
Variables defined inside a function cannot be accessed from anywhere outside the function, because the variable is defined only in 
the scope of the function. However, a function can access all variables and functions defined inside the scope in which it is defined. 
In other words, a function defined in the global scope can access all variables defined in the global scope. A function defined inside 
another function can also access all variables defined in its parent function and any other variable to which the parent function has 
access.
```JavaScript
// The following variables are in global scope
var num1 = 20,
    num2 = 3,
    name = 'Chamahk';
// This function is defined in the global scope
function multiply() {
  return num1 * num2;
}
multiply(); // Returns 60
// A nested function 
function getScore() {
  var num1 = 2,
      num2 = 3;
  
  function add() {
    return name + ' scored ' + (num1 + num2);
  }
  return add();
}
getScore(); // Returns "Chamahk scored 5"
```

## Using the arguments object
The arguments of a function are maintained in an array-like object. Within a function, you can address the arguments passed to it as 
follows:
```JavaScript
arguments[i]
```
Using the ```arguments``` object, you can call a function with more arguments than it is formally declared to accept. This is often useful if you don't know in advance how many arguments will be passed to the function. You can use arguments.length to determine the number of arguments actually passed to the function, 
and then access each argument using the ```arguments``` object.
### Example
```JavaScript
function myConcat(separator) {
   var result = ''; // initialize list
   var i;
   // iterate through arguments
   for (i = 1; i < arguments.length; i++) {
      result += arguments[i] + separator;
   }
   return result;
}
```
### Result
```
// returns "red, orange, blue, "
myConcat(', ', 'red', 'orange', 'blue');

// returns "elephant; giraffe; lion; cheetah; "
myConcat('; ', 'elephant', 'giraffe', 'lion', 'cheetah');

// returns "sage. basil. oregano. pepper. parsley. "
myConcat('. ', 'sage', 'basil', 'oregano', 'pepper', 'parsley');
```
