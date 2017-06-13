[![CircleCI](https://img.shields.io/circleci/project/github/pi0/tapable-promise.svg?style=flat-square)](https://circleci.com/gh/pi0/tapable-promise)
[![Codecov](https://img.shields.io/codecov/c/github/pi0/tapable-promise.svg?style=flat-square)](https://codecov.io/gh/pi0/tapable-promise)
[![npm](https://img.shields.io/npm/v/tapable-promise.svg?style=flat-square)](https://www.npmjs.com/package/tapable-promise)

# tapable-promise
> Extends [tapable](https://www.npmjs.com/package/tapable) with promise support.

## Setup
```bash
yarn add tapable-promise 
# or
npm install --save tapable-promise
```
```js
// Require module
const Tapable = require('tapable-promise')
```

## Usage
For basic usage please see [tapable](https://github.com/webpack/tapable) docs.

### `applyPlugins*`
This functions are wrapped with [pify](https://www.npmjs.com/package/pify) 
and return promise too.

```js
// Using async/await
await this.applyPluginsAsync('init')

// Using Promise
this.applyPluginsAsync('init')
.then(() => {
  // Applied
})
.catch(err => {
  // Some error happened
})
```

### `plugin(names, handler)`
When register plugins `handler` function can also return promise instead of calling `callback` argument.

```js
webpack.plugin('init', async () => {
  // You can use async/await here  
})

// or
webpack.plugin('init', () => new Promise((resolve, reject) => {
  // Call resolve() or rejcet() when finished or chain promise
}))
```

# License

MIT
