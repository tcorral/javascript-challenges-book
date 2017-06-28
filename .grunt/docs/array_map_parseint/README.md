# Using Array.prototype.map and parseInt

## Snippet 1
```
var result = ['1','10','100','1000','10000', '100000', '1000000'].map(parseInt)
```

## Expected
```
var result = [1, 10, 100, 1000, 10000, 100000, 100000];
```
---
What's the result of executing Snippet 1 code?
```js
var result = ;
```
```js
var result = [1, NaN, 4, 27, 256, 3125, 46656];
```
```js
assert(result[0] === 1 && isNaN(result[1]) && result[2] === 4 && result[3] === 27 && result[4] === 256 &&& result[5] === 3125 && result[6] === 46656);
```
---

---
Why?
```js

```
```js
Array.prototype.map has three arguments that pass to the callback we set as argument:
* value
* index
* arr
When we check the specifications of parseInt we can see that parseInt could receive two arguments.
The former is the string to be parsed and the latter is the ratio to convert the value.

When we run Snippet 1 code, the following is actually executed:
 * parseInt(1, 0)           => 1
 * parseInt(10, 1)          => NaN
 * parseInt(100, 2)         => 4
 * parseInt(1000, 3)        => 27
 * parseInt(10000, 4)       => 256
 * parseInt(100000, 5)      => 3125
 * parseInt(1000000, 6)     => 46656
```
```js
__match_answer_and_solution__
```
---

---
We need to get the same array as in Expected 1, please fix the code:
```js
var result = ['1','10','100','1000','10000', '100000', '1000000'].map(parseInt)
```
```js
var result = ['1','10','100','1000','10000', '100000', '1000000'].map(Number)
```
```js
assert(result[0] === 1 && result[1] === 10 && result[2] === 100 && result[3] === 1000 && result[4] === 10000 && result[5] === 100000 && result[6] === 1000000 );
```
---
