# Detect Internet Explorer

---
To accomplish a task you need to detect Internet Explorer browsers without using browser sniffing.

The function to detect the browser can be executed in...

* Opera
* Chrome
* Firefox
* Phantom
* Internet Explorer

... and it should return *true* only if the browser is Internet Explorer.

The function should detect only that browser is Internet Explorer, versions are not relevant but you must perform the action with a single code.

Write the code:

```js
function isIE() {

}
```

```js
function isIE() {
    window.external = '';
    return typeof window.external === 'object';
}
```

```js
assert(trim(isIE.toString()).replace('isIE', '') == trim(isIE_good.toString()).replace('isIE_good', ''));
```

```js
function isIE_good() {
    window.external = '';
    return typeof window.external === 'object';
}
function trim(str) {
    return str.replace(/^\s+|\r\n*|\n*|\s+$/g, '');
}
```
---