Though this expression is perfectly fine in modern `C`, in `K&R C` (`§7`) it is specified that:

> expressions involving a commutative and associative operator may be rearranged, even in the presence of parentheses.

That means that in our case, the expression can be evaluated as `(INT_MAX + 1) - 1`, which causes `signed-integer` overflow which is undefined.
