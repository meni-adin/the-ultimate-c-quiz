Find the bug:

```c
#include <stdio>

void(FILE file)
{
    char *arr[10];
    fread(arr, 1, 10, &file);
}

int main()
{
    FILE *file = fopen("my_file.txt", "r");
    if (f)
    {
        tryRead(*file);
    }
}
```
