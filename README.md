<div align="center">
  <h1>JS is ❤️❤️! Do it everyday 💯💯</h1>
</div>

1. **What will be the output ?**

```JS
console.log(typeof fn);

function fn() {
  return "reassign";
}
var fn = "reassign";

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: `function`

1. console.log(typeof fn);: This line is executed first. At this point, foo is hoisted as a variable, but it has not been assigned a value yet, so its type is undefined.

2. function fn() { return "reassign" }: The function declaration is hoisted to the top of its containing scope (in this case, the entire script or function). This means that the foo variable is now a function.

3. var fn = "reassign";: This line is executed last. It reassigns the variable fn with the string value "reassign" overwriting the previous function declaration.

So, when you call console.log(typeof fn); after the entire script has been executed, the output will be "function" because, at the time of the console.log statement, fn refers to the function declaration that was hoisted.

</p>
</details>

</li>

---

2. **What will be the output ?**

```JS
function fn() {
  return "reassign";
}
var fn;

console.log(typeof fn);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: `function`

function fn() { return "reassign"; }: This is a function declaration, and it creates a function named fn. Function declarations are hoisted to the top of their containing scope.

var fn; This declares a variable foo. However, since there's already a function declaration named foo in the same scope, the variable declaration doesn't override the function declaration.

</p>
</details>

</li>

---

3. **What will be the output ?**

```JS
function outer() {
    inner();
    return;
    function inner() {
      console.log("bar");
    }
  }
  outer();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: "bar"

This ```JS code defines two functions: outer and inner. When you run outer(), it calls inner(), logs "bar" to the console, and exits the outer function. The return statement doesn't affect the output. The final result is that "bar" is printed to the console when the script is executed.


</p>
</details>

</li>

---
4. **What will be the output ?**

```JS
  if (true) {
    function fn() {
      console.log(1);
    }
  } else {
    function fn() {
      console.log(2);
    }
  }
  fn();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼:1

In this code snippet, there's a conditional block, but due to function hoisting, both branches define a function named fn. Regardless of the condition, the function defined inside the if block is the one that gets hoisted and is accessible outside the block. Consequently, when fn() is called outside the conditional block, it prints "1" to the console. The condition itself (if true or false) doesn't affect the output.

</p>
</details>

</li>

---
5. **What will be the output ?**

```JS
  function foo(x) {
    x();
    function x() {
      console.log("foo");
    }
  }

  foo(function () {
    console.log("bar");
  });

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: foo


The code defines a function foo that takes a function x as a parameter. Inside foo, it immediately calls x(), and then declares a nested function x that logs "foo" to the console.

When foo is invoked with an anonymous function logging "bar," due to hoisting, the nested x inside foo is called first, logging "foo," and then the anonymous function is invoked, logging "bar."


</p>
</details>

</li>

---

6. **What will be the output ?**

```JS
  foo();
  function foo() {
    console.log(1);
  }
  var foo = function () {
    console.log(2);
  };
  function foo() {
    console.log(3);
  }
  foo();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 3


The given code will output:


3
Here's the explanation:

Function declarations are hoisted to the top during the compilation phase. So, when the code is executed:

```JS
function foo() {
  console.log(1);
}
```
The first function declaration function foo() is hoisted to the top, and it logs 1 to the console.

Next, there is a variable declaration using var:

```JS
var foo = function () {
  console.log(2);
};
```
This declaration is also hoisted to the top, but it doesn't override the previous function declaration. At this point, foo still refers to the function declared in step 1.

Another function declaration follows:

```JS
function foo() {
  console.log(3);
}
```
Again, this function declaration is hoisted to the top. It overrides the previous function declaration and sets foo to the new function that logs 3 to the console.

When foo() is called:

```JS
foo();
```
It executes the latest function assigned to foo, which logs 3 to the console.


</p>
</details>

</li>

---
7. **What will be the output ?**

```JS
   function animal() {
    console.log("Cat");
  }
  var otherAnimal;
  animal();
  otherAnimal();
  otherAnimal = function () {
    console.log("Dog");
  };

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: error

```JS
function animal() {
    console.log("Cat");
}

var otherAnimal; // Variable declaration (undefined)

animal(); // Function invocation - Outputs: Cat

otherAnimal(); // Error: otherAnimal is not a function

otherAnimal = function () {
    console.log("Dog");
};
```

In this code, an attempt to invoke otherAnimal before its initialization as a function will result in an error. The error occurs because otherAnimal is assigned a function expression after the attempted invocation.





</p>
</details>

</li>

---


7. **What will be the output ?**

```JS
   function animal() {
    console.log("Cat");
  }
  var otherAnimal;
  animal();
  otherAnimal();
  otherAnimal = function () {
    console.log("Dog");
  };

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: ƒ b() {} 6


Function Expression Assignment:

```JS

b = function a() {};

```
Declares a function expression a and assigns it to the variable b.

Variable Declaration and Assignment:

```JS

var a = (b = 6);
```
Assigns the value 6 to b and assigns the result (which is 6) to a.

Function Expression Assignment:

```JS

a = function b() {};
```
Declares a function expression b and assigns it to a.

Function Declarations (hoisted):

```JS

function b() {}
function a() {}
```
Hoisted function declarations for b and a.

Logging the Variables:

```JS

console.log(a, b);
```
Outputs the values, resulting in:

```JS

function b() 6
```
In summary, the code involves variable reassignments, function expressions, and hoisted function declarations. The console.log statement shows the final values of a (function expression) and b (assigned number).

</p>
</details>

</li>

---


