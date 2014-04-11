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

What returns calculateAmountOfStockOptions ? Input the number value.

```js
var stockOptions = ;
```

```js
var stockOptions = 1.94392523364486;
```

```js
assert(stockOptions == 1.94392523364486);
```

---

---

What is the value of calculateChange ? Input the number value.

```js
var change = ;
```

```js
var change = 10.100000000000001;
```

```js
assert(change == 10.100000000000001);
```

---

---

Why?

```js

```

```js
'Javascript has several problems operating with floating point, this is one of the causes that it should not be to operate with floats.'
```

```js
assert(true);
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