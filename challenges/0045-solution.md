According to `C11`, `§7.21.3.6`:

> The address of the FILE object used to control a stream may be significant; a copy of a FILE object need not serve in place of the original.

That's the reason you shouldn't pass a `FILE` but `FILE *` to a function.
