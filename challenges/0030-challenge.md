What would be printed?

```c
#include <stdio.h>

int global_i;

int main(void)
{
    struct MyStruct
    {
        int i;
    } myStruct = {
        .i = ++global_i,
        .i = ++global_i,
    };

    printf("%d\n", global_i);
}
```
