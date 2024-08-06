__Option 1__:
---

(`C11`, `§6.5.3.4.2`)

```c
int main()
{
    char *ptr = 0;
    sizeof(*ptr);
}
```

__Option 2__:
---

(`C11`, `§6.5.3.2.4`, footnote `102`)

```c
int main()
{
    char *ptr = 0;
    &*ptr;
}
```
