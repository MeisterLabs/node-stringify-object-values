## stringify-object-values
```
npm i stringify-object-values
```
Stringifies each value of an object. This is useful when paired with [Webpack's DefinePlugin](https://webpack.github.io/docs/list-of-plugins.html#defineplugin).

```js
// Before
{
  hello: 'world',
  favorite: 1,
  equation: '1+1',
  random: {},
  arr: []  
}

// After
{
  hello: "'world'",
  favorite: 1,
  equation: "'1+1'",
  random: "{}",
  arr: "[]"
}
```

## Usage
```js
var stringify = require('stringify-object-values');
stringify(obj);
```

#### With `webpack.DefinePlugin`
```js
var webpack = require('webpack');
var stringify = require('stringify-object-values');

module.exports = {
  plugins: [
    new webpack.DefinePlugin({ 'process.env': stringify(process.env) });
  ]
}
```