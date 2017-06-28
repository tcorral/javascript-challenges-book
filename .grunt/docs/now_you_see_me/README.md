# Now you see me ...

## Snippet 1
```
var f = function g() {
        return 23;
    };
typeof g();
```

---
What is the result of executing Snippet 1 code?

```js

```

```js
ReferenceError: g is not defined
```

```js
__match_answer_and_solution__
```
---

---
Why?

```js

```

```js
When a function expression has a named function it can only be accessed using this name from inside the function itself, but from outside of the function it doesn't exist this is the reason that 'g' trows a Reference Error when is called.
```

```js
__match_answer_and_solution__
```
---