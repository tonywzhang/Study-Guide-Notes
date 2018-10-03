# JavaScript Notes

## JavaScript

Prototypes are a fundamental feature of Javascript. Given this topic's importance to the language, they are a very hot interview/phone screen topic. Having a strong grasp on Javascript Prototypes will give you a major leg-up in the application process.

[JavaScript Notes](https://medium.freecodecamp.org/the-definitive-javascript-handbook-for-a-developer-interview-44ffc6aeb54e)

## Types && Coercion

There are 7 built-in types: null, undefined, boolean, string, number, object, and symbol.

All of the aforementioned types, aside from object, are primitives.

```
typeof 0              // number
typeof true           // boolean
typeof 'Hello'        // string
typeof Math           // object
typeof null           // object  !!
typeof Symbol('Hi')   // symbol (New ES6)
```

### Null vs Undefined

Undefined is the absence of a definition. It is used as the default value for uninitialized variables, function arguments that were not provided and missing properties of objects. Functions return undefined when nothing has been explicitly returned.

Null is the absence of a value. It is an assignment value that can be assigned to a variable as a representation of ‘no-value’.

### Falsey Values

```
Falsy values: "", 0, null, undefined, NaN, false.

Anything not explicitly on the falsy list is truthy — boolean coerced to true.
```

### String & Number coercion

The first thing you need to be aware of is the + operator. This is a tricky operator because it works for both number addition and string concatenation.

But, the star symbol, / , and -operators are exclusive for numeric operations. When these operators are used with a string, it forces the string to be coerced to a number.


```
1 + "2" = "12"
"" + 1 + 0 = "10"
"" - 1 + 0 = -1
"-9\n" + 5 = "-9\n5"
"-9\n" - 5 = -14
"2" * "3" = 6
4 + 5 + "px" = "9px"
"$" + 4 + 5 = "$45"
"4" - 2 = 2
"4px" - 2 = NaN
null + 1 = 1
undefined + 1 = NaN
```

### == vs. ===

It is widely spread that == checks for equality and === checks for equality and type. Well, that is a misconception.

In fact, == checks for equality with coercion and === checks for equality without coercion — strict equality.

```
2 == '2'            // True
2 === '2'           // False
undefined == null   // True
undefined === null  // False
```

Some tricky comparisons to look out for:

```
false == ""  // true
false == []  // true
false == {}  // false
"" == 0      // true
"" == []     // true
"" == {}     // false
0 == []      // true
0 == {}      // false
0 == null    // false
```
### Value vs Reference

Simple values (also known as primitives) are always assigned by value-copy: null, undefined , boolean, number, string and ES6 symbol.

```
var a = 2;        // 'a' hold a copy of the value 2.
var b = a;        // 'b' is always a copy of the value in 'a'
b++;
console.log(a);   // 2
console.log(b);   // 3
var c = [1,2,3];
var d = c;        // 'd' is a reference to the shared value
d.push( 4 );      // Mutates the referenced value (object)
console.log(c);   // [1,2,3,4]
console.log(d);   // [1,2,3,4]
/* Compound values are equal by reference */
var e = [1,2,3,4];
console.log(c === d);  // true
console.log(c === e);  // false
```

### Scope

Scope refers to the execution context. It defines the accessibility of variables and functions in the code.

Global Scope is the outermost scope. Variables declared outside a function are in the global scope and can be accessed in any other scope. In a browser, the window object is the global scope.

Local Scope is a scope nested inside another function scope. Variables declared in a local scope are accessible within this scope as well as in any inner scopes.

```
function outer() {
  let a = 1;
  function inner() {
    let b = 2;
    function innermost() {
      let c = 3;
      console.log(a, b, c);   // 1 2 3
    }
    innermost();
    console.log(a, b);        // 1 2 — 'c' is not defined
  }
  inner();
  console.log(a);             // 1 — 'b' and 'c' are not defined
}
outer();
```

You may think of Scopes as a series of doors decreasing in size (from biggest to smallest). A short person that fits through the smallest door — innermost scope — also fits through any bigger doors — outer scopes.

### Hoisting

The behavior of “moving” var and function declarations to the top of their respective scopes during the compilation phase is called hoisting.

Function declarations are completely hoisted. This means that a declared function can be called before it is defined.

```
console.log(toSquare(3));  // 9

function toSquare(n){
  return n*n;
}
```

let and const are not hoisted. var is hoisted

```
{  /* Original code */
  console.log(i);  // undefined
  var i = 10
  console.log(i);  // 10
}

{  /* Compilation phase */
  var i;
  console.log(i);  // undefined
  i = 10
  console.log(i);  // 10
}
// ES6 let & const
{
  console.log(i);  // ReferenceError: i is not defined
  const i = 10
  console.log(i);  // 10
}
{
  console.log(i);  // ReferenceError: i is not defined
  let i = 10
  console.log(i);  // 10
}
```

### Function Expression vs Function Declaration

#### Function Expression

A Function Expression is created when the execution reaches it and is usable from then on — it is not hoisted.

```
var sum = function(a, b) {
  return a + b;
}
```

#### Function Declaration
A Function Declaration can be called both before and after it was defined — it is hoisted.

```
function sum(a, b) {
  return a + b;
}
```

### Variables: var, let and const

Before ES6, it was only possible to declare a variable using var. Variables and functions declared inside another function cannot be accessed by any of the enclosing scopes — they are function-scoped.

Variables declared inside a block-scope, such as if statements and for loops, can be accessed from outside of the opening and closing curly braces of the block.

Note: An undeclared variable — assignment without var, let or const — creates a var variable in global scope.

```
function greeting() {
  console.log(s) // undefined
  if(true) {
    var s = 'Hi';
    undeclaredVar = 'I am automatically created in global scope';
  }
  console.log(s) // 'Hi'
}
console.log(s);  // Error — ReferenceError: s is not defined
greeting();
console.log(undeclaredVar) // 'I am automatically created in global scope'
```

ES6 let and const are new. They are not hoisted and block-scoped alternatives for variable declaration. This means that a pair of curly braces define a scope in which variables declared with either let or const are confined in.

```
let g1 = 'global 1'
let g2 = 'global 2'
{   /* Creating a new block scope */
  g1 = 'new global 1'
  let g2 = 'local global 2'
  console.log(g1)   // 'new global 1'
  console.log(g2)   // 'local global 2'
  console.log(g3)   // ReferenceError: g3 is not defined
  let g3 = 'I am not hoisted';
}
console.log(g1)    // 'new global 1'
console.log(g2)    // 'global 2'
```

### Closures

A closure is the combination of a function and the lexical environment from which it was declared. Closure allows a function to access variables from an enclosing scope — environment — even after it leaves the scope in which it was declared.

```
function sayHi(name){
  var message = `Hi ${name}!`;
  function greeting() {
    console.log(message)
  }
  return greeting
}
var sayHiToJon = sayHi('Jon');
console.log(sayHiToJon)     // ƒ() { console.log(message) }
console.log(sayHiToJon())   // 'Hi Jon!'
```

Refers to variables in outer scope.

One of the main benefits of closures is that it allows data encapsulation. This refers to the idea that some data should not be directly exposed. The following example illustrates that.

### Immediate Invoked Function Expression (IIFE)

An IIFE is a function expression that is called immediately after you define it. It is usually used when you want to create a new variable scope.

On IIFE you are calling the function exactly when you are defining it.

```
var result = [];
for (var i=0; i < 5; i++) {
  result.push( function() { return i } );
}
console.log( result[1]() ); // 5
console.log( result[3]() ); // 5
result = [];
for (var i=0; i < 5; i++) {
  (function () {
    var j = i; // copy current value of i
    result.push( function() { return j } );
  })();
}
console.log( result[1]() ); // 1
console.log( result[3]() ); // 3
```
