# Terminator
Here you have the prototype code of the next Terminator fan page:

```
<!DOCTYPE html>
<html>
    <head>
        <title>Terminator Fan Page</title>
    </head>
    <body>
        <form action="/">
            <input type="text" name="name"/>
            <input type="submit" value="Send"/>
        </form>
    </body>
</html>
```
One of my colleagues has written the next code that will log the name we send using the form in the previous page.
```
<script>
    function sayonara( name ) {
        console.log( 'Sayonara ' + name + '!' );
    }

    sayonara( greetings );
</script>
```
But then someone sends the next message as a name and the behaviour of the page changes...
```
'</script><script>console.log("I will come back!")</script><script>'
```

Here is an example of executing the page with the bug:
```
<!DOCTYPE html>
<html>
	<head></head>
	<body>
		<script>
		    var result = '';
			function sayonara( name ) {
				result = 'Sayonara ' + name + '!';
			}

			sayonara( '</script><script>console.log("I will come back!")</script><script>' );
		</script>
	</body>
</html>
```

---
Fix the code:
```js
var result = '';
function sayonara( name ) {
    result = 'Sayonara ' + name + '!';
}

sayonara( '</script><script>console.log("I will come back!")</script><script>' );
```
```js
var result = '';
function sayonara( name ) {
    result = 'Sayonara ' + name + '!';
}

sayonara( '<\/script><script>console.log("I will come back!")<\/script><script>' );
```
```js
assert(result === 'Sayonara <\/script><script>console.log("I will come back!")<\/script><script>!');
```

---
