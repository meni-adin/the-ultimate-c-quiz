Since the variable has static storage duration, it's initialized to 0.
But because the first member is an integer type, that 0 initialization is turning all the integer bits to 0 (C11 §6.7.9.10).
Although the size of a pointer to void may be the same as the size of `unsigned long long`, since it's not
guaranteed that a null-pointer has all-0 bit pattern, the comparison isn't valid.
