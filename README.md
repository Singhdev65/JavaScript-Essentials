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


The given code will output: 3
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


8. **What will be the output ?**

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


9. **What will be the output ?**

```JS
  var a = 10;
console.log("line number 2", a);
function fn() {
  console.log("line number 4", a);
  var a = 20;
  a++;
  console.log("line number 7", a);
  if (a) {
    var a = 30;
    a++;
    console.log("line number 11", a);
  }
  console.log("line number 13", a);
}
fn();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼:
line number 4 undefined
line number 7 21
line number 11 31
line number 13 31

Certainly! Let's break down the code step by step and see what gets printed to the console:

```JS

var a = 10;
console.log("line number 2", a);
Output: line number 2 10
```

Here, a variable a is declared and assigned the value 10. The value of a is then logged to the console.

```JS

function fn() {
  console.log("line number 4", a);
  var a = 20;
  a++;
  console.log("line number 7", a);
  if (a) {
    var a = 30;
    a++;
    console.log("line number 11", a);
  }
  console.log("line number 13", a);
}
fn();
```
Output:

```JS

line number 4 undefined
line number 7 21
line number 11 31
line number 13 31
```
Inside the function fn, a new variable a is declared and assigned the value 20, but the logging of the variable at "line number 4" prints undefined because there is a variable shadowing effect. The inner variable a is hoisted to the top of the function, so at the point of logging, it exists but hasn't been assigned a value yet.

The value of a is then incremented and logged at "line number 7". Inside the if statement, a new variable a is declared and assigned the value 30, incremented, and logged at "line number 11". After exiting the if statement, the value of a is logged again at "line number 13".

So, the final output shows the values of a at different points inside the function. The variable a inside the function does affect the outer a due to the hoisting and variable shadowing.


</p>
</details>

</li>

---

10. **What will be the output ?**

```JS
function foo() {
  let a = (b = 0);
  a++;
  return a;
}
foo();
console.log(typeof a);
console.log(typeof b);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼:undefined,number

Inside the function foo, there is a variable a declared using let, and it is assigned the value (b = 0). Here, the expression (b = 0) assigns 0 to both variable b and variable a. The parentheses are used to avoid any potential issues with the assignment.

a is then incremented by 1 with a++, and the function returns the updated value of a.

When the function foo is invoked with foo();, it doesn't explicitly use the returned value, so the result (the incremented value of a) is not logged or stored anywhere.

After the function call, there are two console.log statements:

console.log(typeof a);: This attempts to log the type of the variable a outside the function. However, since a is declared with let inside the function, it has block scope and is not accessible outside the function. As a result, this line will throw an error, and the script execution may stop at this point.
console.log(typeof b);: This attempts to log the type of the variable b outside the function. Surprisingly, b is not declared with let or var inside the function, making it implicitly a global variable. As a result, this line will log the type of b, which is number.
In summary, the code will likely throw an error at the first console.log statement (typeof a) due to the block-scoping of a. The second console.log statement (typeof b) will log number, as b becomes a global variable due to the absence of a declaration keyword (let, var, or const) inside the function.
</p>
</details>

</li>

---

11. **What will be the output ?**

```JS
let a = {};
let b = { key: "b" };
let c = { key: "c" };

a[b] = 123;
a[c] = 456;

console.log(a[b]);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 456

In this code, a is an empty object that is being assigned properties using the square bracket notation. The values of the properties are being set to the numbers 123 and 456. The keys of the properties are the objects b and c.

When the console.log statement is executed, it logs the value of the property of a whose key is the object b. In this case, the value of this property is 456, because the value of the property was last set to 456 when the object c was used as the key.

This behavior occurs because when objects are used as keys in an object, the object's default behavior is to convert the object to a string representation. In this case, both b and c are converted to the string [object Object], which means that they both end up being used as the same key in the a object. As a result, the value of the property that is set using the object c as the key overwrites the value of the property that was set using the object b as the key.

So the object a looks like -

```JS
{
    "[object Object]": 456
}
```
</p>
</details>

</li>

---

12. **What will be the output ?**

```JS
let obj1 = { key: "value" };
let obj2 = obj1;
let obj3 = obj2;

obj1.key = "new value";
obj2 = { key: "another value" };

console.log(obj1.key, obj2.key, obj3.key);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼:  `new value` `another value` `new value`

In this code, we are declaring three variables obj1, obj2, and obj3, and assigning an object to each of them. Then, we are reassigning a new object to obj2 and modifying a property of obj1.

When the console.log statement is executed, it logs the values of the key property for each object. The value of the key property for obj1 is "new value", the value of the key property for obj2 is "another value", and the value of the key property for obj3 is "new value".

This is because when an object is assigned to a variable, the variable stores a reference to the object in memory rather than the object itself. Changing the value of a property of the object using one variable will affect the value of that property when accessed using a different variable that references the same object. However, reassigning a new object to a variable will change the reference stored in that variable, so the original object is no longer accessible using that variable.

In this case, the value of the key property for obj1 was changed to "new value" using the obj1 variable, which affected the value of the key property when accessed using the obj3 variable, because both variables reference the same object. However, the value of the key property for obj2 was not affected, because the obj2 variable was reassigned to reference a new object.
</p>
</details>

</li>

---

13. **What will be the output ?**

```JS

const obj = {
  a: "foo",
  b: function () {
    console.log(this.a);
  },
};

const c = obj.b;

obj.b();
c();

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: foo, undefined

When the method obj.b is called directly on obj, the output will be "foo". This is because this refers to the object that the method is called on, and obj.a is equal to "foo".

When the variable c is assigned the value of obj.b, it is a reference to the function itself and not the object obj. When c is called, it is not called on an object, so this will not refer to obj and the value of this.a is undefined. As a result, the output when calling c() will be undefined.

</p>
</details>

</li>

---

14. **What will be the output ?**

```JS
const x = { foo: 1 };
const y = { foo: 2 };

function addFoo(obj) {
  return obj.foo + 1;
}

console.log(addFoo(x));
console.log(addFoo(y));

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 2,3

The addFoo function takes an object as an argument and returns the value of obj.foo + 1. When addFoo is called with x as the argument, the output will be 2, because x.foo is equal to 1. When addFoo is called with y as the argument, the output will be 3, because y.foo is equal to 2.

</p>
</details>

</li>

---

15. **What will be the output ?**

```JS
const arr = [1, 2, 3, 4, 5];

for (var i = 0; i < arr.length; i++) {
  setTimeout(function () {
    console.log(i);
  }, 1000);
}

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 5, 5, 5, 5, 5

The setTimeout function is called inside of a loop that iterates through the elements in the arr array. The setTimeout function will execute its callback function after a delay of 1000 milliseconds. However, by the time the delay has elapsed and the callback function is called, the loop will have already completed and the value of i will be 5. As a result, the output will be 5 printed five times.

</p>
</details>

</li>

---

16. **What will be the output ?**

```JS
const arr = [1, 2, 3, 4, 5];

arr.forEach(function (element) {
  console.log(element);
});

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1, 2, 3, 4, 5

The forEach method is called on the arr array and a callback function is passed as an argument. The callback function will be executed for each element in the array, with the element passed as an argument to the callback. As a result, the output will be the elements of the array, 1, 2, 3, 4, and 5, printed on separate lines.

</p>
</details>

</li>

---

17. **What will be the output ?**

```JS
let x = 1;

if (function f() {}) {
  x += typeof f;
}

console.log(x);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1undefined

The if statement is evaluating the function f as a boolean value. In JavaScript, functions are truthy values, so the condition will evaluate to true and the code block inside the if statement will be executed. The value of x is then incremented by the string "undefined", which is the result of calling typeof f.

</p>
</details>

</li>

---

18. **What will be the output ?**

```JS
let a = {
  x: 1,
  y: 2,
};
let b = a;
a.x = 5;
console.log(a);
console.log(b);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: {x:5, y:2} {x:5, y:2}

JavaScript objects are passed by reference. So when we assigned a object to b. b also pointing to the same object in memory. When we change the value of a.x it also affects b.x

</p>
</details>

</li>

---

19. **What will be the output ?**

```JS
let x = [1, 2, 3];
let y = [1, 2, 3];
let z = y;

console.log(x == y);
console.log(x === y);
console.log(z == y);
console.log(z == x);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: false false true false

When comparing two objects with the == operator, it compares their references, not their values. In this case, x and y are different objects with the same values. z is assigned the value of y, so they refer to the same object. As a result, the first comparison returns false, the second comparison also returns false and the third comparison returns true. and the last comparison also returns false.

</p>
</details>

</li>

---

20. **What will be the output ?**

```JS
var x = 0;
for (let i = 0; i < 5; i++) {
  setTimeout(() => {
    x++;
    console.log(x);
  }, 1000);
}

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1 2 3 4 5

The for loop is iterating 5 times, and in each iteration, it is scheduling a function to be invoked after 1000 milliseconds (1 second) using setTimeout. This function increments the value of x and logs it.

But all the 5 functions invoked after 1000 milliseconds.

Since, javascript is single threaded and event loop queue all the functions in the event loop and execute them one by one.

But inside each setTimeout callback execution, x++ increments x value by 1.

It makes difference when position of x++ code changes wrt the setTimout callback.

So all the 5 callbacks logs the values in incremental way, which is 1 2 3 4 5.s

</p>
</details>

</li>

---

21. **What will be the output ?**

```JS
let a = { x: 1 };
let b = { x: 2 };
let c = { x: 3 };
let d = { x: 4 };
let e = { x: 5 };
let arr = [a, b, c, d, e];

arr.forEach((obj) => (obj.x = obj.x * 2));

console.log(a.x, b.x, c.x, d.x, e.x);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 2 4 6 8 10

The code is using the forEach method to iterate over an array of objects, and it is modifying the x property of each object by multiplying it by 2.

It's updating the original objects with x*2 values.

So, the output of the code is 2 4 6 8 10.

</p>
</details>

</li>

---

22. **What will be the output ?**

```JS
let num = 0;

function test() {
  var num = 1;
  return num;
}

console.log(test());
console.log(num);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1 0

The code defines a global variable num with the value of 0 and then a function test which declares a local variable num with the value of 1 and returns it.

When test() is called, it first declares a local variable num with the value of 1.

Then the function return statement logs 1 on the console.

After that, it logs the value of global variable num which is 0.

Because the global and local variables have different scope and different memory allocation.

</p>
</details>

</li>

---

23. **What will be the output ?**

```JS
let obj = { name: "John", age: 25 };
let newObj = { ...obj, age: 30 };

console.log(obj.age);
console.log(newObj.age);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 25 30

The code creates an object obj with properties name and age. Then it creates a new object newObj using the spread operator to copy the properties of obj and then it updates the age property to 30.

The spread operator ... creates a new object with properties copied from the original object.

So, the first console.log statement logs the value of age property of obj which is 25.

And, the second console.log statement logs the value of age property of newObj which is 30.

It doesn't affect the original object obj.

</p>
</details>

</li>

---

24. **What will be the output ?**

```JS
const add = (a = 1, b = 2) => a + b;
console.log(add());
console.log(add(5));
console.log(add(undefined, 10));

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 3 7 11

The code defines a function add which takes two parameters a and b and returns the sum of both. It uses default parameters to assign default values 1 to a and 2 to b if they are not provided.

So, the first console.log statement logs the result of add() which is 1 + 2 = 3 as both the parameters are not provided and default values are used.

The second console.log statement logs the result of add(5) which is 5 + 2 = 7 as only the first parameter is provided and the default value of b is used.

The third console.log statement logs the result of add(undefined, 10) which is 1 + 10 = 11 as the first parameter is provided as undefined and it takes the default value 1 and the second parameter is provided as 10.

</p>
</details>

</li>

---

25. **What will be the output ?**

```JS
const name = "John";
const age = 25;

const user = { name, age };
console.log(user);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: { name: "John", age: 25 }

The code defines two variables name and age with values "John" and 25 respectively.

Then, it uses object literal notation to create an object user with properties name and age and the values are assigned from the variables name and age respectively.

So, the console.log statement logs the user object which is { name: "John", age: 25 }.

In ES6+, you can use object literal notation to create objects with properties using the same name as the variables with the values assigned to them.

</p>
</details>

</li>

---

26. **What will be the output ?**

```JS
const arr = [1, 2, 3];
const [a, b, c] = arr;

console.log(a);
console.log(b);
console.log(c);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1 2 3

The code defines an array arr with values [1, 2, 3].

Then, it uses destructuring assignment to extract the values from the array arr and assign them to variables a, b, and c respectively.

So, the first console.log statement logs the value of a which is 1.

The second console.log statement logs the value of b which is 2.

The third console.log statement logs the value of c which is 3.

In ES6+, you can use destructuring assignment to extract values from arrays and objects and assign them to variables in a concise way.

</p>
</details>

</li>

---

27. **What will be the output ?**

```JS
console.log(typeof null);
console.log(typeof undefined);
console.log(null === undefined);
console.log(null == undefined);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: object undefined false true

typeof null returns object which is an error in JavaScript. This is a historical bug in the language that cannot be fixed without breaking existing code. So, to check for null, you should use === null instead of typeof operator.

typeof undefined returns undefined.

null === undefined is false because null and undefined are two distinct types in JavaScript.

null == undefined is true because == is the loose equality operator in JavaScript, which performs type coercion before comparison. In this case, both null and undefined are coerced to undefined before comparison, and since they both have the same value, the comparison returns true. However, it is generally recommended to use === instead of == to avoid unexpected behavior due to type coercion.

</p>
</details>

</li>

---

28. **What will be the output ?**

```JS
let x = 5;
{
  let x = 10;
  console.log(x);
}
console.log(x);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 10 5

This is because of the block scoping behavior of the let keyword in ES6.

When we declare a variable with let inside a block (in this case, the block is defined by the curly braces), the variable is only accessible inside that block and its sub-blocks.

In the code above, we define a variable x outside the block with the value of 5. Then we define another variable x inside the block with the value of 10.

The first console.log() statement inside the block will print 10, because x refers to the variable defined inside the block. The second console.log() statement outside the block will print 5, because it refers to the variable defined outside the block.

</p>
</details>

</li>

---

29. **What will be the output ?**

```JS
const obj = { a: 1, b: 2, c: 3 };
const { a, b } = obj;
console.log(a, b);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1 2 

This is because of the object destructuring syntax introduced in ES6.

We declare a constant variable obj with an object containing three properties. Then we use object destructuring to extract the properties a and b from the object and assign them to separate variables with the same names.

The console.log() statement then prints the values of the a and b variables, which are 1 and 2 respectively.

</p>
</details>

</li>

---

30. **What will be the output ?**

```JS
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const arr3 = [...arr1, ...arr2];
console.log(arr3);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: [1, 2, 3, 4, 5, 6]

This is because of the spread syntax (...) introduced in ES6.

The ... operator can be used to spread the elements of an array or the properties of an object into a new array or object.

In the code above, we define two arrays arr1 and arr2. Then we create a new array arr3 by spreading the elements of arr1 and arr2 into it using the spread syntax.

The console.log() statement then prints the contents of arr3, which are the elements of arr1 followed by the elements of arr2.

</p>
</details>

</li>

---

31. **What will be the output ?**

```JS
const arr1 = [1, 2, 3];
const arr2 = [...arr1];

arr2.push(4);

console.log(arr1);
console.log(arr2);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: [1, 2, 3] [1, 2, 3, 4]

The code creates an array arr1 with the values [1, 2, 3]. It then creates a new array arr2 using the spread syntax (...) to spread the values of arr1 into a new array.

arr2.push(4) adds the value 4 to the end of arr2.

However, arr1 remains unchanged because arr2 is a new array with its own reference to the values of arr1. This is known as creating a shallow copy of the array.

Therefore, the first console.log(arr1) prints [1, 2, 3] and the second console.log(arr2) prints [1, 2, 3, 4].

</p>
</details>

</li>

---

32. **What will be the output ?**

```JS
const x = 10;

function foo() {
  console.log(x);
  const x = 20;
}

foo();

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: ReferenceError: Cannot access 'x' before initialization

The foo function attempts to log the value of x before it is initialized. This causes a ReferenceError to be thrown, as x is not yet defined in the function scope.

This happens because of variable hoisting in JavaScript. When a variable is declared with const or let, it is not hoisted to the top of the scope like variables declared with var are. Instead, they are only accessible after they are declared.

Therefore, when console.log(x) is called in the foo function, the local variable x has not yet been initialized, resulting in a ReferenceError.

</p>
</details>

</li>

---

33. **What will be the output ?**

```JS
const a = [1, 2, 3];
const b = a;

b.push(4);

console.log(a);
console.log(b);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: [1, 2, 3, 4] [1, 2, 3, 4]

The code creates an array a with the values [1, 2, 3]. It then creates a new variable b and assigns it to a, creating a reference to the same array.

b.push(4) adds the value 4 to the end of the array.

Since a and b reference the same array, both console.log(a) and console.log(b) will print [1, 2, 3, 4].

This is different from the previous example where ... spread operator was used, which created a new array with the same values as the original array instead of referencing the same array.

</p>
</details>

</li>

---

34. **What will be the output ?**

```JS
const companies = [
  { id: "1", name: "Facebook" },
  { id: "2", name: "Apple" },
  { id: "3", name: "Google" },
];

companies.sort((a, b) => (a.name > b.name ? -1 : 1));
console.log(companies);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: [{id: "3", name:"Google"}, {id: "1", name:"Facebook"},{id: "2", name:"Apple"}]

The comparison function takes two parameters, "a" and "b", which represent two elements being compared in the array.

If the "name" property of "a" comes before the "name" property of "b" in alphabetical order, then the function returns -1, which means "a" should come before "b" in the sorted array.

Otherwise, if the "name" property of "a" comes after the "name" property of "b" in alphabetical order, then the function returns 1, which means "b" should come before "a" in the sorted array.

</p>
</details>

</li>

---

35. **What will be the output ?**

```JS
console.log(typeof 42);
console.log(typeof "Hello");
console.log(typeof true);
console.log(typeof [1, 2, 3]);
console.log(typeof { name: "John", age: 25 });
console.log(typeof null);
console.log(typeof undefined);
console.log(typeof function () {});

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: bash Copy code number string boolean object object object undefined function

The typeof operator in JavaScript is used to determine the type of a value or expression. Here's the breakdown of the output:

typeof 42 returns "number" because 42 is a numeric value.<br>
typeof "Hello" returns "string" because "Hello" is a string.<br>
typeof true returns "boolean" because true is a boolean value.<br>
typeof [1, 2, 3] returns "object" because arrays are considered objects in JavaScript.<br>
typeof { name: "John", age: 25 } returns "object" because objects are considered objects in JavaScript.<br>
typeof null returns "object", which is a known quirk in JavaScript. null is considered an object type.<br>
typeof undefined returns "undefined" because it is a special value in JavaScript representing an uninitialized variable.<br>
typeof function() {} returns "function" because it is a function object.

</p>
</details>

</li>

---

36. **What will be the output ?**

```JS
function calculateSum() {
  console.log(result);
  var num1 = 5;
  let num2 = 10;
  const num3 = 15;
  var result = num1 + num2 + num3;
}

calculateSum();

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: undefined

In the code, the variable result is declared using the var keyword, but it is assigned a value after the console.log statement.

When JavaScript executes the function calculateSum(), it hoists the variable declaration of result to the top of the function scope. However, since the assignment of the value num1 + num2 + num3 comes after the console.log statement, the variable is undefined at the point of the console.log.

So, the code is effectively interpreted like this:

```JS
function calculateSum() {
  var result; // Variable declaration is hoisted to the top

  console.log(result); // undefined

  var num1 = 5;
  let num2 = 10;
  const num3 = 15;
  result = num1 + num2 + num3; // Assignment is performed here
}

calculateSum();
```

Since the variable result is hoisted, it exists in the function scope but does not have any assigned value until after the console.log statement. Therefore, when console.log(result) is executed, the variable result exists but is undefined.

</p>
</details>

</li>

---

37. **What will be the output ?**

```JS
let x = 10;

function updateX() {
  if (true) {
    let x = 20;
    console.log(x);
  }
  console.log(x);
}

updateX();

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 20, 10

In this code, the variable x is declared and assigned a value of 10 outside the updateX function.

Inside the function, a new block is created using an if statement. Within that block, a new variable x is declared and assigned a value of 20 using let. This creates a separate scope for the inner x, which is only accessible within the if block.

When the console.log statements are executed, the first one inside the if block will output 20, as it refers to the inner x variable. The second console.log statement outside the if block will output 10, as it refers to the outer x variable.

Therefore, the output will be 20, 10.

</p>
</details>

</li>

---

38. **What will be the output ?**

```JS
const person = {
  name: "John",
  age: 30,
};

Object.freeze(person);
person.age = 40;

console.log(person.age);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 30

In this code, the Object.freeze() method is used to make

the person object immutable. This means that the properties of the object cannot be modified.

When attempting to assign a new value to person.age after freezing the object, it does not throw an error or modify the object. Instead, it silently fails in non-strict mode and throws a TypeError in strict mode.

Since the code is not running in strict mode, the assignment person.age = 40 does not have any effect. Therefore, when console.log(person.age) is executed, it will output the original value of 30.

Hence, the output will be 30.

</p>
</details>

</li>

---

39. **What will be the output ?**

```JS
function foo() {
  let x = 1;

  function bar() {
    let y = 2;
    console.log(x + y);
  }

  bar();
}

foo();

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 3

In this code, there are two nested functions: foo and bar. The variable x is declared and assigned a value of 1 within the foo function, while the variable y is declared and assigned a value of 2 within the bar function.

When the foo function is called, it invokes the bar function. Inside the bar function, the values of x and y are accessed and summed together using console.log(x + y).

Since x is accessible within the bar function due to lexical scoping, the value of x is 1. Similarly, the value of y is 2. Therefore, the output of console.log(x + y) will be 3.

Hence, the correct answer is 3.

</p>
</details>

</li>

---

40. **What will be the output ?**

```JS
let x = 10;

function outer() {
  console.log(x);

  if (false) {
    var x = 20;
  }
}

outer();

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: undefined

In this code snippet, there's a variable hoisting issue with the var declaration inside the outer function. The variable x is declared using var within the outer function scope.

When the function outer() is called, the console.log(x) statement is executed. At this point, the variable x is hoisted to the top of the function scope and is initialized with undefined. This means that the local variable x inside the function is different from the global x.

The if (false) block will not be executed, so the assignment var x = 20; will not take place.

Thus, the console.log(x) statement inside the outer function will log the value of the locally hoisted variable x, which is undefined.

Hence, the correct answer is undefined.

</p>
</details>

</li>

---
