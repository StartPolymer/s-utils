# StartPolymer Utilities

[![PRs welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://help.github.com/articles/about-pull-requests/)

Polymer utility functions, mixins, modules and styles.

## Install

`bower i StartPolymer/s-utils -S`

## Import

### Polymer 1.0

```html
<link rel="import" href="../bower_components/s-utils/utils-es5/throttle.html">
```

### Polymer 2.0

```html
<link rel="import" href="../bower_components/s-utils/utils/throttle.html">
```

## Functions

### throttle() from throttle.html

Creates a throttled function that only invokes `callback` at most once per every `wait` milliseconds.

> See [David Corbacho's article](https://css-tricks.com/debouncing-throttling-explained-examples/)
for details over the differences between throttle and debounce techniques.

```js
// Limiting the api call thrice a second.
var resultFunction = S.Utils.throttle(_apiCall, 1000, 3);

// Calling the closure function in every 100 milliseconds.
setInterval(function () {
  resultFunction();
}, 100);
```

> Inspired by https://stackoverflow.com/a/42975776/1614237

### throttlePerFrame() from throttle.html

Creates a throttled function that only invokes `callback` at most once per frame using `requestAnimationFrame`.
Ideal using for mouse, resize, scroll events.

```js
window.addEventListener('resize', S.Utils.throttlePerFrame(this._onOptimizedResize));
```

> Inspired by [raf-throttle](https://github.com/wuct/raf-throttle)

### timestamp() from date.html

Returns a timestamp measured in milliseconds, accurate to five thousandths of a millisecond (5 microseconds).

```js
S.Utils.timestamp()
```

## Modules

### Browser from browser.html

Module that provides a number of properties for detection of browser types and features.

```js
S.Utils.Browser.hasTouchScreen
S.Utils.Browser.isIE
S.Utils.Browser.onAndroid
```
