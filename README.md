
<div align="left">
  <h1>Hoisting</h1>
</div>

1. **What will be the output ?**

```JS
console.log(typeof foo);

function foo() {
  return "bar";
}
var foo = "bar";

```
<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### Option: `function`

1. console.log(typeof foo);: This line is executed first. At this point, foo is hoisted as a variable, but it has not been assigned a value yet, so its type is undefined.

2. function foo() { return "bar" }: The function declaration is hoisted to the top of its containing scope (in this case, the entire script or function). This means that the foo variable is now a function.

3. var foo = "bar";: This line is executed last. It reassigns the variable foo with the string value "bar," overwriting the previous function declaration.

So, when you call console.log(typeof foo); after the entire script has been executed, the output will be "function" because, at the time of the console.log statement, foo refers to the function declaration that was hoisted.

</p>
</details>

</li>

---
