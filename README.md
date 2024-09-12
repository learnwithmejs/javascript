# JAVASCRIPT

// Date : 07th Sep 2024

## Everything in JavaScript happens inside an `Execution Context`

### Execution Context has two components

1.Memory Component/Variable Environment

2.Thread of Execution/Code component

* Call Stack / Execution Context - Used to manage the execution context

### A. How Javascript works?

### B. Is Javascript Synchronous or Asynchronous?

### C. Is Javascript single threaded or multi-threaded?

### D. What happens when you run the Javascript code?

## `Javascript is a synchronous single-threaded language`

## Hoisting in Javascript(Variables and Functions)

## What is temporal Dead zone?

## are let & const declarations hoisted?

## What is the difference between 'syntax error', 'type error' & 'reference error'

```javascript
getName() //Javascript
console.log(x) //undefined
console.log(getName) // prints the whole getName function
console.log(functionName) // undefined

var x = 7

function getName(){
    console.log('Javascript')
}
// Arrow Function , function was assinged to the variable.
var functionName = () => {
    console.log('Javascript 1')
}
getName() //Javascript
console.log(x) // 7
console.log(getName) // prints the whole getName function
functionName() //Javascript 1
console.log(functionName) // prints the whole getName function
```

## Functions

```javascript
console.log(x) //undefined
var x = 8
a() // 10
b() // 9
console.log(x) //8
function a(){
    var x = 10
    console.log(x)
}
function b(){
    var x = 9
    console.log(x)
}
```

### At Global space `this === window` //true

#### Global space is nothing but anything which is not within the functions

```javascript
var a = 10
function b(){
    var x = 9
}
console.log(a)//10
console.log(window.a)//10
console.log(this.a)//10
console.log(x)// error - b is not defined

```

// Date : 08th Sep 2024

### What is the difference between 'undefined' and 'not defined'?

* undefined is like a placeholder till a variable is not assinged
* undefined != not defined

```javascript
var a
console.log(a)//undefined
a = 10
console.log(a)//10
console.log(x) // not defined
```

// Date : 11th Sep 2024

## The scope chain & Lexical Environment

1. Scope of a variable is directly dependent on the lexical environment.
2. Whenever an execution context is created, a lexical environment is created. Lexical environment is the local memory along with the lexical environment of its parent. Lexical as a term means in hierarchy or in sequence.
3. Having the reference of parent's lexical environment means, the child or the local function can access all the variables and functions defined in the memory space of its lexical parent.
4. The JS engine first searches for a variable in the current local memory space, if its not found here it searches for the variable in the lexical environment of its parent, and if its still not found, then it searches that variable in the subsequent lexical environments, and the sequence goes on until the variable is found in some lexical environment or the lexical environment becomes NULL.
5. The mechanism of searching variables in the subsequent lexical environments is known as Scope Chain. If a variable is not found anywhere, then we say that the variable is not present in the scope chain.

```javascript
function a(){
    console.log(b) //10
    c()
    function c(){
        console.log(b) //10
    }
}
var b = 10;
a()
//------------------------//
function x(){
    var y = 2
}
console.log(y) //y is not defined
```

## LET, VAR & CONSTANT

1. let and const are hoisted but its memory is allocated at other place than window which cannot be accessed before initialisation.
2. Temporal Dead Zone exists until variable is declared and assigned a value.
3. window.variable OR this.variable will not give value of variable defined using let or const.
4. We cannot redeclare the same variable with let/const(even with using var the second time).
5. const variable declaration and initialisation must be done on the same line.
6. There are three types of error: [1] referenceError {given where variable does not have memory allocation} [2] typeError {given when we change type that is not supposed to be changed} [3] syntaxError {when proper syntax(way of writing a statement) is not used}.
7. Use const wherever possible followed by let, Use var as little as possible(only if you have to). It helps avoid error.
8. Initialising variables at the top is good idea, helps shrinks TDZ to zero.
