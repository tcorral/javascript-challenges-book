# Running man
We are playing in 'The Running Man' show and we have 9007199254740992 unit times to survive but all the gamers in previous game have been killed even when they have been playing bravely, could you help us?

*The following code could make crash your browser!! Be careful!!*
```
var endTheGame = 9007199254740992,
    startTheGame = endTheGame - 100,
    count = 0,
    index,
    result;

for ( index = startTheGame; index <= endTheGame; index++ ) {
    count++;
}

result = count;
```

---
Fix the code to allow us to survive:
```js
var endTheGame = 9007199254740992,
    startTheGame = endTheGame - 100,
    count = 0,
    index,
    result;

for ( index = startTheGame; index <= endTheGame; index++ ) {
    count++;
}

result = count;
```

```js
var endTheGame = 9007199254740991,
    startTheGame = endTheGame - 100,
    count = 0,
    result,
    index;

for ( index = startTheGame; index <= endTheGame; index++ ) {
    count++;
}

result = count;
```

```js
assert(result === 101 && endTheGame == 9007199254740991);
```

---

---
Why?
```js

```
```js
9007199254740992 is the maximum number that Javascript can handle then it is unable to manage due to the overflow issue, then the most easy way to do it is decrement the number in one to allow Javascript to work with it.
```
```js
__match_answer_and_solution__
```
---