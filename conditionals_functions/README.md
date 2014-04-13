# Conditionals and functions

Read and execute the following snippets of code:

## Snippet 1:
```
var test;

if ( true ) {
    test = function () {
        console.log( "That's true" );
    };
} else {
    test = function () {
        console.log( "That's false" );
    };
}

test(); // Shows "That's true"
```

## Snippet 2:
```
if ( true ) {
    function test() {
        console.log( "That's true" );
    }
} else {
    function test() {
        console.log( "That's false" );
    }
}

test(); // Shows "That's false"
```

## Snippet 3:
```
var test;

if ( true ) {
    test = function () {
        console.log( "That's true" );
    };
} else {
    function test() {
        console.log( "That's false" );
    }
}

test(); // Shows "That's true"
```

---
What's the reason of this behaviour?

```js

```

```js
The execution of Snippet 1 shows "That's true" because function expressions are evaluated in execution time.
The execution of Snippet 2 shows "That's false" because function declarations are evaluated in evaluation time, and the second one overwrittes the first one.
The execution of Snippet 3 shows "That's true" because when the code has been evaluated it has changed to the function that could return "That's false" but when the code has been executed it has been overwritten again with the function expression.
```

```js
__match_answer_and_solution__
```
---
