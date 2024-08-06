Since the standard doesn't requires that any of the memory allocation functions ever succeeds, the simplest implementation is just returning `0` always:

(you might cast the arguments to `(void)` inside the function to suppress `unused-variable` warnings from the compiler)

```c
#include <stdlib.h>

void *calloc(size_t nmemb, size_t size){return 0;};
void free(void *ptr)                   {};
void *malloc(size_t size)              {return 0;};
void *realloc(void *ptr, size_t size)  {return 0;};
```
