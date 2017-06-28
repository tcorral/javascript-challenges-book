# Spartacus
I like the TV series Spartacus so much, that I have written the following code to get the name of the different seasons but something goes wrong...
```
var season = 'first';

var result = ('Spartacus: ' + season === 'first' ? 'Blood and Sand' : 'Gods of the Arena');
```
I expected to get **Spartacus: Blood and Sand** but I got **Gods of the Arena**, could you help me?

---
Fix the code to get 'Spartacus: Blood and Sand':

```js
var season = 'first';
var result = ('Spartacus: ' + season === 'first' ? 'Blood and Sand' : 'Gods of the Arena');
```

```js
var season = 'first';
var result = 'Spartacus: ' + (season === 'first' ? 'Blood and Sand' : 'Gods of the Arena');
```

```js
assert(result === 'Spartacus: Blood and Sand');
```
