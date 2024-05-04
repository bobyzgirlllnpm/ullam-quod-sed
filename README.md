# @bobyzgirlllnpm/ullam-quod-sed <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES spec-compliant `Object.hasOwn` shim. Invoke its "shim" method to shim `Object.hasOwn` if it is unavailable or noncompliant.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES3-supported environment and complies with the [spec](https://tc39.es/proposal-accessible-object-hasownproperty/).

Most common usage:
```js
var assert = require('assert');
var hasOwn = require('@bobyzgirlllnpm/ullam-quod-sed');

var obj = { a: 1, b: 2 };

assert(hasOwn(obj, 'a'));
assert(hasOwn(obj, 'b'));
assert('toString' in obj && !hasOwn(obj, 'toString'));

if (!Object.hasOwn) {
	hasOwn.shim();
}

assert.deepEqual(Object.hasOwn(obj, 'a'), hasOwn(obj, 'a'));
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.com/package/@bobyzgirlllnpm/ullam-quod-sed
[npm-version-svg]: https://versionbadg.es/bobyzgirlllnpm/ullam-quod-sed.svg
[deps-svg]: https://david-dm.org/bobyzgirlllnpm/ullam-quod-sed.svg
[deps-url]: https://david-dm.org/bobyzgirlllnpm/ullam-quod-sed
[dev-deps-svg]: https://david-dm.org/bobyzgirlllnpm/ullam-quod-sed/dev-status.svg
[dev-deps-url]: https://david-dm.org/bobyzgirlllnpm/ullam-quod-sed#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@bobyzgirlllnpm/ullam-quod-sed.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@bobyzgirlllnpm/ullam-quod-sed.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@bobyzgirlllnpm/ullam-quod-sed.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@bobyzgirlllnpm/ullam-quod-sed
[codecov-image]: https://codecov.io/gh/bobyzgirlllnpm/ullam-quod-sed/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/bobyzgirlllnpm/ullam-quod-sed/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/bobyzgirlllnpm/ullam-quod-sed
[actions-url]: https://github.com/bobyzgirlllnpm/ullam-quod-sed/actions
