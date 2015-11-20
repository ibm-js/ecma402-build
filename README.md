# ecma402-build

Build version of [ibm-js/ecma402](https://github.com/ibm-js/ecma402).

## Status

No official release yet.

## Installation

_Bower_ release installation:

    $ bower install ecma402-build

_Manual_ master installation:

    $ git clone git://github.com/ibm-js/ecma402-build.git

Then install dependencies with bower (or manually from github if you prefer to):

	$ cd ecma402-build
	$ bower install


## How to use

### `baseUrl` is the directory containing `ecma402-build`.
This is the most common use-case so the needed configuration is built in the layer.
To load the minified layer you just need to wrap your main `require` call with another `require`, requiring `"ecma402-build/layer"`.
Then you should continue to refer to modules with `"ecma402/foo"`.

For example, this code:
```js
require(["app/main", "ecma402/foo"], function() {
	...
});
```
Becomes:
```js
require(["ecma402-build/layer"], function() {
	require(["app/main", "ecma402/foo"], function() {
		...
	});
});
```

### Other `baseUrl`

If `baseUrl` is not the directory containing `ecma402-build`, custom configuration is needed.

```js
require.config({
	paths: {
		"ecma402": "path/to/ecma402-build"
	}
});
```


## Bug reporting

Issues should be filled against the source version of this project at [ibm-js/ecma402](https://github.com/ibm-js/ecma402)


## Licensing

This project is distributed by the Dojo Foundation and licensed under the ["New" BSD License](./LICENSE).
All contributions require a [Dojo Foundation CLA](http://dojofoundation.org/about/claForm).
