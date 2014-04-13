# #2 Fooling around boolean

All the following statements are true

```
!!{} == true;
```
```
[] == false;
```

We have the following code:

```
var hasTruthyStuff = function (aSymbols) {
    var nResult = 0,
        i = 0,
        nLen = aSymbols.length;

    for (; i < nLen; i++) {
        nResult |= aSymbols[i];
    }
    return !!nResult;
};
```
But when we execute the following statement it returns false when we expected to return true because {} should return true.

```
hasTruthyStuff([{},[], 0])
```

---
Why does calling the previous statement returns false?

```js

```
```js
You have to be careful when using |= because when it's used to perform a test besides an object it will not modify the original value, then it remains to be zero.
```
```js
__match_answer_and_solution__
```
---