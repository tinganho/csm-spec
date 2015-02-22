SLIM
====

Slim is a package/dependency manager for JavaScript. It analyze your code to efficiently shake off non-used function.

## Contents
[PackageDefinition][]

## Module definition
```javascript
import module1 from 'Module1';

export default class Slim {
  test1() {
    ...
  },

  // Public functions
  // @universal
  test2() {
    this.test();
  },

  // Private function
  // @client
  test3_() {
    ...
  }
}
```

If I later decides in an another file to only use mothed `test3()`. Then, method `test2()` will not be compiled. Assuming that only two files are used through out your application.

```javascript
import slim from 'Slim';
slim.test3();
```

## Annotations
You must make annotations in your code to mark if a function is for server-side or client-side usage.

### Client-side usage:
```
// @client
```

### Server-side usage:
```
// @server
```

### Universal usage:
```
// @universal
```

[PackageDefinition]: ./PackageDefinition.md
