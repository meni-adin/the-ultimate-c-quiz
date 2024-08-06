What is the difference between the memory pointed to by `ptr1` and `ptr2` at the end of this code?

```c
int *ptr1 = malloc*(sizeof(int));
*ptr1 = 0;

int *ptr2 = calloc*(sizeof(int), 1);
```