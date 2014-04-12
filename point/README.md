# Point
This challenge needs you to implement a Point class so that the following code returns true.
```
new Point( new Point(10, 20) + new Point(30, 50) ).toString() === '{40,70}';
```

---
Implement Point and assume that:

* Must be generic and be able to handle x and y values from 0..999
* The requirements to do it are to implement valueOf and/or toString methods.

```js

```
```js
var Point = function (x, y) {
	if(typeof x === 'string') {
		this.convertStringToCoordinates(x);
	}else{
		this.x = x;
		this.y = y;
	}
};
Point.prototype.convertStringToCoordinates = function ( value ) {
	var arr, index, len, item;
	this.x = 0;
	this.y = 0;
	arr = JSON.parse('[' + value.replace(/{/g,'[').replace(/}/g,']').replace( new RegExp('\\]\\[', 'g'), '],[') + ']');
	len = arr.length;
	for(index = 0; index < len; index++) {
		item = arr[index];
		this.x += item[0];
		this.y += item[1];
	}
};
Point.prototype.toString = function () {
	return '{' + this.x + ',' + this.y + '}';
};
```
```js
assert(new Point( new Point(10, 20) + new Point(30, 50) ).toString() === '{40,70}');
```
---