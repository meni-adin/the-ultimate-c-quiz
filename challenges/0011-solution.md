Option 1:
(C11, §6.5.3.4 paragraph 2, footnote 102)
```
int main()
{
    char *ptr = 0;
    sizeof(*ptr);
}
```

Option 2:
(C11, §6.5.3.2 paragraph 4, footnote 102)
```
int main()
{
    char *ptr = 0;
    &*ptr;
}
```
