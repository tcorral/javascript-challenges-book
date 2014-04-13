# Even or Odd

We have the following code that should return only the odd numbers in reverse order that are in values...

```js
(function() {
    var values = [3, 8, '15', Number.MAX_VALUE, Infinity, -23],
        oddValues = [],
        index,
        lenValues = values.length,
        isOdd = function ( value ) {
            return (value % 2) !== 0;
        };

    while(lenValues--) {
        if ( isOdd( values[lenValues] ) ) {
            oddValues.push( values[lenValues] );
        }
    }
    console.log( oddValues );
}());
```

...but when this code is executed we get ``[-23, Infinity, "15", 3]``.

Ah! Maybe Number.MAX_VALUE is a even number then why not substract 1 and check it again?

```js
(function() {
    var values = [3, 8, '15', (Number.MAX_VALUE -1), Infinity, -23],
        oddValues = [],
        index,
        lenValues = values.length,
        isOdd = function ( value ) {
            return (value % 2) !== 0;
        };

    while(lenValues--) {
        if ( isOdd( values[lenValues] ) ) {
            oddValues.push( values[lenValues] );
        }
    }
    console.log( oddValues );
}());
```
...but when this code is executed we get ``[-23, Infinity, "15", 3]`` again.

---
Please explain why Number.MAX_VALUE has not been added:

```js

```

```js
Number.MAX_VALUE can't be handled properly by Javascript to work with it in operations because the overflow issue.
```

```js
__match_answer_and_solution__
```
---

---
Write the code to avoid Infinity to be added.

```js
(function() {
    var values = [3, 8, '15', Number.MAX_VALUE, Infinity, -23],
        oddValues = [],
        index,
        lenValues = values.length,
        isOdd = function ( value ) {
            return (value % 2) !== 0;
        };

    while(lenValues--) {
        if ( isOdd( values[lenValues] ) ) {
            oddValues.push( values[lenValues] );
        }
    }
    console.log( oddValues );
}());
```

```js
(function() {
    var values = [3, 8, '15', Number.MAX_VALUE, Infinity, -23],
        oddValues = [],
        index,
        lenValues = values.length,
        isOdd = function ( value ) {
            return (value % 2);
        };

    while(lenValues--) {
        if ( isOdd( values[lenValues] ) ) {
            oddValues.push( values[lenValues] );
        }
    }
    console.log( oddValues );
}());
```

```js
assert(items[0] === -23 && items[1] === "15" && items[2] === 3);
```

```js
var items;
var backConsole = console;
var counter = 0;
var console = {
    log: function (str) {
        items = str;
        counter++;
        backConsole.log(str);
        if(counter === 1) {
            console = backConsole;
        }
    }
};
```
---