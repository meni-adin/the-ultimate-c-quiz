Why the following is valid code?
(taken from C11 §6.6, footnote 118)

```
    static int i = 2 || 1 / 0;
```