It's forbidden because otherwise it would allow the following:

```
    const char **cpp;
    char *p;
    const char c = 'A';

    cpp = &p;       // constraint violation
    *cpp = &c;      // valid
    *p = 0;         // valid
```