# Invaluable

We have the following code:

```
var strMethod = 'valueOf',
    strProperty = 'length',
    result;
```

## Snippet 1
When we execute the Snippet 1, result has a value of 1.
```
result = [44 + 22][strMethod]()[strProperty];
```

---
Why?
```js

```

```js
Because the precedence of operators, the execution workflow is:
44+22 -> returns 66
66 + [ ]  -> returns [66]
[66].valueOf() -> returns [66]
[66].length -> returns 1
```

```js
__match_answer_and_solution__
```
---

## Snippet 2
When we execute the Snippet 2, result has a value of 0.
```
value = [44 + 22][strMethod][strProperty];
```

---
Why?
```js

```

```js
Because the precedence of operators and how native methods behaviours, the execution workflow is:
44+22 -> returns 66
66 + [ ]  -> returns [66]
[66].valueOf -> returns function valueOf() { [native code] }
(function valueOf() { [native code] }).length -> returns 0
```

```js
__match_answer_and_solution__
```
---