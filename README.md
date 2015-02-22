SLIM
====

Slim is a package/dependency manager for JavaScript. It analyze your code to efficiently shake off non-used function. It is also the ES6+ package manager for Client-Server Rendered Applications.

## Contents
[Module](#module)
[Annotations](#annotations)
[Package](#package)

## Module
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

## Package
You must define your package in package.json. Just like NPM!
```json
{
  "name": "slim",
  "description": "Slim is a package/dependency manager ...",
  "exports": "Slim",
  "version": "2.0.1",
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
  },
  "main": "index.js"
}
```

### name
Name of your package.

### description
Description of your package.

### version
The semantic versioning of your package.

### homepage
The official website of your package.

### author
Authors:

```json
{
  "name": "Tingan Ho",
  "email": "tingan87@gmail.com"
}
```

### repository
Official repository:
```json
{
  "type": "git",
  "url": "git://github.com/tinganho/l10ns.git"
}
```


### maintainers
Maintainers of your package:
```json
[{
  "name": "Tingan Ho",
  "email": "tingan87@gmail.com"
}]
```
