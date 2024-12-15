# Understanding let, const and var in JavaScript

![Variables in JavaScript](/images/thumbnails/01_JSBlog_Thumbnail.jpg)

## Introduction

In JavaScript, the use of `let`, `const`, and `var` for variable declarations is not just a matter of syntax, but a crucial aspect of writing clean and efficient code. Understanding the distinctions between these declarations is of paramount importance.

## var

Since the beginning of JavaScript, the `var` keyword has existed. Variables declared with `var` are function-scoped, which means that the function in which they are declared can access them. They are globally scoped if they are declared outside of a function. The fact that `var` permits variable hoisting—a JavaScript technique that places variables and function declarations at the top of their contained scope during compilation—is one of its primary problems. This may result in unanticipated actions.

Example:

```javascript
console.log(x); // undefined
var x = 5;

console.log(x); // 5
```

## let

The `let` keyword, introduced in ES6 (ECMAScript 2015), brings your code a new level of predictability. Variables declared with `let` are block-scoped, meaning they are only accessible within the block they are declared in, thereby preventing issues related to variable hoisting.

Example:

```javascript
if (true) {
    let y = 10;
    console.log(y); // 10
}

console.log(y); // ReferenceError: y is not defined
```

## const

The `const` keyword, also introduced in ES6, is used to declare variables that are meant to be constant and should not be reassigned. Like `let`, `const` is block-scoped. However, it is essential to note that `const` does not make the variable immutable; it only prevents the reassignment of the variable itself.

Example:

```javascript
const z = 20;
console.log(z); // 20

z = 30; // TypeError: Assignment to constant variable.
```

## Conclusion

Choosing between `let`, `const`, and `var` depends on the use case. Generally, it is recommended to use `const` by default and `let` if you know the variable will need to be reassigned. The use of `var` is discouraged due to its function-scoping and hoisting behaviour, which can lead to bugs and unpredictable code.

You can write more robust and maintainable JavaScript code by understanding these differences.

Thanks for reading! 🚀
