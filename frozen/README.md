#Frozen
This challenge will need a bit of knowledge of one of the new features in Javascript 1.8.5, this feature is Object.freeze to get the correct result.

---
Note:
* You can use anything of ECMASCRIPT 5 but not DOM or BOM, just Javascript
* There is more than one answer but only the most simple will win.

Here you have the code to be fixed:
```js
var dog = {
    sound: 'Bark!'
};

Object.freeze(dog);

/* Put your code here */

//This method should return 'Bark!'
var result = dog.talk();
```

```js
var dog = {
    sound: 'Bark!'
};

Object.freeze(dog);

Object.prototype.talk = function () {
    return this.sound;
};

//This method should return 'Bark!'
var result = dog.talk();
```

```js
assert( result === 'Bark!');
```

---
