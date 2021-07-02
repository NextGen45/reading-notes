# Different types of functions
An anonymous function is a function without a function name. Only function expressions can be anonymous, function declarations must have a name:

// When used as a function expression
(function () {});
// or using the ECMAScript 2015 arrow notation
() => {};
Copy to Clipboard
The following terms are not used in the ECMAScript language specification, they're jargon used to refer to different types of functions.

A named function is a function with a function name:

// Function declaration
function foo() {};
// Named function expression
(function bar() {});
// or using the ECMAScript 2015 arrow notation
const foo = () => {};
Copy to Clipboard
An inner function is a function inside another function (square in this case). An outer function is a function containing a function (addSquares in this case):

function addSquares(a,b) {
   function square(x) {
      return x * x;
   }
   return square(a) + square(b);
};
//Using ECMAScript 2015 arrow notation
const addSquares = (a,b) => {
   const square = x => x*x;
   return square(a) + square(b);
};
Copy to Clipboard
A recursive function is a function that calls itself. See recursion.

function loop(x) {
   if (x >= 10)
      return;
   loop(x + 1);
};
//Using ECMAScript 2015 arrow notation
const loop = x => {
   if (x >= 10)
      return;
   loop(x + 1);
};
Copy to Clipboard
An Immediately Invoked Function Expressions (IIFE) is a function that is called directly after the function is loaded into the browser’s compiler. The way to identify an IIFE is by locating the extra left and right parenthesis at the end of the function’s definition.

// Declared functions can't be called immediately this way
// Error 
/*
function foo() {
    console.log('Hello Foo');
}();
*/

// Function expressions, named or anonymous, can be called immediately
(function foo() {
    console.log("Hello Foo");
}());

(function food() {
    console.log("Hello Food");
})();

(() => console.log('hello world'))();
