
## Arrow functions vs traditional functions

**_How are they different from traditional functions?_**



*   The two main benefits are that they save space visually as they have a more concise syntax and they do not bind the **this** keyword.
*   Traditional functions:

```
hello = function() {
  return "Hi there!";
}
```


*   Arrow function:

```
hello = () => {
  return "Hi there!";
}
```


*   In slight contrast to traditional functions, if an arrow function has only one statement, we can remove the **return**. This is because the arrow function's syntax implicitly states the **return**.

```
hello = () => "Hello World!";
```

*   However, if you have multiple statements, then, like a traditional function, we would need a **return**. You also need the curly braces around the code block.

```
hello = (hour) => {
  if (hour < 12) {
    return 'Good morning!';
  } else {
    return 'Hello there!';
  }
}
```


**_How do you pass in parameters?_**

*   Parameters are passed into arrow functions in the same way as they are passed in traditional functions, within the parentheses.
*   For example, the arrow function with parameter “name”

```
hello = (name) => "Hello " + name;
```


*   You can pass in multiple parameters as you would in a normal function as well

```
hello = (firstName, lastName) => "Hello" + firstName + " " + lastName;
```



**_What about the keyword this?_**



*   This is one of the main benefits of arrow functions. Pun intended. 😏
*   With arrow functions, there is no binding of **this** and instead, it is bound to the code that contains the arrow function.
*   In traditional functions, **this** keyword represents the object that called the function, whether that be the window, document, a button, etc.
*   With arrow functions, **this** keyword always represents the object that defined the arrow function
*   Traditional function

```
hello = function() {
  document.getElementById("demo").innerHTML += this;
}

document.getElementById("btn").addEventListener("click", hello);

// object HTMLButtonElement

```


*   Arrow function

```
hello = () => {
  document.getElementById("demo").innerHTML += this;
}

document.getElementById("btn").addEventListener("click", hello);

// object Window

```

JSBin: https://jsbin.com/womayih/edit?html,js,output

Github Gist: https://gist.github.com/brada1703/78774e856a0b661bbeecffe9749f46d2

*   Note that the arrow function here is referring to the object Window, which, in this case is the parent scope. If it had been in another function, then that function would be the parent scope.

**_When should you use arrow functions?_**


*   In general, you should strive for code readability and easiness of debugging. If using an arrow function helps shorten your code in a way that makes it easier to read and less likely to create bugs, then you should add them to your code. Just be careful when referring to **this**, as it will reference the parent scope.

Resources: 

[Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
