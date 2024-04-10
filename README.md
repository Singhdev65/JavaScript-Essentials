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

#### ➼➼➼: `new value` `another value` `new value`

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

It's updating the original objects with x\*2 values.

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

41. **What will be the output ?**

```JS
const obj = {
  a: 1,
  b: 2,
  c: {
    a: 3,
    b: 4,
  },
};

const {
  a,
  b,
  c: { a: nestedA },
} = obj;

console.log(a, b, nestedA);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1 2 3

This code snippet uses destructuring assignment to extract values from the obj object. It extracts the properties a, b, and the nested property a from the c object and assigns them to the corresponding variables a, b, and nestedA, respectively.

After destructuring, the variables will hold the following values:

a: 1 (value of obj.a)
b: 2 (value of obj.b)
nestedA: 3 (value of obj.c.a)
When console.log(a, b, nestedA) is executed, it will print 1 2 3, as the values of the variables match the above assignments.

Hence, the correct answer is 1 2 3.

</p>
</details>

</li>

---

42. **What will be the output ?**

```JS
function sum(){
    let a = 8;
    const b=2;
    var c=a+b;
}
console.log(a,b,c)
sum()
console.log(a,b,c)
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: error error

console.log(a)
// Reference error: a is not defined

console.log(b)
// Reference error: a is not defined

console.log(c)
// Reference error: a is not defined

sum()

console.log(a)
// Reference error: a is not defined

console.log(b)
// Reference error: b is not defined

console.log(c)
//Output: undefined

</p>
</details>

</li>

---

43. **What will be the output ?**

```JS
let arr=[1,2,3,4,5]
console.log(arr[2], arr.length);
arr.length=0;
console.log(arr[2], arr.length);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 3 5 undefined 0

As we can see in above code 1st questions is so easy but second is bit tricky one for second we are re-assigning the value of arr.length which logically we can do that's why after assign new value to arr.length our output is undefined for index value and 0 for arr.length.

</p>
</details>

</li>

---

44. **What will be the output ?**

```JS
for (var i = 0; i < 3; i++) {
  setTimeout(function() { alert(i); }, 1000 + i);
}
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 3 3 3

As we are using var so which is a global scope that's why as we are calling setTimeout which itself take time to RUN is call stack so within that time all Loops is finished that's why it takes last value which is 3 in each iteration.

</p>
</details>

</li>

---

45. **What will be the output ?**

```JS
for(let i = 0; i <5; i++){
	setTimeout(()=>{
		console.log(i);
    },0)
}
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 0 1 2 3 4

It relates to previous questions, as we are using let so which is a block scope that's why it keeps increase until loop didn't finished.

</p>
</details>

</li>

---

46. **What will be the output ?**

```JS
let count = 0;
(function immediate() {
  if (count === 0) {
    let count = 1;
    console.log(count);
  }
  console.log(count);
})();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 0 1

As we know code runs top to bottom so when go inside function count === 0 is TRUE as count variable defined before function called so output will be firstly 1 then 0 for second console.log().

</p>
</details>

</li>

---

47. **What will be the output ?**

```JS
console.log(1+false);
console.log(1+true);
console.log(1-false);
console.log(1+'2'-1);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1 2 1 11

internal type coersion

</p>
</details>

</li>

---

48. **What will be the output ?**

```JS
(function fnA(a) {
  return (function fnB(b) {
    console.log(a);
  })(1);
})(0);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 0

It is immediate runs function as we are calling into () and as we can see we are calling function inside function which is also a Closure concept that's why we are able to get the value of variable b

</p>
</details>

</li>

---

49. **What will be the output ?**

```JS
let randomValue = { name: "Lydia" }
randomValue = 23

if (!typeof randomValue === "string") {
	console.log("It's not a string!")
} else {
	console.log("Yay it's a string!")
}
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: Yay it's a string!

The condition within the if statement checks whether the value of !typeof randomValue is equal to "string". The ! operator converts the value to a boolean value. If the value is truthy, the returned value will be false, if the value is falsy, the returned value will be true. In this case, the returned value of typeof randomValue is the truthy value "number", meaning that the value of !typeof randomValue is the boolean value false.

!typeof randomValue === "string" always returns false, since we're actually checking false === "string". Since the condition returned false, the code block of the else statement gets run, and Yay it's a string! gets logged.

</p>
</details>

</li>

---

50. **What will be the output ?**

```JS
const createMember = ({ email, address = {}}) => {
	const validEmail = /.+\@.+\..+/.test(email)
	if (!validEmail) throw new Error("Valid email pls")

	return {
		email,
		address: address ? address : null
	}
}

const member = createMember({ email: "my@email.com" })
console.log(member)
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: { email: "my@email.com", address: {} }

The default value of address is an empty object {}. When we set the variable member equal to the object returned by the createMember function, we didn't pass a value for the address, which means that the value of the address is the default empty object {}. An empty object is a truthy value, which means that the condition of the address ? address : null conditional returns true. The value of the address is the empty object {}

</p>
</details>

</li>

---

51. **What will be the output ?**

```JS
const promise1 = Promise.resolve('First')
const promise2 = Promise.resolve('Second')
const promise3 = Promise.reject('Third')
const promise4 = Promise.resolve('Fourth')

const runPromises = async () => {
	const res1 = await Promise.all([promise1, promise2])
	const res2  = await Promise.all([promise3, promise4])
	return [res1, res2]
}

runPromises()
	.then(res => console.log(res))
	.catch(err => console.log(err))
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 'Third'

The Promise.all method runs the passed promises in parallel. If one promise fails, the Promise.all method rejects with the value of the rejected promise. In this case, promise3 is rejected with the value "Third". We’re catching the rejected value in the chained catch method on the runPromises invocation to catch any errors within the runPromises function. Only "Third" gets logged, since promise3 is rejected with this value.

</p>
</details>

</li>

---

52. **What will be the output ?**

```JS
const user = {
	email: "my@email.com",
	updateEmail: email => {
		this.email = email
	}
}

user.updateEmail("new@email.com")
console.log(user.email)
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: my@email.com

The updateEmail function is an arrow function, and is not bound to the user object. This means that the this keyword is not referring to the user object, but refers to the global scope in this case. The value of email within the user object does not get updated. When logging the value of user.email, the original value of my@email.com gets returned.

</p>
</details>

</li>

---

53. **What will be the output ?**

```JS
const animals = {};
let dog = { emoji: '🐶' }
let cat = { emoji: '🐈' }

animals[dog] = { ...dog, name: "Shubham" }
animals[cat] = { ...cat, name: "Swati" }

console.log(animals[dog])
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: { emoji: "🐈", name: "Swati" }

Object keys are converted to strings.

Since the value of dog is an object, animals[dog] actually means that we’re creating a new property called "[object Object]" equal to the new object. animals["[object Object]"] is now equal to { emoji: "🐶", name: "Shubham"}.

cat is also an object, which means that animals[cat] actually means that we’re overwriting the value of animals["[object Object]"] with the new cat properties.

Logging animals[dog], or actually animals["[object Object]"] since converting the dog object to a string results "[object Object]", returns the { emoji: "🐈", name: "Swati" }

</p>
</details>

</li>

---

54. **What will be the output ?**

```JS
const fruit = ['🍌', '🍊', '🍎']

fruit.slice(0, 1)
fruit.splice(0, 1)
fruit.unshift('🍇')

console.log(fruit)
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: ['🍇', '🍊', '🍎']

First, we invoke the slice method on the fruit array. The slice method does not modify the original array, but returns the value that it sliced off the array: the banana emoji. Then, we invoke the splice method on the fruit array. The splice method does modify the original array, which means that the fruit array now consists of ['🍊', '🍎']. At last, we invoke the unshift method on the fruit array, which modifies the original array by adding the provided value, ‘🍇’ in this case, as the first element in the array. The fruit array now consists of ['🍇', '🍊', '🍎'].

</p>
</details>

</li>

---

55. **What will be the output ?**

```JS
const user = {
	email: "e@mail.com",
	password: "12345"
}

const updateUser = ({ email, password }) => {
	if (email) {
		Object.assign(user, { email })
	}

	if (password) {
		user.password = password
	}

	return user
}

const updatedUser = updateUser({ email: "new@email.com" })

console.log(updatedUser === user)
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: true

The updateUser function updates the values of the email and password properties on user, if their values are passed to the function, after which the function returns the user object. The returned value of the updateUser function is the user object, which means that the value of updatedUser is a reference to the same user object that user points to. updatedUser === user equals true.

</p>
</details>

</li>

---

56. **What will be the output ?**

```JS
const person = {
  name: 'Tutu Singh',
  hobbies: ['swimming'],
};

function addHobby(hobby, hobbies = person.hobbies) {
  hobbies.push(hobby);
  return hobbies;
}

addHobby('running', []);
addHobby('dancing');
addHobby('baking', person.hobbies);

console.log(person.hobbies);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: ["swimming", "dancing", "baking"]

The addHobby function receives two arguments, hobby and hobbies with the default value of the hobbies array on the person object.

First, we invoke the addHobby function, and pass "running" as the value for hobby and an empty array as the value for hobbies. Since we pass an empty array as the value for hobbies, "running" gets added to this empty array.

Then, we invoke the addHobby function, and pass "dancing" as the value for hobby. We didn't pass a value for hobbies, so it gets the default value, the hobbies property on the person object. We push the hobby dancing to the person.hobbies array.

Last, we invoke the addHobby function, and pass "baking" as the value for hobby, and the person.hobbies array as the value for hobbies. We push the hobby baking to the person.hobbies array.

After pushing dancing and baking, the value of person.hobbies is ["swimming", "dancing", "baking"]

</p>
</details>

</li>

---

57. **What will be the output ?**

```JS
const add = x => x + x;

function myFunc(num = 2, value = add(num)) {
  console.log(num, value);
}

myFunc();
myFunc(3);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 2 4 and 3 6

First, we invoked myFunc() without passing any arguments. Since we didn't pass arguments, num and value got their default values: num is 2, and value is the returned value of the function add. To the add function, we pass num as an argument, which had the value of 2. add returns 4, which is the value of value.

Then, we invoked myFunc(3) and passed the value 3 as the value for the argument num. We didn't pass an argument for value. Since we didn't pass a value for the value argument, it got the default value: the returned value of the add function. To add, we pass num, which has the value of 3. add returns 6, which is the value of value.

</p>
</details>

</li>

---

58. **What will be the output ?**

```JS
const myPromise = Promise.resolve(Promise.resolve('Promise'));

function funOne() {
  setTimeout(() => console.log('Timeout 1!'), 0);
  myPromise.then(res => res).then(res => console.log(`${res} 1!`));
  console.log('Last line 1!');
}

async function funTwo() {
  const res = await myPromise;
  console.log(`${res} 2!`)
  setTimeout(() => console.log('Timeout 2!'), 0);
  console.log('Last line 2!');
}

funOne();
funTwo();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: Last line 1! Promise 2! Last line 2! Promise 1! Timeout 1! Timeout 2!

First, we invoke funOne. On the first line of funOne, we call the asynchronous setTimeout function, from which the callback is sent to the Web API. (see my article on the event loop here.)

Then we call the myPromise promise, which is an asynchronous operation. Pay attention, that now only the first then clause was added to the microtask queue.

Both the promise and the timeout are asynchronous operations, the function keeps on running while it's busy completing the promise and handling the setTimeout callback. This means that Last line 1! gets logged first, since this is not an asynchonous operation.

Since the callstack is not empty yet, the setTimeout function and promise in funOne cannot get added to the callstack yet.

In funTwo, the variable res gets Promise because Promise.resolve(Promise.resolve('Promise')) is equivalent to Promise.resolve('Promise') since resolving a promise just resolves it's value. The await in this line stops the execution of the function until it receives the resolution of the promise and then keeps on running synchronously until completion, so Promise 2! and then Last line 2! are logged and the setTimeout is sent to the Web API. If the first then clause in funOne had its own log statement, it would be printed before Promise 2!. Howewer, it executed silently and put the second then clause in microtask queue. So, the second clause will be printed after Promise 2!.

Then the call stack is empty. Promises are microtasks so they are resolved first when the call stack is empty so Promise 1! gets to be logged.

Now, since funTwo popped off the call stack, the call stack is empty. The callbacks waiting in the queue (() => console.log("Timeout 1!") from funOne, and () => console.log("Timeout 2!") from funTwo) get added to the call stack one by one. The first callback logs Timeout 1!, and gets popped off the stack. Then, the second callback logs Timeout 2!, and gets popped off the stack.

</p>
</details>

</li>

---

59. **What will be the output ?**

```JS
const emojis = ['🥑', ['✨', '✨', ['🍕', '🍕']]];

console.log(emojis.flat(1));
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: ['🥑', '✨', '✨', ['🍕', '🍕']]

With the flat method, we can create a new, flattened array. The depth of the flattened array depends on the value that we pass. In this case, we passed the value 1 (which we didn't have to, that's the default value), meaning that only the arrays on the first depth will be concatenated. ['🥑'] and ['✨', '✨', ['🍕', '🍕']] in this case. Concatenating these two arrays results in ['🥑', '✨', '✨', ['🍕', '🍕']]

</p>
</details>

</li>

---

60. **What will be the output ?**

```JS
const myPromise = Promise.resolve('yo man!, I did it');

(async () => {
  try {
    console.log(await myPromise);
  } catch {
    throw new Error(`Oops, I couldn't do it`);
  } finally {
    console.log('Oh finally!, something has happend');
  }
})();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: "yo man!, I did it" "Oh finally!, something has happend"

In the try block, we're logging the awaited value of the myPromise variable: "yo man!, I did it". Since no errors were thrown in the try block, the code in the catch block doesn't run. The code in the finally block always runs, "Oh finally!, something has happend" gets logged.

</p>
</details>

</li>

---

61. **What will be the output ?**

```JS
const randomValue = 21;

function getInfo() {
  console.log(typeof randomValue);
  const randomValue = 'Tutu Singh';
}

getInfo();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: ReferenceError

Variables declared with the const keyword are not referenceable before their initialization: this is called the temporal dead zone. In the getInfo function, the variable randomValue is scoped in the functional scope of getInfo. On the line where we want to log the value of typeof randomValue, the variable randomValue isn't initialized yet: a ReferenceError gets thrown! The engine didn't go down the scope chain since we declared the variable randomValue in the getInfo function.

</p>
</details>

</li>

---

62. **What will be the output ?**

```JS
let num = 1;
const list = ['🥳', '🤠', '🥰', '🤪'];

console.log(list[(num += 1)]);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 🥰

With the += operator, we're incrementing the value of num by 1. num had the initial value 1, so 1 + 1 is 2. The item on the second index in the list array is 🥰, console.log(list[2]) prints 🥰.

</p>
</details>

</li>

---

63. **What will be the output ?**

```JS
const person = {
  name: 'Tutu',
  age: 29,
};

const changeAge = (x = { ...person }) => (x.age += 1);
const changeAgeAndName = (x = { ...person }) => {
  x.age += 1;
  x.name = 'Singh';
};

changeAge(person);
changeAgeAndName();

console.log(person);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: { name: "Singh", age: 30 }

Both the changeAge and changeAgeAndName functions have a default parameter, namely a newly created object { ...person }. This object has copies of all the key/values in the person object.

First, we invoke the changeAge function and pass the person object as its argument. This function increases the value of the age property by 1. person is now { name: "Tutu", age: 30 }.

Then, we invoke the changeAgeAndName function, however we don't pass a parameter. Instead, the value of x is equal to a new object: { ...person }. Since it's a new object, it doesn't affect the values of the properties on the person object. person is still equal to { name: "Singh", age: 30 }

</p>
</details>

</li>

---

64. **What will be the output ?**

```JS
console.log(`${(x => x)('I love')} javaScript`);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: I love javaScript

Expressions within template literals are evaluated first. This means that the string will contain the returned value of the expression, the immediately invoked function (x => x)('I love') in this case. We pass the value 'I love' as an argument to the x => x arrow function. x is equal to 'I love', which gets returned. This results in I love javaScript

</p>
</details>

</li>

---

65. **What will be the output ?**

```JS
let name = 'Tutu';

function getName() {
  console.log(name);
  let name = 'Yadav';
}

getName();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: ReferenceError

Each function has its own execution context (or scope). The getName function first looks within its own context (scope) to see if it contains the variable name we're trying to access. In this case, the getName function contains its own name variable: we declare the variable name with the let keyword, and with the value of 'Sarah'.

Variables with the let keyword (and const) are hoisted, but unlike var, don't get initialized. They are not accessible before the line we declare (initialize) them. This is called the "temporal dead zone". When we try to access the variables before they are declared, JavaScript throws a ReferenceError.

If we wouldn't have declared the name variable within the getName function, the javascript engine would've looked down the scope chain. The outer scope has a variable called name with the value of Tutu. In that case, it would've logged Tutu.

```JS
let name = 'Tutu';

function getName() {
  console.log(name);
}

getName(); // Tutu

```

</p>
</details>

</li>

---

66. **What will be the output ?**

```JS
const food = ['🍕', '🍫', '🥑', '🍔'];
const info = { favoriteFood: food[0] };

info.favoriteFood = '🍝';

console.log(food);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: ['🍕', '🍫', '🥑', '🍔']

We set the value of the favoriteFood property on the info object equal to the string with the pizza emoji, '🍕'. A string is a primitive data type. In JavaScript, primitive data types don't interact by reference.

In JavaScript, primitive data types (everything that's not an object) interact by value. In this case, we set the value of the favoriteFood property on the info object equal to the value of the first element in the food array, the string with the pizza emoji in this case ('🍕'). A string is a primitive data type, and interact by value (see my blogpost if you're interested in learning more)

Then, we change the value of the favoriteFood property on the info object. The food array hasn't changed, since the value of favoriteFood was merely a copy of the value of the first element in the array, and doesn't have a reference to the same spot in memory as the element on food[0]. When we log food, it's still the original array, ['🍕', '🍫', '🥑', '🍔'].

</p>
</details>

</li>

---

67. **Which of these methods modifies the original array?**

```JS
const emojis = ['✨', '🥑', '😍'];

emojis.map(x => x + '✨');
emojis.filter(x => x !== '🥑');
emojis.find(x => x !== '🥑');
emojis.reduce((acc, cur) => acc + '✨');
emojis.slice(1, 2, '✨');
emojis.splice(1, 2, '✨');
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: splice

With splice method, we modify the original array by deleting, replacing or adding elements. In this case, we removed 2 items from index 1 (we removed '🥑' and '😍') and added the ✨ emoji instead.

map, filter and slice return a new array, find returns an element, and reduce returns a reduced value.

</p>
</details>

</li>

---

68. **What's its value?**

```JS
const colorConfig = {
  red: true,
  blue: false,
  green: true,
  black: true,
  yellow: false,
};

const colors = ['pink', 'red', 'blue'];

console.log(colorConfig.colors[1]);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: TypeError

In JavaScript, we have two ways to access properties on an object: bracket notation, or dot notation. In this example, we use dot notation (colorConfig.colors) instead of bracket notation (colorConfig["colors"]).

With dot notation, JavaScript tries to find the property on the object with that exact name. In this example, JavaScript tries to find a property called colors on the colorConfig object. There is no property called colors, so this returns undefined. Then, we try to access the value of the first element by using [1]. We cannot do this on a value that's undefined, so it throws a TypeError: Cannot read property '1' of undefined.

JavaScript interprets (or unboxes) statements. When we use bracket notation, it sees the first opening bracket [ and keeps going until it finds the closing bracket ]. Only then, it will evaluate the statement. If we would've used colorConfig[colors[1]], it would have returned the value of the red property on the colorConfig object.

</p>
</details>

</li>

---

69. **What will be the output ?**

```JS
function compareMembers(person1, person2 = person) {
  if (person1 !== person2) {
    console.log('Not the same!');
  } else {
    console.log('They are the same!');
  }
}

const person = { name: 'Tutu' };

compareMembers(person);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: They are the same!

Objects are passed by reference. When we check objects for strict equality (===), we're comparing their references.

We set the default value for person2 equal to the person object, and passed the person object as the value for person1.

This means that both values have a reference to the same spot in memory, thus they are equal.

The code block in the else statement gets run, and They are the same! gets logged.

</p>
</details>

</li>

---

70. **What will be the output ?**

```JS
const set = new Set();

set.add(1);
set.add('Tutu');
set.add({ name: 'Tutu' });

for (let item of set) {
  console.log(item + 2);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 3, Tutu2, [object Object]2

The + operator is not only used for adding numerical values, but we can also use it to concatenate strings. Whenever the JavaScript engine sees that one or more values are not a number, it coerces the number into a string.

The first one is 1, which is a numerical value. 1 + 2 returns the number 3.

However, the second one is a string "Tutu". "Tutu" is a string and 2 is a number: 2 gets coerced into a string. "Tutu" and "2" get concatenated, which results in the string "Tutu2".

{ name: "Tutu" } is an object. Neither a number nor an object is a string, so it stringifies both. Whenever we stringify a regular object, it becomes "[object Object]". "[object Object]" concatenated with "2" becomes "[object Object]2".

</p>
</details>

</li>

---

71. **What will be the output ?**

```JS
const myPromise = () => Promise.resolve('I have resolved!');

function firstFunction() {
  myPromise().then(res => console.log(res));
  console.log('second');
}

async function secondFunction() {
  console.log(await myPromise());
  console.log('second');
}

firstFunction();
secondFunction();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: second, I have resolved! and I have resolved!, second

With a promise, we basically say I want to execute this function, but I'll put it aside for now while it's running since this might take a while. Only when a certain value is resolved (or rejected), and when the call stack is empty, I want to use this value.

We can get this value with both .then and the await keywords in an async function. Although we can get a promise's value with both .then and await, they work a bit differently.

In the firstFunction, we (sort of) put the myPromise function aside while it was running, but continued running the other code, which is console.log('second') in this case. Then, the function resolved with the string I have resolved, which then got logged after it saw that the callstack was empty.

With the await keyword in secondFunction, we literally pause the execution of an async function until the value has been resolved before moving to the next line.

This means that it waited for the myPromise to resolve with the value I have resolved, and only once that happened, we moved to the next line: second got logged.

</p>
</details>

</li>

---

72. **What will be the output ?**

```JS
const one = false || {} || null;
const two = null || false || '';
const three = [] || 0 || true;

console.log(one, two, three);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: {} "" []

With the || operator, we can return the first truthy operand. If all values are falsy, the last operand gets returned.

(false || {} || null): the empty object {} is a truthy value. This is the first (and only) truthy value, which gets returned. one is equal to {}.

(null || false || ""): all operands are falsy values. This means that the last operand, "" gets returned. two is equal to "".

([] || 0 || ""): the empty array[] is a truthy value. This is the first truthy value, which gets returned. three is equal to [].

</p>
</details>

</li>

---

73. **What will be the output ?**

```JS
const output = `${[] && 'Im'}possible!
You should${'' && `n't`} see a therapist after so much JavaScript lol`;
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: Impossible! You should see a therapist after so much JavaScript lol

[] is a truthy value. With the && operator, the right-hand value will be returned if the left-hand value is a truthy value. In this case, the left-hand value [] is a truthy value, so "Im' gets returned.

"" is a falsy value. If the left-hand value is falsy, nothing gets returned. n't doesn't get returned.

</p>
</details>

</li>

---

74. **What will be the output ?**

```JS
const getList = ([x, ...y]) => [x, y]
const getUser = user => { name: user.name, age: user.age }

const list = [1, 2, 3, 4]
const user = { name: "Tutu", age: 29 }

console.log(getList(list))
console.log(getUser(user))
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: [1, [2, 3, 4]] and SyntaxError

The getList function receives an array as its argument. Between the parentheses of the getList function, we destructure this array right away. You could see this as:

[x, ...y] = [1, 2, 3, 4]

With the rest parameter ...y, we put all "remaining" arguments in an array. The remaining arguments are 2, 3 and 4 in this case. The value of y is an array, containing all the rest parameters. The value of x is equal to 1 in this case, so when we log [x, y], [1, [2, 3, 4]] gets logged.

The getUser function receives an object. With arrow functions, we don't have to write curly brackets if we just return one value. However, if you want to instantly return an object from an arrow function, you have to write it between parentheses, otherwise everything between the two braces will be interpreted as a block statement. In this case the code between the braces is not a valid JavaScript code, so a SyntaxError gets thrown.

The following function would have returned an object:

const getUser = user => ({ name: user.name, age: user.age })

</p>
</details>

</li>

---

75. **What will be the output ?**

```JS
const info = {
  [Symbol('a')]: 'b',
};

console.log(info);
console.log(Object.keys(info));
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: {Symbol('a'): 'b'} and []

A Symbol is not enumerable. The Object.keys method returns all enumerable key properties on an object. The Symbol won't be visible, and an empty array is returned. When logging the entire object, all properties will be visible, even non-enumerable ones.

This is one of the many qualities of a symbol: besides representing an entirely unique value (which prevents accidental name collision on objects, for example when working with 2 libraries that want to add properties to the same object), you can also "hide" properties on objects this way (although not entirely. You can still access symbols using the Object.getOwnPropertySymbols() method).

</p>
</details>

</li>

---

76. **What will be the output ?**

```JS
function nums(a, b) {
  if (a > b) console.log('a is bigger');
  else console.log('b is bigger');
  return
  a + b;
}

console.log(nums(4, 2));
console.log(nums(1, 2));
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: a is bigger, undefined and b is bigger, undefined

In JavaScript, we don't have to write the semicolon (;) explicitly, however the JavaScript engine still adds them after statements. This is called Automatic Semicolon Insertion. A statement can for example be variables, or keywords like throw, return, break, etc.

Here, we wrote a return statement, and another value a + b on a new line. However, since it's a new line, the engine doesn't know that it's actually the value that we wanted to return. Instead, it automatically added a semicolon after return. You could see this as:

return;
a + b;

This means that a + b is never reached, since a function stops running after the return keyword. If no value gets returned, like here, the function returns undefined. Note that there is no automatic insertion after if/else statements!

</p>
</details>

</li>

---

77. **What will be the output ?**

```JS
function getItems(fruitList, ...args, favoriteFruit) {
  return [...fruitList, ...args, favoriteFruit]
}

getItems(["banana", "apple"], "pear", "orange")
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: SyntaxError

...args is a rest parameter. The rest parameter's value is an array containing all remaining arguments, and can only be the last parameter! In this example, the rest parameter was the second parameter. This is not possible, and will throw a syntax error.

function getItems(fruitList, favoriteFruit, ...args) {
return [...fruitList, ...args, favoriteFruit];
}

getItems(['banana', 'apple'], 'pear', 'orange');
The above example works. This returns the array [ 'banana', 'apple', 'orange', 'pear' ]

</p>
</details>

</li>

---

78. **What will be the output ?**

```JS
const person = {
  name: 'Tutu',
  age: 4,
};

for (const [x, y] of Object.entries(person)) {
  console.log(x, y);
}
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: name Tutu and age 4

Object.entries(person) returns an array of nested arrays, containing the keys and objects:

[ [ 'name', 'Lydia' ], [ 'age', 21 ] ]

Using the for-of loop, we can iterate over each element in the array, the subarrays in this case. We can destructure the subarrays instantly in the for-of loop, using const [x, y]. x is equal to the first element in the subarray, y is equal to the second element in the subarray.

The first subarray is [ "name", "Lydia" ], with x equal to "name", and y equal to "Lydia", which get logged. The second subarray is [ "age", 21 ], with x equal to "age", and y equal to 21, which get logged.

</p>
</details>

</li>

---

79. **What will be the output ?**

```JS
function giveTutuPizza() {
  return 'Here is pizza!';
}

const giveTutuChocolate = () =>
  "Here's chocolate... now go hit the gym already.";

console.log(giveTutuPizza.prototype);
console.log(giveTutuChocolate.prototype);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: { constructor: ...} undefined

Regular functions, such as the giveTutuPizza function, have a prototype property, which is an object (prototype object) with a constructor property. Arrow functions however, such as the giveTutuChocolate function, do not have this prototype property. undefined gets returned when trying to access the prototype property using giveTutuChocolate.prototype.

</p>
</details>

</li>

---

80. **What will be the output ?**

```JS
let newList = [1, 2, 3].push(4);

console.log(newList.push(5));
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: Error

The .push method returns the new length of the array, not the array itself! By setting newList equal to [1, 2, 3].push(4), we set newList equal to the new length of the array: 4.

Then, we try to use the .push method on newList. Since newList is the numerical value 4, we cannot use the .push method: a TypeError is thrown.

</p>
</details>

</li>

---

81. **What will be the output ?**

```JS
console.log('I want pizza'[0]);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: "I"

In order to get a character at a specific index of a string, you can use bracket notation. The first character in the string has index 0, and so on. In this case, we want to get the element with index 0, the character "I', which gets logged.

Note that this method is not supported in IE7 and below. In that case, use .charAt().

</p>
</details>

</li>

---

82. **What will be the output ?**

```JS
function checkAge(age) {
  if (age < 18) {
    const message = "Sorry, you're too young.";
  } else {
    const message = "Yay! You're old enough!";
  }

  return message;
}

console.log(checkAge(21));
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: ReferenceError

Variables with the const and let keywords are block-scoped. A block is anything between curly brackets ({ }). In this case, the curly brackets of the if/else statements. You cannot reference a variable outside of the block it's declared in, a ReferenceError gets thrown.

</p>
</details>

</li>

---

83. **What will be the output ?**

```JS
const person = {
  name: 'Tutu',
  age: 4,
};

let city = person.city;
city = 'Noida';

console.log(person);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: { name: "Tutu", age: 4 }

We set the variable city equal to the value of the property called city on the person object. There is no property on this object called city, so the variable city has the value of undefined.

Note that we are not referencing the person object itself! We simply set the variable city equal to the current value of the city property on the person object.

Then, we set city equal to the string "Noida". This doesn't change the person object: there is no reference to that object.

When logging the person object, the unmodified object gets returned.

</p>
</details>

</li>

---

84. **What will be the output ?**

```JS
var status = '😎';

setTimeout(() => {
  const status = '😍';

  const data = {
    status: '🥑',
    getStatus() {
      return this.status;
    },
  };

  console.log(data.getStatus());
  console.log(data.getStatus.call(this));
}, 0);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: "🥑" and "😎"

The value of the this keyword is dependent on where you use it. In a method, like the getStatus method, the this keyword refers to the object that the method belongs to. The method belongs to the data object, so this refers to the data object. When we log this.status, the status property on the data object gets logged, which is "🥑".

With the call method, we can change the object to which the this keyword refers. In functions, the this keyword refers to the the object that the function belongs to. We declared the setTimeout function on the global object, so within the setTimeout function, the this keyword refers to the global object. On the global object, there is a variable called status with the value of "😎". When logging this.status, "😎" gets logged.

</p>
</details>

</li>

---

85. **What will be the output ?**

```JS
const add = () => {
  const cache = {};
  return num => {
    if (num in cache) {
      return `From cache! ${cache[num]}`;
    } else {
      const result = num + 10;
      cache[num] = result;
      return `Calculated! ${result}`;
    }
  };
};

const addFunction = add();
console.log(addFunction(10));
console.log(addFunction(10));
console.log(addFunction(5 * 2));
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: Calculated! 20 From cache! 20 From cache! 20

The add function is a memoized function. With memoization, we can cache the results of a function in order to speed up its execution. In this case, we create a cache object that stores the previously returned values.

If we call the addFunction function again with the same argument, it first checks whether it has already gotten that value in its cache. If that's the case, the cache value will be returned, which saves execution time. Otherwise, if it's not cached, it will calculate the value and store it afterward.

We call the addFunction function three times with the same value: on the first invocation, the value of the function when num is equal to 10 isn't cached yet. The condition of the if-statement num in cache returns false, and the else block gets executed: Calculated! 20 gets logged, and the value of the result gets added to the cache object. cache now looks like { 10: 20 }.

The second time, the cache object contains the value that gets returned for 10. The condition of the if-statement num in cache returns true, and 'From cache! 20' gets logged.

The third time, we pass 5 \* 2 to the function which gets evaluated to 10. The cache object contains the value that gets returned for 10. The condition of the if-statement num in cache returns true, and 'From cache! 20' gets logged.

</p>
</details>

</li>

---

86. **What will be the output ?**

```JS
const box = { x: 10, y: 20 };

Object.freeze(box);

const shape = box;
shape.x = 100;

console.log(shape);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: { x: 10, y: 20 }

Object.freeze makes it impossible to add, remove, or modify properties of an object (unless the property's value is another object).

When we create the variable shape and set it equal to the frozen object box, shape also refers to a frozen object. You can check whether an object is frozen by using Object.isFrozen. In this case, Object.isFrozen(shape) would return true, since the variable shape has a reference to a frozen object.

Since shape is frozen, and since the value of x is not an object, we cannot modify the property x. x is still equal to 10, and { x: 10, y: 20 } gets logged.

</p>
</details>

</li>

---

87. **What will be the output ?**

```JS
function addToList(item, list) {
  return list.push(item);
}

const result = addToList('apple', ['banana']);
console.log(result);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 2

The .push() method returns the length of the new array! Previously, the array contained one element (the string "banana") and had a length of 1. After adding the string "apple" to the array, the array contains two elements, and has a length of 2. This gets returned from the addToList function.

The push method modifies the original array. If you wanted to return the array from the function rather than the length of the array, you should have returned list after pushing item to it.

</p>
</details>

</li>

---

88. **What will be the output ?**

```JS
console.log(String.raw`Hello\nworld`);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: Hello\nworld

String.raw returns a string where the escapes (\n, \v, \t etc.) are ignored! Backslashes can be an issue since you could end up with something like:

const path = `C:\Documents\Projects\table.html`

Which would result in:

"C:DocumentsProjects able.html"

With String.raw, it would simply ignore the escape and print:

C:\Documents\Projects\table.html

In this case, the string is Hello\nworld, which gets logged.

</p>
</details>

</li>

---

89. **What will be the output ?**

```JS
async function getData() {
  return await Promise.resolve('I made it!');
}

const data = getData();
console.log(data);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: Promise {<pending>}

An async function always returns a promise. The await still has to wait for the promise to resolve: a pending promise gets returned when we call getData() in order to set data equal to it.

If we wanted to get access to the resolved value "I made it", we could have used the .then() method on data:

data.then(res => console.log(res))

This would've logged "I made it!"

</p>
</details>

</li>

---

90. **What will be the output ?**

```JS
console.log(Number(2) === Number(2));
console.log(Boolean(false) === Boolean(false));
console.log(Symbol('foo') === Symbol('foo'));
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: true, true, false

Every Symbol is entirely unique. The purpose of the argument passed to the Symbol is to give the Symbol a description. The value of the Symbol is not dependent on the passed argument. As we test equality, we are creating two entirely new symbols: the first Symbol('foo'), and the second Symbol('foo'). These two values are unique and not equal to each other, Symbol('foo') === Symbol('foo') returns false.

</p>
</details>

</li>

---

91. **What will be the output ?**

```JS
[1, 2, 3, 4].reduce((x, y) => console.log(x, y));
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1 2 and undefined 3 and undefined 4

The first argument that the reduce method receives is the accumulator, x in this case. The second argument is the current value, y. With the reduce method, we execute a callback function on every element in the array, which could ultimately result in one single value.

In this example, we are not returning any values, we are simply logging the values of the accumulator and the current value.

The value of the accumulator is equal to the previously returned value of the callback function. If you don't pass the optional initialValue argument to the reduce method, the accumulator is equal to the first element on the first call.

On the first call, the accumulator (x) is 1, and the current value (y) is 2. We don't return from the callback function, we log the accumulator, and the current values: 1 and 2 get logged.

If you don't return a value from a function, it returns undefined. On the next call, the accumulator is undefined, and the current value is 3. undefined and 3 get logged.

On the fourth call, we again don't return from the callback function. The accumulator is again undefined, and the current value is 4. undefined and 4 get logged.

</p>
</details>

</li>

---

92. **What will be the output ?**

```JS
const value = { number: 10 };

const multiply = (x = { ...value }) => {
  console.log((x.number *= 2));
};

multiply();
multiply();
multiply(value);
multiply(value);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 20, 20, 20, 40

In ES6, we can initialize parameters with a default value. The value of the parameter will be the default value, if no other value has been passed to the function, or if the value of the parameter is "undefined". In this case, we spread the properties of the value object into a new object, so x has the default value of { number: 10 }.

The default argument is evaluated at call time! Every time we call the function, a new object is created. We invoke the multiply function the first two times without passing a value: x has the default value of { number: 10 }. We then log the multiplied value of that number, which is 20.

The third time we invoke multiply, we do pass an argument: the object called value. The _= operator is actually shorthand for x.number = x.number _ 2: we modify the value of x.number, and log the multiplied value 20.

The fourth time, we pass the value object again. x.number was previously modified to 20, so x.number \*= 2 logs 40.

</p>
</details>

</li>

---

93. **What will be the output ?**

```JS
let num = 10;

const increaseNumber = () => num++;
const increasePassedNumber = number => number++;

const num1 = increaseNumber();
const num2 = increasePassedNumber(num1);

console.log(num1);
console.log(num2);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 10, 10

The unary operator ++ first returns the value of the operand, then increments the value of the operand. The value of num1 is 10, since the increaseNumber function first returns the value of num, which is 10, and only increments the value of num afterward.

num2 is 10, since we passed num1 to the increasePassedNumber. number is equal to 10(the value of num1). Again, the unary operator ++ first returns the value of the operand, then increments the value of the operand. The value of number is 10, so num2 is equal to 10.

</p>
</details>

</li>

---

94. **What will be the output ?**

```JS
const numbers = [1, 2, 3, 4, 5];
const [y] = numbers;

console.log(y);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1

We can unpack values from arrays or properties from objects through destructuring. For example:

[a, b] = [1, 2];

The value of a is now 1, and the value of b is now 2. What we actually did in the question, is:

[y] = [1, 2, 3, 4, 5];

This means that the value of y is equal to the first value in the array, which is the number 1. When we log y, 1 is returned.

</p>
</details>

</li>

---

95. **What will be the output ?**

```JS
const user = { name: 'Tutu', age: 4 };
const admin = { admin: true, ...user };

console.log(admin);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: { admin: true, name: "Tutu", age: 4 }

It's possible to combine objects using the spread operator .... It lets you create copies of the key/value pairs of one object, and add them to another object. In this case, we create copies of the user object, and add them to the admin object. The admin object now contains the copied key/value pairs, which results in { admin: true, name: "Tutu", age: 4 }.

</p>
</details>

</li>

---

96. **What will be the output ?**

```JS
const name = 'Tutu';
age = 4;

console.log(delete name);
console.log(delete age);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: false, true

The delete operator returns a boolean value: true on a successful deletion, else it'll return false. However, variables declared with the var, const, or let keywords cannot be deleted using the delete operator.

The name variable was declared with a const keyword, so its deletion is not successful: false is returned. When we set age equal to 21, we actually added a property called age to the global object. You can successfully delete properties from objects this way, also the global object, so delete age returns true.

</p>
</details>

</li>

---

97. **What will be the output ?**

```JS
const set = new Set([1, 1, 2, 3, 4]);

console.log(set);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: {1, 2, 3, 4}

The Set object is a collection of unique values: a value can only occur once in a set.

We passed the iterable [1, 1, 2, 3, 4] with a duplicate value 1. Since we cannot have two of the same values in a set, one of them is removed. This results in {1, 2, 3, 4}.

</p>
</details>

</li>

---

98. **What will be the output ?**

```JS
(() => {
  let x = (y = 10);
})();

console.log(typeof x);
console.log(typeof y);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: "undefined", "number"

let x = (y = 10); is actually shorthand for:

y = 10;
let x = y;
When we set y equal to 10, we actually add a property y to the global object (window in the browser, global in Node). In a browser, window.y is now equal to 10.

Then, we declare a variable x with the value of y, which is 10. Variables declared with the let keyword are block scoped, they are only defined within the block they're declared in; the immediately invoked function expression (IIFE) in this case. When we use the typeof operator, the operand x is not defined: we are trying to access x outside of the block it's declared in. This means that x is not defined. Values who haven't been assigned a value or declared are of type "undefined". console.log(typeof x) returns "undefined".

However, we created a global variable y when setting y equal to 10. This value is accessible anywhere in our code. y is defined, and holds a value of type "number". console.log(typeof y) returns "number".

</p>
</details>

</li>

---

99. **What will be the output ?**

```JS
function Car() {
  this.make = 'Tata';
  return { make: 'BMW' };
}

const myCar = new Car();
console.log(myCar.make);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: BMW

When a constructor function is called with the new keyword, it creates an object and sets the this keyword to refer to that object. By default, if the constructor function doesn't explicitly return anything, it will return the newly created object.

In this case, the constructor function Car explicitly returns a new object with make set to "BMW", which overrides the default behavior. Therefore, when new Car() is called, the returned object is assigned to myCar, resulting in the output being "BMW" when myCar.make is accessed.

</p>
</details>

</li>

---

100. **What will be the output ?**

```JS
function getInfo(member, year) {
  member.name = 'Tutu';
  year = '2018';
}

const person = { name: 'Naina' };
const birthYear = '2020';

getInfo(person, birthYear);

console.log(person, birthYear);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: { name: "Tutu" }, "2020"

Arguments are passed by value, unless their value is an object, then they're passed by reference. birthYear is passed by value, since it's a string, not an object. When we pass arguments by value, a copy of that value is created.

The variable birthYear has a reference to the value "2020". The argument year also has a reference to the value "2020", but it's not the same value as birthYear has a reference to. When we update the value of year by setting year equal to "1998", we are only updating the value of year. birthYear is still equal to "2020".

The value of person is an object. The argument member has a (copied) reference to the same object. When we modify a property of the object member has a reference to, the value of person will also be modified, since they both have a reference to the same object. person's name property is now equal to the value "Tutu"

</p>
</details>

</li>

---

101. **What will be the output ?**

```JS
[1, 2, 3].map(num => {
  if (typeof num === 'number') return;
  return num * 2;
});
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: [undefined, undefined, undefined]

When mapping over the array, the value of num is equal to the element it’s currently looping over. In this case, the elements are numbers, so the condition of the if statement typeof num === "number" returns true. The map function creates a new array and inserts the values returned from the function.

However, we don’t return a value. When we don’t return a value from the function, the function returns undefined. For every element in the array, the function block gets called, so for each element we return undefined.

</p>
</details>

</li>

---

102. **What will be the output ?**

```JS
const num = parseInt('7*6', 10);
console.log(num);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 7

Only the first number in the string is returned. Based on the radix (the second argument in order to specify what type of number we want to parse it to: base 10, hexadecimal, octal, binary, etc.), the parseInt checks whether the characters in the string are valid. Once it encounters a character that isn't a valid number in the radix, it stops parsing and ignores the following characters.

- is not a valid number. It only parses "7" into the decimal 7. num now holds the value of 7.

</p>
</details>

</li>

---

103. **What will be the output ?**

```JS
console.log(3 + 4 + '5');
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: "75"

Operator associativity is the order in which the compiler evaluates the expressions, either left-to-right or right-to-left. This only happens if all operators have the same precedence. We only have one type of operator: +. For addition, the associativity is left-to-right.

3 + 4 gets evaluated first. This results in the number 7.

7 + '5' results in "75" because of coercion. JavaScript converts the number 7 into a string, see question 15. We can concatenate two strings using the +operator. "7" + "5" results in "75".

</p>
</details>

</li>

---

104. **What will be the output ?**

```JS
const person = {
  name: 'Tutu',
  age: 4,
};

for (const item in person) {
  console.log(item);
}
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: "name", "age"

With a for-in loop, we can iterate through object keys, in this case name and age. Under the hood, object keys are strings (if they're not a Symbol). On every loop, we set the value of item equal to the current key it’s iterating over. First, item is equal to name, and gets logged. Then, item is equal to age, which gets logged.

</p>
</details>

</li>

---

105. **What will be the output ?**

```JS
const firstPromise = new Promise((res, rej) => {
  setTimeout(res, 500, 'one');
});

const secondPromise = new Promise((res, rej) => {
  setTimeout(res, 100, 'two');
});

Promise.race([firstPromise, secondPromise]).then(res => console.log(res));
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: "two"

When we pass multiple promises to the Promise.race method, it resolves/rejects the first promise that resolves/rejects. To the setTimeout method, we pass a timer: 500ms for the first promise (firstPromise), and 100ms for the second promise (secondPromise). This means that the secondPromise resolves first with the value of 'two'. res now holds the value of 'two', which gets logged.

</p>
</details>

</li>

---

106. **What will be the output ?**

```JS
[[0, 1], [2, 3]].reduce(
  (acc, cur) => {
    return acc.concat(cur);
  },
  [1, 2],
);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: [1, 2, 0, 1, 2, 3]

[1, 2] is our initial value. This is the value we start with, and the value of the very first acc. During the first round, acc is [1,2], and cur is [0, 1]. We concatenate them, which results in [1, 2, 0, 1].

Then, [1, 2, 0, 1] is acc and [2, 3] is cur. We concatenate them, and get [1, 2, 0, 1, 2, 3]

</p>
</details>

</li>

---

107. **What will be the output ?**

```JS
(() => {
  let x, y;
  try {
    throw new Error();
  } catch (x) {
    (x = 1), (y = 2);
    console.log(x);
  }
  console.log(x);
  console.log(y);
})();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1 undefined 2

The catch block receives the argument x. This is not the same x as the variable when we pass arguments. This variable x is block-scoped.

Later, we set this block-scoped variable equal to 1, and set the value of the variable y. Now, we log the block-scoped variable x, which is equal to 1.

Outside of the catch block, x is still undefined, and y is 2. When we want to console.log(x) outside of the catch block, it returns undefined, and y returns 2.

</p>
</details>

</li>

---

108. **What will be the output ?**

```JS
const numbers = [1, 2, 3];
numbers[10] = 11;
console.log(numbers);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: [1, 2, 3, empty x 7, 11]

When you set a value to an element in an array that exceeds the length of the array, JavaScript creates something called "empty slots". These actually have the value of undefined, but you will see something like:

[1, 2, 3, empty x 7, 11]

depending on where you run it (it's different for every browser, node, etc.)

</p>
</details>

</li>

---

109. **What will be the output ?**

```JS
console.log(typeof typeof 1);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: "string"

typeof 1 returns "number". typeof "number" returns "string"

</p>
</details>

</li>

---

110. **What will be the output ?**

```JS
function sayHi() {
  return (() => 0)();
}

console.log(typeof sayHi());
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: "number"

The sayHi function returns the returned value of the immediately invoked function expression (IIFE). This function returned 0, which is type "number".

FYI: typeof can return the following list of values: undefined, boolean, number, bigint, string, symbol, function and object. Note that typeof null returns "object".

</p>
</details>

</li>

---

111. **What will be the output ?**

```JS
const person = { name: 'Tutu' };

function sayHi(age) {
  return `${this.name} is ${age}`;
}

console.log(sayHi.call(person, 4));
console.log(sayHi.bind(person, 4));
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: Tutu is 4 function

With both, we can pass the object to which we want the this keyword to refer to. However, .call is also executed immediately!

.bind. returns a copy of the function, but with a bound context! It is not executed immediately.

</p>
</details>

</li>

---

112. **What will be the output ?**

```JS
for (let i = 1; i < 5; i++) {
  if (i === 3) continue;
  console.log(i);
}
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1 2 4

The continue statement skips an iteration if a certain condition returns true.

</p>
</details>

</li>

---

113. **What will be the output ?**

```JS
const obj = { a: 'one', b: 'two', a: 'three' };
console.log(obj);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: { a: "three", b: "two" }

If you have two keys with the same name, the key will be replaced. It will still be in its first position, but with the last specified value.

</p>
</details>

</li>

---

114. **What will be the output ?**

```JS
const obj = { 1: 'a', 2: 'b', 3: 'c' };
const set = new Set([1, 2, 3, 4, 5]);

obj.hasOwnProperty('1');
obj.hasOwnProperty(1);
set.has('1');
set.has(1);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: true true false true

All object keys (excluding Symbols) are strings under the hood, even if you don't type it yourself as a string. This is why obj.hasOwnProperty('1') also returns true.

It doesn't work that way for a set. There is no '1' in our set: set.has('1') returns false. It has the numeric type 1, set.has(1) returns true.

</p>
</details>

</li>

---

115. **What will be the output ?**

```JS
function checkAge(data) {
  if (data === { age: 18 }) {
    console.log('You are an adult!');
  } else if (data == { age: 18 }) {
    console.log('You are still an adult.');
  } else {
    console.log(`Hmm.. You don't have an age I guess`);
  }
}

checkAge({ age: 18 });
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: Hmm.. You don't have an age I guess

When testing equality, primitives are compared by their value, while objects are compared by their reference. JavaScript checks if the objects have a reference to the same location in memory.

The two objects that we are comparing don't have that: the object we passed as a parameter refers to a different location in memory than the object we used in order to check equality.

This is why both { age: 18 } === { age: 18 } and { age: 18 } == { age: 18 } return false.

</p>
</details>

</li>

---

116. **What will be the output ?**

```JS
let number = 0;
console.log(number++);
console.log(++number);
console.log(number);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 0 2 2

The postfix unary operator ++:

Returns the value (this returns 0)
Increments the value (number is now 1)
The prefix unary operator ++:

Increments the value (number is now 2)
Returns the value (this returns 2)
This returns 0 2 2.

</p>
</details>

</li>

---

117. **What will be the output ?**

```JS
const shape = {
  radius: 10,
  diameter() {
    return this.radius * 2;
  },
  perimeter: () => 2 * Math.PI * this.radius,
};

console.log(shape.diameter());
console.log(shape.perimeter());
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 20 and NaN

Note that the value of diameter is a regular function, whereas the value of perimeter is an arrow function.

With arrow functions, the this keyword refers to its current surrounding scope, unlike regular functions! This means that when we call perimeter, it doesn't refer to the shape object, but to its surrounding scope (window for example).

Since there is no value radius in the scope of the arrow function, this.radius returns undefined which, when multiplied by 2 \* Math.PI, results in NaN.

</p>
</details>

</li>

---

118. **What will be the output ?**

```JS
var trees = ["xyz", "xxxx", "test", "ryan", "apple"];
delete trees[3];
console.log(trees.length);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 5

The code above will output `5` as output. When we used `delete` operator for deleting an array element then, the array length is not affected by this. This holds even if you deleted all elements of an array using `delete` operator.
So when delete operator removes an array element that deleted element is no longer present in the array. In place of value at deleted index undefined x 1 in chrome and undefined is placed at the index. If you do console.log(trees) output ["xyz", "xxxx", "test", undefined × 1, "apple"] in Chrome and in Firefox ["xyz", "xxxx", "test", undefined, "apple"].

</p>
</details>

</li>

---

119. **What will be the output ?**

```JS
var bar = true;
console.log(bar + 0);
console.log(bar + "xyz");
console.log(bar + true);
console.log(bar + false);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1, "truexyz", 2, 1

Number + Number -> Addition
Boolean + Number -> Addition
Boolean + Boolean -> Addition
Number + String -> Concatenation
String + Boolean -> Concatenation
String + String -> Concatenation

</p>
</details>

</li>

---

120.  **What will be the output ?**

```JS
var salary = "1000$";

(function () {
  console.log("Original salary was " + salary);

  var salary = "5000$";

  console.log("My New Salary " + salary);
})();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: undefined, 5000$

The code above will output: undefined, 5000$ because of hoisting. In the code presented above, you might be expecting salary to retain it values from outer scope until the point that salary was re-declared in the inner scope. But due to hoisting salary value was undefined instead. To understand it better have a look of the following code, here salary variable is hoisted and declared at the top in function scope. When we print its value using console.log the result is undefined. Afterwards the variable is redeclared and the new value "5000$" is assigned to it.

</p>
</details>

</li>

---

121.  **What will be the output ?**

```JS
function User(name) {
  this.name = name || "JsGeeks";
}

var person = new User("xyz")["location"] = "USA";
console.log(person);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: USA

The output of above code would be "USA". Here new User("xyz") creates a brand new object and created property location on that and USA has been assigned to object property location and that has been referenced by the person.

</p>
</details>

</li>

---

122.  **What will be the output ?**

```JS
var strA = "hi there";
var strB = strA;
strB="bye there!";
console.log (strA)
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 'hi there'

The output will be 'hi there' because we're dealing with strings here. Strings are passed by value, that is, copied.

</p>
</details>

</li>

---

123.  **What will be the output ?**

```JS
var objA = {prop1: 42};
var objB = objA;
objB.prop1 = 90;
console.log(objA)
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: {prop1: 90}

The output will be {prop1: 90} because we're dealing with objects here. Objects are passed by reference, that is, objA and objB point to the same object in memory.

</p>
</details>

</li>

---
