# JSON
This challenge will help you to understand how JSON object works.
Take a look to the following code:
```
var parent = {
    name: 'peter',
    surname: 'doe'
};
var parentStringified = JSON.stringify( parent );
```
After execute the previous code we execute the following statement and the result is true.
```
console.log( parentStringified === '{ "name": "peter", "surname": "doe" }');
```

---

Write the code needed to get the expected result without changing the values of ``obj.name`` and ``obj.surname`` values:

```js
var obj = {
    name: 'john',
    surname: 'doe'
};

// Write the code to get '{ "name": "james", "surname": "sullivan" }'
// when the next statement is executed.

var result = JSON.stringify( obj );
```

```js
var obj = {
    name: 'john',
    surname: 'doe'
};
obj.toJSON = function () {
    return { name: 'james', surname: 'sullivan' };
};
var result = JSON.stringify( obj );
```

```js
assert(JSON.parse(result).name == 'james' && JSON.parse(result).surname == 'sullivan');
```
---
