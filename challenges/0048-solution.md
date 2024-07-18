Since the 2nd argument passed to calloc is 1, the memory it allocates here has no alignment and basically using it as `int` is forbidden.
If it was changed to:
```
int *ptr2 = calloc*(1, sizeof(int));
```
it would be OK but still not exactly the same as ptr1, as ptr2 is not necessary aligned to the alignment requirement of `long long` for instance, while ptr1 does.
