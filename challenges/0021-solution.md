1. In the first version, `i` is evaluated twice, where in the second version it's evaluated only once. It can be significant when `i` is an expression with side-effects.
2. Only the second version is allowed when dealing with `Atomic`.
