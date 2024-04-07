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
The main difference between null and undefined in JavaScript is that null is an assigned value that represents the absence of a value, while undefined is a variable that has been declared but not assigned a value.Let's consider a example,to store variable value we use a box and if the box is empty then it is null and if the box is not present then it is undefined.



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

## Q21. What is the find() method in JavaScript?
The find() method in JavaScript is used to find the first element in an array that satisfies a certain condition. The find() method returns the value of the first element that satisfies the condition, or undefined if no such element is found.

```jsx
let numbers = [1, 2, 3, 4, 5];
let evenNumber = numbers.find((number) => number % 2 === 0);
console.log(evenNumber); // 2
```
## Q22. What is the some() method in JavaScript?
The some() method in JavaScript is used to check if at least one element in an array satisfies a certain condition. The some() method returns true if at least one element satisfies the condition, otherwise it returns false.

```jsx
let numbers = [1, 2, 3, 4, 5];
let hasEvenNumber = numbers.some((number) => number % 2 === 0);
console.log(hasEvenNumber); // true
```

## Q23. What is the every() method in JavaScript?
The every() method in JavaScript is used to check if all elements in an array satisfy a certain condition. The every() method returns true if all elements satisfy the condition, otherwise it returns false.

```jsx
let numbers = [1, 2, 3, 4, 5];
let allEvenNumbers = numbers.every((number) => number % 2 === 0);
console.log(allEvenNumbers); // false
```

## Q24. What is difference between slice() and splice() method in JavaScript?
The slice() and splice() methods are used to manipulate arrays in JavaScript, but they have different purposes and behaviors.

### slice():
The slice() method in JavaScript is used to extract a portion of an array and return a new array without modifying the original array. The slice() method takes two arguments: the start index and the end index (optional). The slice() method returns a new array containing the elements from the start index up to, but not including, the end index.

```jsx
let numbers = [1, 2, 3, 4, 5];
let slicedNumbers = numbers.slice(1, 4);
console.log(slicedNumbers); // [2, 3, 4]
console.log(numbers); // [1, 2, 3, 4, 5]
```

### splice():
The splice() method in JavaScript is used to add or remove elements from an array. The splice() method takes three arguments: the start index, the number of elements to remove, and optional elements to add. The splice() method modifies the original array and returns an array containing the removed elements.

```jsx
let numbers = [1, 2, 3, 4, 5];
let removedNumbers = numbers.splice(1, 2);
console.log(removedNumbers); // [2, 3]
console.log(numbers); // [1, 4, 5]
```

## Q25. What is the difference between rest and spread operator in JavaScript?
The rest and spread operators are both introduced in ES6 (ECMAScript 2015) and are used to work with arrays and objects in JavaScript. The main difference between the rest and spread operators is their usage and syntax. The rest operator is used to gather elements into an array, while the spread operator is used to spread elements from an array.

### Rest Operator:
The rest operator is denoted by three dots (...) and is used to gather elements into an array. The rest operator can be used to collect the remaining arguments of a function into an array or to destructure an array into individual elements.

```jsx
function sum(...numbers) {
    return numbers.reduce((acc, curr) => acc + curr, 0);
}

console.log(sum(1, 2, 3, 4, 5)); // 15
```

### Spread Operator:
The spread operator is also denoted by three dots (...) and is used to spread elements from an array. The spread operator can be used to copy an array, concatenate arrays, or pass elements of an array as arguments to a function.

```jsx
let numbers = [1, 2, 3];
let newNumbers = [...numbers, 4, 5];
console.log(newNumbers); // [1, 2, 3, 4, 5]
```

## Q26. How to delete a key from the object?
To delete a key from an object in JavaScript, you can use the delete operator. The delete operator removes a property from an object. Here is an example of how to delete a key from an object:

```jsx
let person = {
    name: 'John',
    age: 30,
    city: 'New York'
};

delete person.age;

console.log(person); // { name: 'John', city: 'New York' }
```

## Q27. How to check that a key exists in an object?
To check if a key exists in an object in JavaScript, you can use the hasOwnProperty() method or the in operator. The hasOwnProperty() method returns true if the object has the specified property, while the in operator returns true if the property exists in the object or its prototype chain.

```jsx
let person = {
    name: 'John',
    age: 30,
    city: 'New York'
};

console.log(person.hasOwnProperty('age')); // true

console.log('age' in person); // true
```


--------------------- Execution Context ----------------------------
## Q28. What is the Execution Context in JavaScript?
The execution context in JavaScript means that how the code execute is JS.The execution context consist of two things or part ** Crational Phase ** and ** Execution Phase **.

### Creation Phase:
In the creation phase, the JavaScript engine creates the global object, sets up the scope chain, and creates the variable and assign them value with **undefined**. The variable object contains all the variables, function declarations, and formal parameters in the current execution context.
Let me give you an example of the creation phase.

```jsx

let a=10; // In creations phase the value of all variables store as undefined
let b=a;  // As the value of a is undefined so the value of b will be undefined

function print(){
    console.log("Hello World")
} // In creation phase the value of print will hold the function definition


```
### Execution Phase:
In the execution phase, the JavaScript engine assigns values to variables and executes the code line by line. The JavaScript engine starts executing the code from the top of the file and moves down line by line. The JavaScript engine assigns values to variables, evaluates expressions, and executes function calls during the execution phase.

```jsx
let a=10; // In creations phase the value of all variables store as undefined
let b=a;  // As the value of a is undefined so the value of b will be undefined

const print = function(){
    console.log("Hello World")
} // In creation phase the value of print will hold the function definition

print() // Hello World
```
|  JS Code | Creation Phase | Execution Phase |
| --- | --- | --- |
| let a=10; | a=undefined | a=10 |
| let b=a; | b=undefined | b=10 |
| const print = function(){console.log("Hello World")} | print=undefined | print=function(){console.log("Hello World")} |
| print() | | console.log("Hello World") |
| function show(){console.log("Hello World")} | show={function definition} | |


## Q29. What is the Global Execution Context and Function or Local Execution Context in JavaScript?

### Global Execution Context:
When a JavaScript program starts, the JavaScript engine creates the global execution context. The global execution context is the outermost context and is responsible for executing the global code. The global execution context consists of the global object, the this keyword, the scope chain, and the variable object.

### Function or Local Execution Context:
When a function is called in JavaScript, the JavaScript engine creates a new execution context for that function. This new execution context is known as the function or local execution context. This function execution context is also consist of two parts ** Creation Phase ** and ** Execution Phase **. The variables declared inside the function have local scope and are only accessible within that function. When the function completes execution, its execution context is removed from the stack.
We use **call stack** to determine the order of local execution context

```jsx
function print() {
    let message = 'Hello World';
    console.log(message);
}

print(); // Hello World
```
![image](./context.png)

## Q30. What is the call stack in JavaScript ?
Whenever a function is called in JavaScript, the JavaScript engine creates an execution context for that function and adds it to the call stack. The call stack is a data structure that stores information on the based on the LIFO (Last In, First Out) principle. Soon the function completes execution means it's 2nd part of execution context is removed from the stack.
When our script is loaded, the global execution context is added to the call stack. As functions are called, their execution contexts are added to the call stack, and when they complete execution, their execution contexts are removed from the stack.

```jsx
const a=10;
const b=20;

function sum(){
    let name="Dev"

    function print(){
        console.log("hellow World")
    }
}




![alt text](call-stack.png)
 









// Stack and Heap



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



