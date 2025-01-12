Understanding let, const, and var in JavaScript: Practical Examples and Differences
===================================================================================

[![David Ezekiel](https://miro.medium.com/v2/da:true/resize:fill:88:88/0*_I_7Y21JAjTPVOpO)](https://medium.com/@siredave1?source=post_page---byline--64f5d37e3f65--------------------------------)

[David Ezekiel](https://medium.com/@siredave1?source=post_page---byline--64f5d37e3f65--------------------------------)

·

[Follow](https://medium.com/m/signin?actionUrl=https%3A%2F%2Fmedium.com%2F_%2Fsubscribe%2Fuser%2Fea7405f4fea4&operation=register&redirect=https%3A%2F%2Fmedium.com%2F%40siredave1%2Fturning-code-into-stories-exploring-the-heart-of-javascript-64f5d37e3f65&user=David+Ezekiel&userId=ea7405f4fea4&source=post_page-ea7405f4fea4--byline--64f5d37e3f65---------------------post_header-----------)

3 min read

·

1 day ago

[nameless link](https://medium.com/m/signin?actionUrl=https%3A%2F%2Fmedium.com%2F_%2Fvote%2Fp%2F64f5d37e3f65&operation=register&redirect=https%3A%2F%2Fmedium.com%2F%40siredave1%2Fturning-code-into-stories-exploring-the-heart-of-javascript-64f5d37e3f65&user=David+Ezekiel&userId=ea7405f4fea4&source=---header_actions--64f5d37e3f65---------------------clap_footer-----------)

--

[nameless link](https://medium.com/m/signin?actionUrl=https%3A%2F%2Fmedium.com%2F_%2Fbookmark%2Fp%2F64f5d37e3f65&operation=register&redirect=https%3A%2F%2Fmedium.com%2F%40siredave1%2Fturning-code-into-stories-exploring-the-heart-of-javascript-64f5d37e3f65&source=---header_actions--64f5d37e3f65---------------------bookmark_footer-----------)

Listen

Share

JavaScript is a versatile language with a rich set of features, but understanding the basics is crucial to writing clean, maintainable code. **Among these basics are the variable declaration keywords: let, const, and var.** While they may seem interchangeable at first glance, they have distinct characteristics that can significantly affect how your code behaves.

In this article, I’ll explain the differences between _let_, _const_, and _var_, backed with practical examples to help you use them effectively.

1. The Old Guard: var
======================

_var_ has been around since the early days of JavaScript. It’s function-scoped, meaning its scope is limited to the function in which it is declared. However, it is not block-scoped and can lead to unexpected behaviors.

**Characteristics of var:**

**Function-scoped**: Accessible only within the function it is declared in.

**Hoisting**: Variables declared with _var_ are hoisted to the top of their scope and initialized with undefined.

**Can be redeclared within the same scope.**

Example:

```
function demoVar() { 
 console.log(x); // undefined (hoisting)
 var x = 10; 
 console.log(x); // 10 
} 
demoVar(); 
```

Potential Pitfall:

```
if (true) { 
 var x = 5; 
} 
console.log(x); // 5 (x is not block-scoped) 
```

The above behavior can cause bugs in your code, especially in complex applications.

2. Modern and Reliable: let
============================

Introduced in ES6 (2015), _let_ addresses the shortcomings of _var_. It is block-scoped, meaning it is only accessible within the block where it is defined.

**Characteristics of let:**

**Block-scoped:** Limited to the block, statement, or expression where it is used.

**Hoisting:** Variables are hoisted but remain in a "temporal dead zone" until they are initialized.

Cannot be redeclared within the same scope.

Example:

```
function demoLet() { 
  if (true) { 
   let y = 10; 
   console.log(y); // 10
   } // console.log(y); // ReferenceError: y is not defined } 
demoLet(); 
```

Temporal Dead Zone:

```
console.log(z); // ReferenceError: Cannot access 'z' before initialization let z = 20; 
```

The temporal dead zone ensures you can’t use a let variable before declaring it, preventing bugs.

3. Immutable by Default: const
===============================

_const_ is also block-scoped, like _let_, but with one key difference: once a variable is assigned, its value cannot be reassigned. This makes it perfect for declaring constants or values that shouldn’t change.

**Characteristics of const:**

**Block-scoped**: Same scoping rules as let.

Must be initialized at the time of declaration.

**Immutable bindings**: The variable identifier cannot be reassigned. However, objects and arrays declared with const can still be mutated.

Example:

```
const PI = 3.14159; console.log(PI); // 3.14159 // PI = 3.14; // TypeError: Assignment to constant variable 
```

Mutating Objects or Arrays:

```
const person = { name: 'Ezekiel’, age: 20 }; person.age =22; // Allowed console.log(person); // { name: 'Ezekiel’, age: 22 } // person = { name: 'David' }; // TypeError: Assignment to constant variable 
```

Here are the key differences between var, let, and const:
=========================================================

**1. Scope**:
--------------

_var_ is function-scoped, meaning it’s only accessible within the function where it’s declared.
_let_ and _const_ are block-scoped, meaning they’re only accessible within the block (e.g., inside {}) where they’re declared.

**2. Hoisting:**

Variables declared with _var_ are hoisted to the top of their scope and initialized with undefined.
_let_ and _const_ are also hoisted, but they remain in a "temporal dead zone" until they are initialized.

**3. Redeclaration:**

_var_ allows redeclaring the same variable within the same scope.
_let_ and _const_ do not allow redeclaration within the same scope.

**4. Reassignment:**

_var_ and _let_ allow reassigning values to the variable.
_const_ does not allow reassignment of its value.

5. **Initialization:**

_var_ and _let_ can be declared without being initialized.
_const_ must be initialized at the time of declaration.

**When to Use Which?**
======================

Use _const_ by default for values that shouldn’t change. It makes your code predictable and prevents accidental reassignment.

Use _let_ when you need a variable whose value will change.

Avoid using _var_ unless maintaining legacy code or dealing with specific scenarios that require function-scoping.

Conclusion
==========

Understanding the differences between _let_, _const_, and _var_ is vital for writing robust and error-free JavaScript. By following best practices and leveraging _let_ and _const_ over _var_, you can ensure your code is clean, maintainable, and less prone to unexpected behaviors.

What are your thoughts on _var_, _let_, and _const_? Do you have any tips or tricks for using them effectively? Let’s discuss @  https://medium.com/@siredave1/turning-code-into-stories-exploring-the-heart-of-javascript-64f5d37e3f65