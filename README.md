flow-max
========

Transform stream which returns the maximum value from a stream of numeric data.


## Installation

``` bash
$ npm install flow-max
```


## Examples

``` javascript
var eventStream = require( 'eventStream' ),
	mStream = require( 'flow-max' );

// Create some data...
var data = new Array( 1000 );
for ( var i = 0; i < data.length; i++ ) {
	data[ i ] = Math.random();
}

// Create a readable stream:
var readStream = eventStream.readArray( data );

// Create a new max stream:
var stream = mStream().stream();

// Create a pipeline:
readStream.pipe( stream )
	.pipe( eventStream.map( function( d, clbk ) {
		clbk( null, d.toString() );
	}))
	.pipe( process.stdout );
```

## Tests

Unit tests use the [Mocha](http://visionmedia.github.io/mocha) test framework with [Chai](http://chaijs.com) assertions.

Assuming you have installed Mocha, execute the following command in the top-level application directory to run the tests:

``` bash
$ mocha
```

All new feature development should have corresponding unit tests to validate correct functionality.


## License

[MIT license](http://opensource.org/licenses/MIT). 


---
## Copyright

Copyright &copy; 2014. Athan Reines.

