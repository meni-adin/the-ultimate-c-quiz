The Standard (`C11`, `§6.8.6.4.4`) gives that example:

```c
struct s { double i; } f(void);

union {
    struct {
        int f1;
        struct s f2;
    } u1;
    struct {
        struct s f3;
        int f4;
    } u2;
} g;

struct s f(void)
{
    return g.u1.f2;
}

/* ... */

g.u2.f3 = f();
```

> there is no undefined behavior, although there would be if the assignment were done directly (without using a function call to fetch the value).
