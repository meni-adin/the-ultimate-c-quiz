What is the problem with the following code?

```c
#include <stddef.h>

union MyUnion
{
    unsigned long long i;
    void *ptr;
} myUnion;

int main(void)
{
    return (myUnion.ptr == NULL);
}
```
