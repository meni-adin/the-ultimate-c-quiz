Since it's invalid for 2 cases to have the same value, the only replacement I can think of is:

```C
int main()
{
    switch(1)
    {
        case __LINE__:
            return 0;
        case __LINE__:
            return 0;
    }
}
```
