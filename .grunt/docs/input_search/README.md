# Input Search

Reviewing the code of your colleague you have found this snipped of code:

```
$( document ).ready( function() {
  $( '#inputSearch' ).keypress( function() {
      $.ajax( {
        url: 'http://www.domain.com/search',
        data: this.value,
        success: function ( data )
        {
            var results = data.results;
            $( '#list' ).empty();
            $.each( data, function ( item ) {
                $( '#list' ).append( '<li>' + item + '</li>' );
            } );

        },
        error: function ( xhr, status, error ) {
            console.log( 'Something goes wrong!', status, error.message );
        }
      } );
  } );
} );
```
In this code there is a performance issue that should be fixed, could you help us?

---
Fix the performance issue:
```js
$( document ).ready( function() {
  $( '#inputSearch' ).keypress( function() {
      $.ajax( {
        url: 'http://www.domain.com/search',
        data: this.value,
        success: function ( data )
        {
            var results = data.results;
            $( '#list' ).empty();
            $.each( data, function ( item ) {
                $( '#list' ).append( '<li>' + item + '</li>' );
            } );

        },
        error: function ( xhr, status, error ) {
            console.log( 'Something goes wrong!', status, error.message );
        }
      } );
  } );
} );
```
```js
function delayTimer(delay){
  var timer;
    return function(fn){
      timer = clearTimeout(timer);
      if(fn)
        timer = setTimeout(function() {
           fn();
        },delay);

      return timer;
  };
}
var delayer = delayTimer(500);

$( document ).ready( function() {
  $( '#inputSearch' ).keyup( function() {
      delayer(function() {
        var $list = $( '#list' );
        $.ajax( {
          url: 'http://www.domain.com/search',
          data: this.value,
          success: function ( data )
          {
              var results = data.results;
              $list.empty();
              $.each( data, function ( item ) {
                  $list.append( '<li>' + item + '</li>' );
              } );

          },
          error: function ( xhr, status, error ) {
              console.log( 'Something goes wrong!', status, error.message );
          }
        } );
      } );
  } );
} );
```

```js
assert(counter === 1);
```
```js
var document = '';
var counter = 0;
var setTimeout = function (cb) {
    cb();
};
var $ = function ( element ) {
    var jQuery = {
        ready: function ( callback ) {
            callback();
            return jQuery;
        },
        keypress: function ( callback ) {
            callback();
            return jQuery;
        },
        keyup: function ( callback ) {
            counter++;
            callback();
            return jQuery;
        }
    };
    return jQuery;
};
$.ajax = function () {};
```
---