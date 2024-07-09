What would be printed?

```
#include <stdio.h>

int first(void)
{
    printf("%s\n", __func__);
    return 1;
}

int second(void)
{
    printf("%s\n", __func__);
    return 2;
}

int main(void)
{
    int arr[] = {first(), second()};
}
```