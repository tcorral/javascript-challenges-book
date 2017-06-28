# Undefined values in Array
See the next snippet of code:
```
var arr = [];
arr.length = 10;
// The next statement shows [] in the console.
console.log(arr);
// The next statement shows [undefined × 10] in the console.
arr;
// The next statement shows undefined in the console.
console.log(JSON.stringify(arr[0]));
```

## Snippet 1

```
console.log(JSON.stringify(arr));
```

---

What will be shown in the console if we execute Snippet 1?

```js

```

```js
[null,null,null,null,null,null,null,null,null,null]
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
When JSON.stringify is called it call toJSON method of object but undefined is not an object itself then it calls the object that is in the backend of undefined, returning 'null' as value, this is the reason of undefined == null is true.
```

```js
__match_answer_and_solution__
```

---

## Snippet 2

```
console.log(arr.toString());
```

---

What will be shown in the console if we execute Snippet 2?

```js

```

```js
",,,,,,,,,"
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
When the toString of arr is called it returns an empty string for each undefined value in the array.
```

```js
__match_answer_and_solution__
```

---