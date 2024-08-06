The following example is from `C11`, `§6.8.3.6`, but was removed in `C23` Standard - why?

> __EXAMPLE 3__ A null statement may also be used to carry a label just before the closing } of a compound statement.
```c
while (loop1) {
    /* ... */
    while (loop2) {
        /* ... */
        if (want_out)
            goto end_loop1;
        /* ... */
    }
    /* ... */
end_loop1: ;
}
```
