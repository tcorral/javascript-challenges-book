# Delete

Execute this code:
```
var name = 'John',
    obj = {
        name: 'James'
    },
    Animal,
    mammal;

Animal = function(){};
Animal.prototype.name = 'animal';

mammal = new Animal();

delete name;

console.log('#1: ' + name);

delete obj.name;

console.log('#2: ' + obj.name);

delete obj.toString;

console.log('#3: ' + obj.toString);

delete mammal.name;

console.log('#4: ' + mammal.name);
```

The execution of this code logs:
```
#1: John
```
```
#2: undefined
```
```
#3: function toString() { [native code] }
```
```
#4: animal
```

---
Why #1: John is logged?

```js

```
```js

```
```js
assert(true);
```
---

---
Why #2: undefined is logged?

```js

```
```js

```
```js
assert(true);
```
---

---
Why #3: function toString() { [native code] } is logged?

```js

```
```js

```
```js
assert(true);
```
---

---
Why #4: animal is logged?

```js

```
```js

```
```js
assert(true);
```
---