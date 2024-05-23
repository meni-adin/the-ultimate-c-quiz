In modern C, the integer promotion turns (1u - 2) into expression of type unsigned int, with value -1 modulo 2 to the power of the width of an int, which is equal to UINT_MAX (C11, §6.3.1.8).
When assigned to an int, since it can't hold that value, the assigned value is implementation-defined (C11, §6.3.1.3).
When assigned to a long, assuming a long can hold UINT_MAX, tha value is unchanged (C11, §6.3.1.3).
