# Scope;
## Snippet 1
```
(function test() { test = 123; console.log( test );}())
```
---
What it's logged when Snippet 1 is executed?

```js

```
```js
function test() { test = 123; console.log( test );}()
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
When the code tries to modify test value inside the function it doesn't works because the precedence of the declaration of the function that test reference remains unchanged, then the code that is executed is console.log logs the function body in the console.
```
```js
__match_answer_and_solution__
```
---