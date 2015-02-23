SLIM
====

Slim is a package manager for Typescript. It analyze your code to efficiently shake off non-used function. It is also a package manager for Client-Server Rendered Applications. It allows pre-processing code block inclusion for each platform—client or server. It addresses some of the big problem with node applications being very heavy in code. Each member of this package management tool must pay a yearly fee—this fee is later shared through module owners and maintainers. The formula for sharing fee is based on the amount of code and popularity.

## Contents
 * [Module](#module)
 * [Annotations](#annotations)
 * [Package](#package)

## Module
```javascript
import module1 from 'Module1';

export default class Slim {
  test1() {
    ...
  },

  /// if client
  // Public functions
  test2() {
    this.test();
  },
  /// endif

  // Private function
  // @client
  test3_() {
    ...
  }
}
```

If I later decides in an another file to only use method `test3()`. Then, method `test2()` will not be compiled. Assuming that only two files are used through out your application.

```javascript
import slim from 'Slim';
slim.test3();
```

## Annotations
You must make annotations in your code to mark if a function is for server-side or client-side usage.

### Client-side usage:
```
/// if client
/// end if
```

### Server-side usage:
```
/// if server
/// endif
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

### dependencies
Dependencies for your package:
```json
{
  "slim": "^1.0.0"
}
```

### devDependencies
Development dependencies for your package:
```json
{
  "slim": "^1.0.0"
}
```

### peerDependencies
Peer dependencies for your package:
```json
{
  "slim": "^1.0.0"
}
```
