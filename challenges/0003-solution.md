According to the `C11` Standard at `§6.7.2.1`:

> While the number of bits in a _Bool object is at least CHAR_BIT, the width (number of sign and value bits) of a _Bool may be just 1 bit.

which means that as long as the LSB is `0`, an object of type `_Bool` may be evaluated as `false`.
