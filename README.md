# JAVASCRIPT

// Date : 07th Sep 2024
Date.format(new Date("07 Sep 2024"), "%B %d, %Y")

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
Date.format(new Date("08 Sep 2024"), "%B %d, %Y")

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
