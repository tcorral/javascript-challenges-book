# Nested Scopes

Take a look at the following code but don't execute it in the console.

```
{var a = 1;{var b = 2;{( function() {var c = a + b;} )()}}c;}
```

---
What's the result of executing the previous code?

```js

```

```js
ReferenceError: c is not defined
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
The cause of the error is because Javascript only has not block scopes as in other languages, then 'c' only exist inside the function block and it throws an error when we are trying to call it from the current scope.
```

```js
__match_answer_and_solution__
```
---