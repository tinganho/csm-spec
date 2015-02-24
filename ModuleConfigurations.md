# Configurations

## Slim Configuration
You must define your package in `slim.json`.
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
  "main": "index.js",
  "moduleFolder": "modules"
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

### moduleFolder
The name of your module folder.
