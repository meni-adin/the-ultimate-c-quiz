Although the expression can be evaluated at compile-time to 1,
the standard says (C11 §6.7.6.2.4):
> If the size is an integer constant expression and the element type has a known constant size, the array type is not a variable length array type; otherwise, the array type is a variable length array type.

and §6.6.6, `integer constant` is defined as:

> An integer constant expression shall have integer type and shall only have operands that are integer constants ... and floating constants that are the immediate operands of casts.

Since the immediate operand here is the result of a division operation, it isn't an `integer constant`, and the array should have a VLA type
(although it seems that on some compilers it's still a usual array).
