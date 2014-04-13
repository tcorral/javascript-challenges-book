# Timers

We have the following code to show a log in the console after 1000 ms / 1 sec.
```
var check = false;
var timeStart = new Date().getTime();

setTimeout( function () {
    check = true;
}, 1000 );

while( !check ){
}

console.log( 'Loop has finished', 'Elapsed time:' + (new Date().getTime() - timeStart) );
```
But for some weird reason it doesn't works as expected and blocks the browser, could you help us?

---
Why this is happening?
```js

```
```js
As you should know Javascript is single threaded then when we launch this code the while statement doesn't free the thread because the continuos execution blocking any other statement to be executed and blocks the change of 'check' to true blocking the environment where it's executed.
```
```js
__match_answer_and_solution__
```
---

---
Fix the code:
```js
var check = false;
var timeStart = new Date().getTime();

setTimeout( function () {
    check = true;
}, 1000 );

while( !check ){
}

console.log( 'Loop has finished', 'Elapsed time:' + (new Date().getTime() - timeStart) );
```
```js
var timeStart = new Date().getTime();
var endTime = timeStart + 1000;

while( new Date().getTime() < endTime ){
}

console.log( 'Loop has finished', 'Elapsed time:' + (new Date().getTime() - timeStart) );
```
```js
assert(items[0] === 'Loop has finished');
```
```js
var backConsole = console;
var items = [];
var console = {
    log: function (str) {
        items.push(str);
        backConsole.log(str);
    }
};
```
---