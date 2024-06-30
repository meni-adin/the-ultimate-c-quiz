What is the value of `s2->d[0]` after the last assignment?
(variation of C11 §6.7.2.1.25)

```
    struct s { int n; double d[]; } *s1, *s2;

    s1 = malloc(sizeof (struct s) + sizeof(double));
    s2 = malloc(sizeof (struct s) + sizeof(double));

    s2->d[0] = 1;

    *s2 = *s1;
```
