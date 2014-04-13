# Ghost Array

Take a look at this code:

## Snippet 1
```
var arr = [];
arr[999] = 'john';
console.log(arr.length);
```

---
What is the result of execute "Snippet 1" code?

```js

```
```js
1000
```
```js
__match_answer_and_solution__
```
---

## Snippet 2
```
var arr = [];
arr[4294967295] = 'james';
console.log(arr.length);
```

---
What is the result of execute "Snippet 2" code?

```js

```
```js
0
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
Because 4294967295 overflows the max number of elements that could be handled by Javascript in Arrays.
```
```js
__match_answer_and_solution__
```
---

## Snippet 3

```
var arr = [];
arr[4294967295] = 'james';
console.log(arr[4294967295]);
```

---
What is the result of execute "Snippet 3" code?

```js

```
```js
"james"
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
Javascript arrays can work as objects, dictionaries, when you are using as key any value that can not be handled by Array objects.
```
```js
__match_answer_and_solution__
```
---

## Snippet 4

```
var arr = [];
arr[Number.MIN_VALUE] =  'mary';
console.log(arr.length);
```

---
What is the result of execute "Snippet 4" code?

```js

```
```js
0
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
Javascript arrays can work as objects, dictionaries, when you are using as key any value that can not be handled by Array objects.
```
```js
__match_answer_and_solution__
```
---

## Snippet 5

```
var arr = [];
arr[Number.MIN_VALUE] =  'mary';
console.log(arr[Number.MIN_VALUE]);
```

---
What is the result of execute "Snippet 5" code?

```js

```
```js
"mary"
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
Javascript arrays can work as objects, dictionaries, when you are using as key any value that can not be handled by Array objects.
```
```js
__match_answer_and_solution__
```
---