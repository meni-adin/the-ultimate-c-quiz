It's forbidden to access any member of a `union` that's isn't the current 'active' member.
There is an exception though:

> if a union contains several structures that share a common initial sequence ... and if the union object currently contains one of these structures, it is permitted to inspect the common initial part of any of them anywhere that a declaration of the completed type of the union is visible.

The problem in our case is that the declaration ot the `union` isn't visible within function `f`.

In reality, both GCC and clang output (from certain optimization level and above) is `-1`, as they (correctly) assume that p1 and p2 can't point to the same object.

However, according to the Standard, the following code has a well-defined behavior:

```c
#include <stdio.h>

struct t1 { int m; };
struct t2 { int m; };
union {
    struct t1 s1;
    struct t2 s2;
} u;

int f(struct t1 *p1, struct t2 *p2)
{
    if (p1->m < 0)
        p2->m = -p2->m;
    return p1->m;
}

int main(void)
{
    u.s1.m = -1;
    printf("%d\n", f(&u.s1, &u.s2));
}
```

but running it has the same results.

Turns out there is an old discussion on this issue in the GCC community: [here](https://gcc.gnu.org/bugzilla/show_bug.cgi?id=14319) and [here](https://gcc.gnu.org/bugzilla/show_bug.cgi?id=65892)
