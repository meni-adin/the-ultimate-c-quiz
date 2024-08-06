1. Pre-`C99` it is allowed to completely omit the inclusion, since it's OK to implicitly declare functions.
2. Pre-`C99` it is allowed to omit the `int` before the definition of `main`, since such declarations are defaulted to `int`.
3. In all `C` standards, you can use the function `puts` which automatically puts `\n` at the end.
