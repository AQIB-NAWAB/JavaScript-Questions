## Q1. Scope

The region where we can access the variable is known as the scope for that variable 
Scope determines the accessibility (visibility) of variables.

JavaScript variables have 3 types of scope:

- Block scope
- Function scope
- Global scope

### Block Scope

Variables defined in the curly braces using the let and const keyword have block scope. These variables are only accessible in that pair of braces.

Before ES6 (2015), JavaScript variables had only **Global Scope** and **Function Scope**.

ES6 introduced two important new JavaScript keywords: `let` and `const`.

These two keywords provide **Block Scope** in JavaScript.

Variables declared inside a { } block cannot be accessed from outside the block:

```jsx
{
  let x = 2;
}
// x can NOT be used here
```

Variables declared with the `var` keyword can NOT have block scope.

Variables declared inside a { } block can be accessed from outside the block.

This is because of the temporal dead zone , we will discuss it later (:

### Global Scope

The variables that can accessed from anywhere in the code are known as global variables 

### Function or  Local Scope

Variables declared within a JavaScript function, are **LOCAL** to the function:

```jsx

function myFunction() {
  let carName = "Volvo";
  // variable carName has local scope because it is declared inside a function 
}

**Question -> Can you tell that the variable carName have local scope or block scope?** 

```

## Q2. Difference Between the == and === operators?

Basically, we used both of the operators for comparison while the main difference is that the === operator in type restricted and  == is not.

Let's consider an example of what actual comparison looks like in both of these operator 

                                                   **operand == operand**

### 1. ==

In JavaScript, the **`==`** operator is known as the equality operator. When using **`==`**, JavaScript attempts to convert both operands to a common type before making the comparison. This process is called type coercion.

Here's how JavaScript decides which types to convert the operands to:

1. **If either operand is a string**: JavaScript converts the other operand to a string.
2. **If either operand is a number or a boolean**: JavaScript converts the other operand to a number.
3. **If either operand is an object**: JavaScript converts both operands to numbers if possible, or to strings if not.
4. **If either operand is null or undefined**: No conversion happens, and the comparison returns true only if both operands are null or undefined.
5. **If one operand is NaN**: The result of the comparison is always false.
6. **If both operands are objects**: They are compared as object references, and the comparison returns true only if they reference the same object.

```jsx
console.log(1 == '1');       // true, '1' is converted to a number
console.log(true == 1);      // true, true is converted to 1
console.log({} == '[object Object]'); // true, both are converted to strings
console.log(null == undefined); // true, null and undefined are considered equal
console.log(0 == NaN);       // false, NaN is not equal to anything including itself
console.log({} == {});       // false, different objects

```

 

### 2. ===

**`===`** operator in JavaScript is known as the strict equality operator. It behaves differently from the **`==`** operator in that it does not perform type coercion. Instead, it requires both operands to be of the same type and have the same value for the comparison to return true.

## Q3. Function and there types

Functions in JavaScript are blocks of reusable code that perform a specific task. There are several types of functions in JavaScript:

### Simple Functions with functions declaration

These functions are simply defined with the **function** keyword and the name of the function

We can call a function or execute the code of a function by using its name.
let me give you an example. 

```jsx
function print(name){
	console.log(name)
}

print("Dev") // Dev
```

### **Function Expressions or A**nonymous function expression:

What is an expression in Mathematics ?
Assigning a variable with some equation, similar to this 

**a=2+4bc** 

Here **a** is a variable while holding an expression “**2+4bc”** 

In functions saving a function into a variable as an expression is known as a function expression

Here is example 

```jsx
const greet = function(name) {
    console.log('Hello, ' + name + '!');
};

```

 They can be named (function expression) or anonymous (anonymous function expression).

We call then anonymous function expression because these functions don’t have there own name that’s they are anonymous

### **Arrow Functions**:

Arrow functions, also known as arrow function expressions, provide a concise syntax for writing functions in JavaScript. They were introduced in ES6 (ECMAScript 2015) and offer a more concise and expressive way to define functions compared to traditional function expressions.

```jsx
const print = (name) => {
    console.log(name);
};

print("Dev"); // Dev

```

### Q4. What is IIFE (Immediately Invoked Function Expression)?
A Immediately Invoked Function Expression (IIFE) is a JavaScript function that runs as soon as it is defined. It is a design pattern that is used to create a private scope for variables to avoid polluting the global scope.To call the function immediately after defining it, we wrap the function in parentheses and then append an additional set of parentheses at the end.
    
    ```jsx
    (function() {
        console.log("Hello World");
    })();
    ```


## Q5. What kind of JS language is , compiled language or intrepeted language ?
JavaScript is an interpreted language, not a compiled language. The major difference between complied language and interpreted language is that complied language is first converted into machine code and then executed while interpreted language is executed line by line.So which means that JS is single threaded language.

```jsx
console.log("Hello World") // this will be executed first then the next line will be executed
console.log("Hello World") // this will be executed after the first line
```

## Q6. What is the difference between null and undefined in JavaScript?
The main difference between null and undefined in JavaScript is that null is an assigned value that represents the absence of a value, while undefined is a variable that has been declared but not assigned a value.Let's consider a example,to store variable value we use a box and if the box is empty then it is undefined and if the box is not present then it is null.



```jsx
let a;
console.log(a); // undefined
```

## Q7. Is JavaScript a synchronous or asynchronous programming language?
### Synchronous Programming
JavaScript is a synchronous programming language, meaning that it executes code line by line in the order it appears in the source code.Which means that it will execute one line of code at a time and move to next line after the execution of the first line.
### Asynchronous Programming
JavaScript is also capable of asynchronous programming, which allows code to run in parallel without blocking the main execution thread. This is achieved using asynchronous functions, callbacks, promises, and async/await.

```jsx 
console.log("Hello World") // this will be executed first
setTimeout(() => {
    console.log("Hello World") // this will be executed after 2 seconds
}, 2000)
console.log("Hello World")  // this will be executed after the first line
```
In the above example, the first and third console.log statements will be executed first, followed by the second console.log statement after a delay of 2 seconds.


