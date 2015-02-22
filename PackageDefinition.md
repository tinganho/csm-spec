You must define your package in package.json. Just like NPM!
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
  },
  "main": "index.js"
}
```