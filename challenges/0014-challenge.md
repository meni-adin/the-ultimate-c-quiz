Why assignment like the following is forbidden?
(taken from C11 §6.5.16.2.6)

```
    const char **cpp;
    char *p;

    cpp = &p;
```