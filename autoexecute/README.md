# Self Invoking Functions

I want to set variable 'a' to 3 using a Self Invoking Function, can you help me?

```
var testValue;
function test() { testValue = 3; }();
```

---

What is the result of executing the previous code?

```js

```

```js
SyntaxError: Unexpected token )
```

```js
assert(true);
```

---

---

What is the value of variable 'testValue'?

```js

```

```js
undefined
```

```js
assert(true);
```

---


---

Why?

```js

```

```js
The value of testValue is undefined because the function has not been autoexecuted.
```

```js
assert(true);
```

---

---

Write the code to execute this function adding only one more character to the sentence.

```js
var testValue;
function test() { testValue = 3; }();
```

```js
var testValue;
!function test() { testValue = 3; }();
```

```js
assert(testValue == 3);
```

---