# Encapsulate collection

We have the following code:
```
function Order() {
         this.orderLines = [];
         this.orderTotal = 0;
}
Order.prototype.getOrderLines = function() {
         return this.orderLines;
};
Order.prototype.addOrderLine = function(orderLine) {
         this.orderTotal += orderLine.total;
         this.orderLines.push(orderLine);
};
Order.prototype.removeOrderLine = function(orderLineItem) {
         var orderTotal, orderLine;
         orderLine = this.orderLines.map(function(order) {
                  return order === orderLineItem;
         })[0];

         if(typeof orderLine === 'undefined' || orderLine === null) {
                  return;
         }
         this.orderTotal -= orderLine.total;
         this.orderLines.splice(this.orderTotal, 1);
};
```
```
var order = new Order();
order.addOrderLine( { total: 10 } );
console.log(order.getOrderLines());  // [ { total: 10 } ]
console.log(order.orderTotal);   // 10
```
The problem with this code is that anyone could get access to orderLines and add or modify values without increasing or decreasing orderTotal.
```
order.orderLines[0] = { total: 20 };
console.log(order.getOrderLines()); // [ { total: 20 } ]
console.log(order.orderTotal);  // 10;
```

---
Modify the code to encapsulate the collection to avoid this issue.

```js
function Order() {
         this.orderLines = [];
         this.orderTotal = 0;
}
Order.prototype.getOrderLines = function() {
         return this.orderLines;
};
Order.prototype.addOrderLine = function(orderLine) {
         this.orderTotal += orderLine.total;
         this.orderLines.push(orderLine);
};
Order.prototype.removeOrderLine = function(orderLineItem) {
         var orderTotal, orderLine;
         orderLine = this.orderLines.map(function(order) {
                  return order === orderLineItem;
         })[0];

         if(typeof orderLine === 'undefined' || orderLine === null) {
                  return;
         }
         this.orderTotal -= orderLine.total;
         this.orderLines.splice(this.orderTotal, 1);
};
```

```js
function Order() {
         var orderLines, orderTotal;
         orderLines = [];
         orderTotal = 0;
         this.getOrderLines = function () {
            return orderLines;
         };
         this.getOrderTotal = function () {
            return orderTotal;
         };
         this.setOrderTotal = function (total) {
            orderTotal += total;
         };
}
Order.prototype.addOrderLine = function (orderLine) {
    var orderLines;
    orderLines = this.getOrderLines();
    this.setOrderTotal(orderLine.total);
    orderLines.push(orderLine);
};
Order.prototype.removeOrderLine = function(orderLineItem) {
         var orderTotal, orderLine, orderLines;
         orderLines = this.getOrderLines();
         orderLine = this.orderLines.map(function(order) {
                  return order === orderLineItem;
         })[0];

         if(typeof orderLine === 'undefined' || orderLine === null) {
                  return;
         }

         this.setOrderTotal( (-1 * orderLine.total) );
         orderLines.splice( this.getOrderTotal(), 1);
};
```

```js
var order = new Order();
assert(typeof order.orderLines === 'undefined');
```
