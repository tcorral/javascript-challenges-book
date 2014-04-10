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

```

```js
assert(true);
```
---
