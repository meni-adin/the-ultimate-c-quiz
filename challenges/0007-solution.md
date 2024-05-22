The standard-library function `strchr` can by used to do it:
```
#include <string.h>

void *removeConst(const void *cptr)
{
    return strchr(cptr, *((const char *)cptr));
}
```

Note: since C23, it's required to suppress the generic function by surrounding the function name with parentheses.
