#Floats Operations Imprecision

Welcome to Bank Ruptcy, and we want to hire you to fix our algorithm to exchange the stock options, because we have some weird behaviour.

This is our algorithm to exchange the stock options:

```
var stockOptionsCost = 10.70, paid = 20.80;

function calculateChange() {

    return paid - stockOptionsCost;
}

function calculateAmountOfStockOptions () {
    return paid / stockOptionsCost;
}

var amountStockOptions = calculateAmountOfStockOptions();
var yourChange = calculateChange();
```

---

What returns calculateAmountOfStockOptions ?

```js

```

```js
1.94392523364486
```

```js
__match_answer_and_solution__
```

---

---

What is the value of calculateChange ? Input the number value.

```js

```

```js
10.100000000000001
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
Javascript has several problems operating with floating point, this is one of the causes that it should not be to operate with floats.
```

```js
__match_answer_and_solution__
```

---

---

Please fix this code to return the correct change.

```js
var stockOptionsCost = 10.70, paid = 20.80;

function calculateChange() {

    return paid - stockOptionsCost;
}

function calculateAmountOfStockOptions () {
    return paid / stockOptionsCost;
}

var amountStockOptions = calculateAmountOfStockOptions();
var yourChange = calculateChange();
```

```js
var stockOptionsCost = 10.70, paid = 20.80;

function calculateChange() {

    return (paid - stockOptionsCost).toFixed(2);
}

function calculateAmountOfStockOptions () {
    return paid / stockOptionsCost;
}

var amountStockOptions = calculateAmountOfStockOptions();
var yourChange = calculateChange();
```

```js
assert(yourChange == 10.10);
```

---