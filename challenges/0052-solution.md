The idea behind this rule is right, and it should be followed in a normal program, but there is a way to write a perfectly correct program that doesn't follow this rule.

Since the function `realloc` acts as `malloc` if passed a null-pointer (in all `C` standards, at least until `C23`, including), replacing all calls to `malloc` with `realloc` can break the balance of the rule.

In `C89` (but not since `C99`) `realloc` can also act as free if called with size `0`.
