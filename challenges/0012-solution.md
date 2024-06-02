The following code would print the value UINT_MAX as the first result, due to integer-promotion in conditional operator,
assuming `long` can hold it:

```
#include <stdio.h>
#include <stdbool.h>

int main()
{
    bool b = true;
    int arg1 = -1;
    unsigned int arg2 = 0;
    long result;

    result = b ? arg1 : arg2;
    printf("First result: %ld\n", result);

    if (b)
        result = arg1;
    else
        result = arg2;
    printf("Second result: %ld\n", result);
}
```
