# Exit nested loop

How to exit of a nested loop.

---

Make the modifications to the following code so that  when it's executed it should exit the first time indexInnerLoop has a value of 10 and indexOuterLoop has a value of 0.

```js
var indexOuterLoop, iterationsOuterLoop = 1000, indexInnerLoop, iterationsInnerLoop = 100;

for (indexOuterLoop = 0; indexOuterLoop < 1000; indexOuterLoop++)
{
     for (indexInnerLoop = 0; indexInnerLoop < iterationsInnerLoop; indexInnerLoop++)
     {
        if (indexInnerLoop === 10)
        {
            console.log( 'indexInnerLoop is equals to 10' );
            break;
        }
     }
}

console.log( indexOuterLoop );  // Should log 0.
```

```js
var indexOuterLoop, iterationsOuterLoop = 1000, indexInnerLoop, iterationsInnerLoop = 100;

outer:
for (indexOuterLoop = 0; indexOuterLoop < 1000; indexOuterLoop++)
{
     inner:
     for (indexInnerLoop = 0; indexInnerLoop < iterationsInnerLoop; indexInnerLoop++)
     {
        if (indexInnerLoop === 10)
        {
            console.log( 'indexInnerLoop is equals to 10' );
            break outer;
        }
     }
}

console.log( indexOuterLoop );  // Should log 0.
```

```js
assert(items[0] === 'indexInnerLoop is equals to 10' && items[1] === 0);
```

```js
var items = [];
var backConsole = console;
var counter
var console = {
    log: function (str) {
        items.push(str);
        counter++;
        if(counter === 2){
            console = backConsole;
        }
    }
};
```

---
