SLIM
====

Slim is a package/dependency manager for JavaScript. It analyze your code to efficiently function shaking.

package.json
```
{
  name: "slim",
  description: "Slim is a package/dependency manager for JavaScript that does function shaking.",
  exports: "Slim"
  version: "2.0.1",
  "homepage": "https://github.com/tinganho/l10ns",
  "author": {
    "name": "Tingan Ho",
    "email": "tingan87@gmail.com"
  },
  "repository": {
    "type": "git",
    "url": "git://github.com/tinganho/l10ns.git"
  },
  "dependencies": {
    "test": "2.0.1"
  },
  "devDepencies": {
    "test": "2.0.1"
  }
}
```

Module dependencies
```javascript
requires('Module1');
exports('slim', Slim);

class Slim {
  constructor() {

  },

  test1() {

  }

  // Public functions
  test2() {
    this.test();
  },

  // Private function
  test3_() {

  }
}
```

If I later decides in an another file to only use mothed `test3()`. Then, method `test2()` will not be compiled.

```javascript
require('Slim');
slim.test3();
```
