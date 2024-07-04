What's the difference between the first 3 declarations and the last one?
(taken from C11 §6.7.6.3.21)

```
    void f(double (* restrict a)[5]);
    void f(double a[restrict][5]);
    void f(double a[restrict 3][5]);
    void f(double a[restrict static 3][5]);
```
