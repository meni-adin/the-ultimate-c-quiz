1. In the 1st version, `i` is evaluated twice, where in the 2nd version it's evaluated only once.
It can be significant when `i` is an expression with side-effects.
2. Only the 2nd version is allowed when dealing with Atomic.
