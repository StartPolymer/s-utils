# s-utils

Polymer utility functions and mixins.

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

### throttle()

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

### throttleRaf()

Creates a throttled function that only invokes `callback` at most once per frame using `requestAnimationFrame`.
Ideal using for mouse, resize, scroll events.

Run `_onOptimizedResize` once every 10 frames.

```js
window.addEventListener('resize', S.Utils.throttleRaf(this._onOptimizedResize, 10));
```

> Inspired by [raf-throttle](https://github.com/wuct/raf-throttle)
