# Closures and Objects

As you know Javascript has two different ways to treat the data it receives as arguments of a function:

* Primitives are passed by copy.
* Objects are passed by reference.

See the following code:

```
var oPerson = { name: 'john' };

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

Explain why this is happening:

```js

```

```js
This is happening because when the closure has been executed it has saved the reference in memory for oPerson as oTeacher and even when oPerson has changed the assigned value to a different object it continues being referenced inside the closure. It is important to check this problems because if you make the same with DOM elements and the element is removed from the DOM tree you will get memory leaks issues
```

```js
__match_answer_and_solution__
```

---

---

Fix the code to make the third execution return ``Object { name: "mary", surname: "sullivan" }``

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
