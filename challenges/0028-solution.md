Look at this example (assuming `CHAR_BIT == 8`):

1
---

```c
#include <stdio.h>

int main()
{
    union MyUnion
    {
        int i;
        char c;
    } myUnion = {256};

    printf("%d\n", myUnion.i);
}
```

Output is:
```
256
```

2
---

```c
#include <stdio.h>

int main()
{
    union MyUnion
    {
        char c;
        int i;
    } myUnion = {256};

    printf("%d\n", myUnion.i);
}
```

Output is:
```
0
```

This is because the first member of a `union` is the one initialized.
