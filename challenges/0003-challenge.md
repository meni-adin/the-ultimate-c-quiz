What is the problem with the following code?

```c
#include <stdio.h>

union MyBool
{
    int i;
    _Bool b;
};

int main()
{
    union MyBool myBool;
    myBool.i = 42;
    if (myBool.b)
        printf("true\n");
    else
        printf("false\n");
}
```
