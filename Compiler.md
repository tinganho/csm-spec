Compiler specification
======================

As a rule of thumb everything that contains an identifier is being shaked off. And all these primitives are shaked off.

- Interfaces
- Constants
- Variables
- Functions
- Class methods
- Classes
- Types?

We should omit functions that takes one other function as a parameter. Because it doesn't contain an identifier.

```
function(value1: , function1) {
     function1();
}
```