You can use designators (`C11`, `§6.7.9.36`):

```c
#include <stdio.h>

int main(void)
{
    int arr[] = {[98] = 1, 2};
    printf("[0] : %d\n[98]: %d\n[99]: %d\n", arr[0], arr[98], arr[99]);
}
```
