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

To load the minified layer you need to wrap your main `require` call with another `require`, requiring `"ecma402-build/layer"`. Then you should continue to
refer to modules with `"ecma402/foo"`.

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

## Licensing

This project is distributed by the Dojo Foundation and licensed under the ["New" BSD License](./LICENSE).
All contributions require a [Dojo Foundation CLA](http://dojofoundation.org/about/claForm).
