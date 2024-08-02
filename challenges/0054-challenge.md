Explain the result of running the following code:

```c
#include <stdio.h>
#include <limits.h>

typedef struct
{
    unsigned int ui;
    unsigned int ui_31bit : CHAR_BIT * sizeof(unsigned int) - 1;
} MyStruct;


int main(int argc, char *argv[])
{
    MyStruct myStruct = (MyStruct){
        .ui = 1,
        .ui_31bit = 1,
    };

    long long int lli_ui       = 0 - myStruct.ui;
    long long int lli_ui_31bit = 0 - myStruct.ui_31bit;

    printf("lli_ui:       % lli\n", lli_ui);
    printf("lli_ui_31bit: % lli\n", lli_ui_31bit);
}
```

Output:
```
lli_ui:        4294967295
lli_ui_31bit: -1
```