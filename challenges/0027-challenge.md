What will be the output in each of the following:

## 1
```
#include <stdio.h>

int main()
{
    struct MyStruct
    {
        int a;
        int;   // unnamed member
        int c;
    };
    struct MyStruct myStruct = {1, 2};

    printf("%d, %d\n", myStruct.a, myStruct.c);
    printf("sizeof(struct MyStruct): %zu\n", sizeof(struct MyStruct));
}
```

## 2
```
#include <stdio.h>

int main()
{
    struct MyStruct
    {
        int a;
        struct s // int moved into tagged struct
        {
            int b;
        };
        int c;
    };
    struct MyStruct myStruct = {1, 2};

    printf("%d, %d\n", myStruct.a, myStruct.c);
    printf("sizeof(struct MyStruct): %zu\n", sizeof(struct MyStruct));
}
```

## 3
```
#include <stdio.h>

int main()
{
    struct MyStruct
    {
        int a;
        struct // no tag
        {
            int b;
        };
        int c;
    };
    struct MyStruct myStruct = {1, 2};

    printf("%d, %d\n", myStruct.a, myStruct.c);
    printf("sizeof(struct MyStruct): %zu\n", sizeof(struct MyStruct));
}
```
