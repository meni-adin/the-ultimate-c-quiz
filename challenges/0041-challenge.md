To what does this expand?

```c
#define f(a) a*g

#define g(a) f(a)

f(2)(9)
```
