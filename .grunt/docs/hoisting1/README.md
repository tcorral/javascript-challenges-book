# Hoisting and Conditionals Statements

I'm Ernie and my friend is Bert and we wrote this code to tell other people which type of birds we like.

```
var bird = 'Pidgeons';
( function () {
    if ( typeof bird === 'undefined' ){
        var bird = 'Rubber Duck';
        console.log('Ernie loves his ' + bird );
    } else {
        console.log('Bert loves his ' + bird );
    }
}() );
```

There should be a problem with our code because for some reason I only see 'Ernie loves his Rubber Duck' when I expected to see 'Bert loves his Pidgeons', could you help me?

---

Why this is happening?

```js

```

```js
This is happening because the hoisting problem. Remember that in Javascript there are no block variables.
```

```js
__match_answer_and_solution__
```

---

---

Please help me and fix this code to get 'Bert loves his Pidgeons'.

```js
var bird = 'Pidgeons';
( function () {
    if ( typeof bird === 'undefined' ){
        var bird = 'Rubber Duck';
        console.log('Ernie loves his ' + bird );
    } else {
        console.log('Bert loves his ' + bird );
    }
}() );
```

```js
var bird = 'Pidgeons';
( function () {
    if ( typeof bird === 'undefined' ){
        bird = 'Rubber Duck';
        console.log('Ernie loves his ' + bird );
    } else {
        console.log('Bert loves his ' + bird );
    }
}() );
```

```js
assert(inputs[0] === 'Bert loves his Pidgeons');
```

```js
var inputs = [];
var backConsole = console;
var console = {
    log: function (str) {
        inputs.push(str);
        backConsole.log(str);
        console = backConsole;
    }
};
```
---
