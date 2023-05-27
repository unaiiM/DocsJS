---------------
Declaration
---------------
You use variables as symbolic names for values in your application. The names of variables, called identifiers, conform to certain rules.
Evenry variable declaration starts with a letter, underscore (_), or dollar sign ($) and can follow with numbers or the other ones.
- Identifier --> is a sequence of characters in the code that identifies a variable, function, or property.

Variables should always be declared before they are used. JavaScript used to allow assigning to undeclared variables, which creates an undeclared global variable. This is an error in strict mode and should be avoided altogether.

- var
- let
- const

------------------
Declaration and initialization
------------------
`let x = 42` the `let x` is called the declaration and `= 42` is called the initializer. The declaration allows the variable to be accessed later in code, while the initializer assigns a value to the variable. In var and let declarations, the initializer is optional. If a variable is declared without an initializer, it is assigned the value undefined.

const declarations always need an initializer, because they forbid any kind of assignment after declaration, and implicitly initializing it with undefined is likely a programmer mistake.

------------------
Variable scope
------------------
The scope is the current context of execution in which variables are "visible" or can be referenced.

- Global scope: The default scope for all code running in script mode.
- Module scope: The scope for code running in module mode.
- Function scope: The scope created with a function.

Variables declared with let or const can belong to an additional scope:

- Block scope: The scope created with a pair of curly braces (a block).

When you declare a variable outside of any function, it is called a global variable, because it is available to any other code in the current document. When you declare a variable within a function, it is called a local variable, because it is available only within that function.

let and const declarations can also be scoped to the block statement that they are declared in.

```
if (Math.random() > 0.5) {
  const y = 5;
}
console.log(y); // ReferenceError: y is not defined
```

However, variables created with var are not block-scoped, but only local to the function (or global scope) that the block resides within.

```
if (true) {
  var x = 5;
}
console.log(x); // x is 5
```
------------------
Variable hoisting
------------------
Hoisting --> interpreter appears to move the declaration of functions, variables or classes to the top of their scope, prior to execution of the code.
`var` declared variables are hoisted, meaning you can refer to the variable anywhere in its scope, even if its declaration isn't reached yet. If you access a variable before it's declared, the value is always undefined, because only its declaration is hoisted, but not its initialization.

```
console.log(x === undefined); // true
var x = 3;

(function () {
  console.log(x); // undefined
  var x = "local value";
})();
```
Same as:
```
var x;
console.log(x === undefined); // true
x = 3;

(function () {
  var x;
  console.log(x); // undefined
  x = "local value";
})();
```

All var statements in a function should be placed as near to the top of the function as possible. This best practice increases the clarity of the code.
`let` and `const` referencing the variable in the block before the variable declaration always results in a ReferenceError.

Unlike var declarations, which only hoist the declaration but not its value, function declarations are hoisted entirely.

------------------
Global variables
------------------
Global variables are in fact properties of the global object.
In web pages, the global object is window, then you can access them by `window.variableName`.

You can access global variables declared in one window or frame from another window or frame by specifying the window or frame name. For example, if a variable called phoneNumber is declared in a document, you can refer to this variable from an iframe as parent.phoneNumber.

------------------
Literals
------------------
Primitives --> represent bàsic data types from programming language; number, string, boolean.
Literals --> represent instance of a primitive like; 10, "hello", false.

------------------
Destructuring assignment
------------------
Can declare variables to unpack values from an object.
For example, `const { bar } = foo`. This will create a variable named bar and assign to it the value corresponding to the key of the same name from object foo.

------------------
Types, Values, and Variables
------------------
Variables --> defines a symbolic name for a value and allows the value to be referred to by name. 

Values --> 

Types --> values that can be represented and manipulated in a programming language are known, fundamental characteristics of a programming language is the set of types it supports.
- JavaScript types can be divided into two categories: primitive types and object types.
- Primitive --> number, a string, a boolean, or *null or undefined* (special values).
- Object --> any javascript value that is not a primitive value is considered an object. Is a collection of properties where each property has a name and a value. Arrays are special object  that represents an ordered collection of numbered values. Another special object are the functions, is an object that has executable code associated with it, that when the function become invoked the executable code are executed to return a computed value. Like arrays, functions behave differently from other kinds of objects, and JavaScript defines a special language syntax for working with them.
Functions that are written to be used (with the new operator) to initialize a newly created object are known as constructors.

The JavaScript interpreter performs automatic garbage collection for memory management. This means that a program can create objects as needed, when an object is no longer reachable—when a program no longer has any way to refer to it—the interpreter knows it can never be used again and automatically reclaims the memory it was occupying.

JavaScript’s types can be divided into primitive types and object types. And they can be divided into types with methods and types without. They can also be categorized as mutable and immutable types.
Mutable --> values can be modified or changed after they are created.
```
let arr = [2, 3, 4];
arr[0] = 4; // H -> B
console.log(arr) // 4, 3, 4;
```
Immutable --> values cannot be changed after they are created. (Numbers, booleans, null, undefined and strings)
```
let str = "Hello";
str[0] = "B"; // H -> B
console.log(str) // Hello;
```

JavaScript converts values liberally from one type to another. If a program expects a string, for example, and you give it a number, it will automatically convert the number to a string for you.
JavaScript variables are untyped: you can assign a value of any type to a variable, and you can later assign a value of a different type to the same variable. 
