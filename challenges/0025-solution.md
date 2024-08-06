Consider the following code:

__main.c__
---

```c
float my_func();

int main(void)
{
    float f1 = 123456;
    float f2 = my_func(f1);
    if (f1 == f2)
    {
        printf("Just as expected\n");
    }
    else
    {
        printf("Unexpected result\n");
    }
}
```

__my_lib.c__
---

```c
float my_func(float f)
{
    return f;
}
```

It may seems like the function returns exactly what it gets, but it's not true.

Since where there is no function prototype, the `usual-arithmetic-conversions` is performed on all arguments, in that case converting the float to a double. Since the called function expects a float, the input isn't layed out correctly in memory, probably causing undefined-behavior. Then, the sign, exponent, and mantissa of the float are interpreted and returned to the caller, causing a wrong number to be returned.

There are many other errors that could occur (wrong number of arguments, etc.)
