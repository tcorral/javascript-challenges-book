# Closures and Objects

As you know Javascript has two different ways to treat the data it receives as arguments of a function:

* Primitives are passed by copy.
* Objects are passed by reference.

See the following code:

```
var oPerson = { name: 'john'};

(function(oTeacher) {
   window.getTeacher= function() {
      console.log(oTeacher);
   };
}(oPerson));

window.getTeacher();

oPerson.surname = 'doe';

window.getTeacher();

oPerson = { name: 'mary', surname: 'sullivan' };

window.getTeacher();
```

The first execution of window.getTeacher returns:
```
Object { name: "john" }
```
The second execution of window.getTeacher returns:
```
Object { name: "john", surname: "doe" }
```
The third execution of window.getTeacher returns:
```
Object { name: "john", surname: "doe" }
```

---

Explain what this is happening:

```js

```

```js

```

```js
assert(true);
```

---

---

Fix the code to :

```js
var oPerson = { name: 'john'};

(function(oTeacher) {
   window.getTeacher= function() {
      console.log(oTeacher);
   };
}(oPerson));

window.getTeacher();

oPerson.surname = 'doe';

window.getTeacher();

oPerson = { name: 'mary', surname: 'sullivan' };

window.getTeacher();
```

```js
var oPerson = { name: 'john'};

window.getTeacher= function() {
  console.log(oPerson);
};

window.getTeacher();

oPerson.surname = 'doe';

window.getTeacher();

oPerson = { name: 'mary', surname: 'sullivan' };

window.getTeacher();
```

```js
assert(items.length == 3 && items[2].name == 'mary' && items[2].surname == 'sullivan');
```

```js
var items = [];
var backConsole = console;
var console = {
    log: function (str) {
        items.push(str);
        if(items.length === 3)
        {
            console = backConsole;
        }else{
            backConsole.log(str);
        }
    }
};
```
---