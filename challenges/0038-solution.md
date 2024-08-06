Until `C89` - yes. It's OK to return from a non-`void` function without an expression as long as the returned value isn't used.

It's not allowed since `C99` (`§6.8.6.4.1`).
