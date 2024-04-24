# @ellentorg/jubilant-tribble

Babel plugin that adds React import declaration if file contains JSX tags.

This plugin is only about stateless components that doesn't extends `React.Component`.
If you want to use any other React functions then you should import their by yourself.

## Example

Your `component.js` that contains this code:

```js
export default function Component() {
  return (
    <div />
  );
}
```

will be transpiled into something like this:

```js
import React from 'react';

export default function Component() {
  /* this part will be transpiled by babel itself as usual */
  return (
    React.createElement('div')
  );
}
```

## Usage

* Install `@ellentorg/jubilant-tribble`.

```
npm install @ellentorg/jubilant-tribble --save-dev
```

* Add `react-require` into `.babelrc`. This plugin should be defined before `transform-es2015-modules-commonjs` plugin because it's using ES2015 modules syntax to import `React` into scope.

```json
{
  "plugins": [
    "react-require"
  ]
}
```
