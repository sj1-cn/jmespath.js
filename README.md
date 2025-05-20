## Introduction
This is the fork of https://github.com/jmespath/jmespath.js

This fork add the `extendsFunction` API. Provide the ability to override builtin-functions or extend custom functions.

The package name changed from `jmespath` to `@yidata/jmespath`

## Install

```sh
npm install --save @yidata/jmespath
```

## Usage

```js
import jmespath from '@yidata/jmespath'

jmespath.extendsFunction('foo', function (supportedTypes) {
  return {
    processor: function (resolvedArgs) {
      return 99 + resolvedArgs[0];
    },
    signature: [
      { types: [supportedTypes.TYPE_NUMBER] }
    ]
  }
});
jmespath.search({ bar: 1 }, 'foo(bar)')
// The result should be 100
```
> [!NOTE]
> All other functionalities are the same with the original jmespath
