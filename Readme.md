CSM
====

CSM is a package manager for Typescript and stands for Client-Server Modules. It analyze your code to efficiently shake off non-used function. It allows pre-processing code block inclusion for each platform—client or server. It addresses some of the big problem with node applications being very heavy in code. Each member of this package management tool must pay a yearly fee—this fee is later shared through module owners and maintainers. The formula for sharing revenue is based on the amount of code and popularity of the module.

## Contents
 * [Installation](#installation)
 * [Function Shaking](#function-shaking)
 * [Annotations](#annotations)
 * [Module Configurations](ModuleConfigurations.md)
 * [Implementation](#implementation)
 * [CLI Methods](#cli-methods)

## Installation
```
npm install csm -g
```

## Function Shaking
```typescript
module Application {
  export default class CSM{
    test1() {
      ...
    },

    /// @if client
    /// @public
    test2() {
      this.test();
    },
    /// @endif

    /// @if client
    test3_() {
      ...
    }
    /// @endif
  }
}

```

If I later decides in an another file to only use method `test3()`. Then, method `test2()` will not be compiled. Assuming that only two files are used through out your application.

```typescript
/// @requires Application

var csm = new Application.CSM();
csm.test3();
```

## Annotations
You must make annotations in your code to mark if a function is for server-side or client-side usage.

### Client-side usage:
```
/// @if client
/// @endif
```

### Server-side usage:
```
/// @if server
/// @endif
```

### Server-side or client side usage:
```
/// @if server
/// @else
/// @endif
```

### Requires
Requires a module.
```
/// @requires <name>
```
## Implementation

CSM uses TypeScript's compiler API to compile files. Though it uses its' own internal API:s to do some pre-processing first. The pre-processing steps includes function shaking and conditional include filtering.

## CLI methods

### install
`csm install` will install all your modules.

`csm install <module_name>` will install `module_name`.

`csm install <module_name> -g` will install `module_name` globally.

The installation folder for all modules would be defined in your `csm.json` file. It uses

### publish
`csm publish` will publish your module to a public repo.

### test

`csm test` will both performance and unit test your module. It will also the offical CSM repo so that the version of your module follows semver.
