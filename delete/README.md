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
mammal.name = 'mammal';

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

Why **#1: John** is logged?

```js

```
```js
John is logged because name is a global variable and global variables can't be deleted.
```
```js
__match_answer_and_solution__
```

---

---

Why **#2: undefined** is logged?

```js

```
```js
undefined is logged because we have deleted the name property of obj, properties or members of objects can be deleted excluding the properties or members of the global object.
```
```js
__match_answer_and_solution__
```

---

---

Why **#3: function toString() { [native code] }** is logged?

```js

```
```js
function toString() { [native code] } is logged because toString is an inherited method from Object and inherited methods or members can't be deleted.
```
```js
__match_answer_and_solution__
```

---

---

Why **#4: animal** is logged?

```js

```
```js
animal is logged because we have deleted the own mammal.name property but the inherited property is shown.
```
```js
__match_answer_and_solution__
```

---