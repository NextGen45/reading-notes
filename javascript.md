# Java Script 

Control flow
The control flow is the order in which the computer executes statements in a script.

Code is run in order from the first line in the file to the last line, unless the computer runs across the (extremely frequent) structures that change the control flow, such as conditionals and loops. 

For example, imagine a script used to validate user data from a webpage form. The script submits validated data, but if the user, say, leaves a required field empty, the script prompts them to fill it in. To do this, the script uses a conditional structure or if...else, so that different code executes depending on whether the form is complete or not:

if (field==empty) {
    promptUser();
} else {
    submitForm();
}
A typical script in JavaScript or PHP (and the like) includes many control structures, including conditionals, loops and functions. Parts of a script may also be set to execute when events occur.

For example, the above excerpt might be inside a function that runs when the user clicks the Submit button for the form. The function could also include a loop, which iterates through all of the fields in the form, checking each one in turn. Looking back at the code in the if and else sections, the lines promptUser and submitForm could also be calls to other functions in the script. As you can see, control structures can dictate complex flows of processing even with only a few lines of code.

Control flow means that when you read a script, you must not only read from start to finish but also look at program structure and how it affects order of execution.

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

