deep-equal2
============

Reason for the existance: https://github.com/substack/node-deep-equal/pull/3

Node's `assert.deepEqual() algorithm` with constructor check

This module is around [5 times faster](https://gist.github.com/2790507)
than wrapping `assert.deepEqual()` in a `try/catch`.


example-normal
==============

``` js
var equal = require('deep-equal2');
console.dir([
    equal(
        { a : [ 2, 3 ], b : [ 4 ] },
        { a : [ 2, 3 ], b : [ 4 ] }
    ),
    equal(
        { x : 5, y : [6] },
        { x : 5, y : 6 }
    )
]);
```
example - with constructor check
================================
``` js
var equal = require('deep-equal2');
console.dir([
    equal(
        { a : 'str', b: 10, c: [10, true], d: {k: [1121, 2323], d: Number} },
        { a : String, b: Number, c: [Number, Boolean] , d: {k: Array, d: 10} }
    )
]);
```

methods
=======

var deepEqual = require('deep-equal2')

deepEqual(a, b)
---------------

Compare objects `a` and `b`, returning whether they are equal according to a
recursive equality algorithm.

install
=======

With [npm](http://npmjs.org) do:

```
npm install deep-equal2
```

test
====

With [npm](http://npmjs.org) do:

```
npm test
```

license
=======

MIT. Derived largely from node's assert module.
