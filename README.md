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

                                                   operand == operand

### 1. ==

In JavaScript, the **`==`** operator is known as the equality operator. When using **`==`**, JavaScript attempts to convert both operands to a common type before making the comparison. This process is called type coercion.

Here are some examples of how the **`==`** operator works:





```jsx
console.log(1 == '1');       // true, '1' is converted to a number
console.log(true == 1);      // true, true is converted to 1
console.log({} == '[object Object]'); // true, both are converted to strings
console.log(null == undefined); // true, null and undefined are considered equal
console.log(0 == NaN);       // false, NaN is not equal to anything including itself
console.log({} == {});       // false, different objects

```

 

### 2. ===

**`===`** operator in JavaScript is known as the strict equality operator. It behaves differently from the **`==`** operator in that it does not perform type coercion. Instead, it requires both operands to be of the **same type** and have the same value for the comparison to return true else it will return false even the value are same but the data type is different.

```jsx
console.log(1 === '1');       // false, number is not equal to string
console.log(true === 1);      // false, boolean is not equal to number
```

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

## Q4. What is IIFE (Immediately Invoked Function Expression)?
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

## Q8. what is difference between window and document in JavaScript?

| Window | Document |
| --- | --- |
| It is the root level element in any web page. | It is the child element of the window object. |
| It represents the browser window or tab. | It represents the HTML document loaded in the window. |
|By default window object is available implicitly in the page. | You can access it via window.document or document. |
| It has methods like alert(), confirm() and properties like document, location, history. | It has methods like getElementById(), getElementsByClassName() and properties like body, forms. |

## Q9. What is the eval() function in JavaScript?
The eval() function in JavaScript is used to evaluate or execute an argument as an expression. The argument can be a string containing JavaScript code, a function, or an expression. The eval() function is a global function and can be used to execute code dynamically at runtime.

```jsx
console.log(eval('2 + 2')); // 4
```

## Q10. What is the difference between http and https?
HTTP and HTTPS are both protocols used to transfer data over the web, but they operate over different communication channels and have different security mechanisms.The main difference between HTTP and HTTPS is that HTTP is not secure and data is transferred in plain text, while HTTPS is secure and data is encrypted before being transferred.

| HTTP | HTTPS |
| --- | --- |
| HTTP stands for Hypertext Transfer Protocol. | HTTPS stands for Hypertext Transfer Protocol Secure. |
| It operates over port 80. | It operates over port 443. |
| Data is transferred in plain text. | Data is encrypted before being transferred. |
| It is not secure and can be intercepted by attackers. | It is secure and protects against eavesdropping

## Q11. What is the difference between local storage and session storage in HTML5?
Local storage and session storage are both web storage options available in HTML5 that allow developers to store data locally in the user's browser. The main difference between local storage and session storage is the lifetime of the data and the scope of the data.The data saved in session storage is available only for the duration of the page session, while the data saved in local storage persists even after the browser is closed and reopened.


## Q12. What is the ternary operator in JavaScript?
Do you ever heared about the if else statement in JavaScript, the ternary operator is the shorthand version of the if else statement in JavaScript. The ternary operator is a conditional operator that takes three operands: a condition followed by a question mark (?), an expression to execute if the condition is true, and a colon (:) followed by an expression to execute if the condition is false.
  let me write it in general form 
  ** condition ? this will execute if condition true : this will execute if condition is false **
  
  ```jsx
    let marks = 18;
    let result = (marks >= 40) ? 'Pass' : 'Fail';
    console.log(result); // Fail 
```jsx


## Q13. What is the JSON object in JavaScript?
JSON (JavaScript Object Notation) is a lightweight data interchange format that is easy for humans to read and write and easy for machines to parse and generate. JSON is a text-based format and is used to represent structured data. In JavaScript, the JSON object is used to parse and stringify JSON data. The JSON object has two methods: JSON.parse() and JSON.stringify().

```jsx
let person = {
    name: 'John',
    age: 30,
    city: 'New York'
};

let json = JSON.stringify(person);
console.log(json); // {"name":"John","age":30,"city":"New York"}

let obj = JSON.parse(json);
console.log(obj.name); // John
```

---------------- Arrays and objects ------------------------

## Q14. What is the array in JavaScript?
An array in JavaScript is a special type of variable that can hold multiple values at once. Arrays are used to store collections of data, such as a list of numbers or a list of objects.We can save function, object, string, number, boolean in an array.To access the element of an array we use the index of the element.

```jsx 
let numbers = [1, 2, 3, 4, 5];
console.log(numbers[0]); // 1
```

## Q15. What is the object in JavaScript?
An Object is a vairable that can hold multiple values at once. Objects are used to store collections of key-value pairs, where each key is a unique identifier for a value. Objects can contain properties and methods, which are defined as key-value pairs within the object.

```jsx
let person = {
    name: 'John',
    age: 30,
    city: 'New York'
};

console.log(person.name); // John
```

## Q16. What is the forEeach() method in JavaScript?
The forEach() method in JS used to execute a function on every element of an array.We can use the forEach() method to iterate over an array and perform an operation on each element without using a for loop.It will change the original array if we perfoam any operation on element.



```jsx
let numbers = [1, 2, 3, 4, 5];
// I want to add 1 to each element of the array
// We can use forEach method to iterate over the each element of the array and add 1 to each element

numbers.forEach((number, index) => {
    numbers[index] = number + 1;
});

console.log(numbers); // [2, 3, 4, 5, 6]
```

## Q18. What is the map() method in JavaScript?
The map() method in JavaScript is used to create a new array by applying a function to each element of an existing array. The map() method does not change the original array but returns a new array with the results of the function applied to each element.

```jsx
let numbers = [1, 2, 3, 4, 5];
let newNumbers = numbers.map((number) => number * 2);
console.log(newNumbers); // [2, 4, 6, 8, 10]
console.log(numbers); // [1, 2, 3, 4, 5]
```

## Q19. What is the filter() method in JavaScript?
The filter() method in JavaScript is used to create a new array with elements that pass a certain condition. The filter() method does not change the original array but returns a new array with elements that satisfy the condition.

```jsx
let numbers = [1, 2, 3, 4, 5];
let evenNumbers = numbers.filter((number) => number % 2 === 0);
console.log(evenNumbers); // [2, 4]
console.log(numbers); // [1, 2, 3, 4, 5]
```

## Q20. What is the reduce() method in JavaScript?
The reduce() method in JavaScript is used to reduce an array to a single value by applying a function to each element of the array. The reduce() method takes an accumulator and a current value as arguments and returns a single value. The reduce() method can be used to perform operations such as summing the elements of an array or finding the maximum value.

```jsx
let numbers = [1, 2, 3, 4, 5];
let sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue, 0);
console.log(sum); // 15
```








## Q17. what is meant by call back function in JavaScript?
A callback function is a function that is passed as an argument to another function and is executed after the completion of the first function. Callback functions are used to handle asynchronous operations, such as reading a file or making an API request, and are commonly used in event handling, timers, and AJAX requests.

```jsx
function fetchData(callback) {
    setTimeout(() => {
        const data = 'Hello World';
        callback(data);
    }, 2000);
}

function displayData(data) {
    console.log(data);
}

fetchData(displayData); // Hello World
```



