# Variable Scope

We have the following code:
```
var name = 'John',
    obj = {
        name: 'Mary',
        whoIam: function() {
            var name = 'James';

            console.log( this.name );

            setTimeout( function () {
                console.log( this.name );
            }, 100 );
        }
    };

obj.whoIam();
```
---
What does it prints?
```js

```
```js
"Mary"
undefined
"John"
```
```js
__match_answer_and_solution__
```
---

---
Why?
```js

```
```js
It logs Mary because the context of execution is obj.
It logs John because setTimeout is executed in the global context.
```
```js
__match_answer_and_solution__
```
---