# #1 Fooling around boolean

Look at the following "implementation" of a xor method on the prototype of the Boolean type.

```
Boolean.prototype.xor = function ( value ) { return !!this !== !!value; };
```

When we execute the following statement we get an unexpected result.

```
false.xor(false);   // => true
```

---
Why does xor resolves in an unexpected manner?

```js

```
```js
Because this is not false, this inside the function is the complete object and it evaluates to true when it's converted to true the same way that !!{} is true.
```
```js
__match_answer_and_solution__
```

---

---
Write the code to fix the implementation of xor method:
```js
Boolean.prototype.xor = function ( value ) { return !!this !== !!value; };
```
```js
Boolean.prototype.xor = function ( value ) { return !!this.valueOf() !== !!value; };
```
```js
assert(false.xor(false) === false);
```
---