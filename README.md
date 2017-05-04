# eslint-plugin-no-for-of-loops
Prevents `for (...of)` loops usage in your code base.

[![Build Status](https://travis-ci.org/dharFr/eslint-plugin-no-for-of-loops.svg?branch=master)](https://travis-ci.org/dharFr/eslint-plugin-no-for-of-loops)
[![npm](https://img.shields.io/npm/v/eslint-plugin-no-for-of-loops.svg)](https://www.npmjs.com/package/eslint-plugin-no-for-of-loops)


## Installation
``` sh
npm install --save-dev eslint-plugin-no-for-of-loops
```

## Usage
In your `.eslintrc`:

``` javascript
{
  "plugins": [
    "no-for-of-loops"
  ],
  "rules": {
    "no-for-of-loops/no-for-of-loops": 2
  }
}
```

## Rule
Disallow use of `for (..of)` loops.

## Why
Using  `for (...of)` loops requires a `Symbol` and iterator polyfill to work on older browsers (see [babel/babel#1534](https://github.com/babel/babel/issues/1534))
Depending on your browsers target (for example, Android 4.4 in-app Webview is capped to Chrome 33), you might not want to include those polyfills to save some kilobytes.

See [for..of](http://kangax.github.io/compat-table/es6/#test-for..of_loops) and [Symbol](http://kangax.github.io/compat-table/es6/#test-Symbol)  compatibily tables

## Disabling the rule
What to disable the rule anyway? Your call :

```javascript
// eslint-disable-next-line no-for-of-loops/no-for-of-loops
for (let i of iterable) {
  // ...
}
```

## Credits

This project was initialy forked form [eslint-plugin-no-loops](https://github.com/buildo/eslint-plugin-no-loops). Kudos!