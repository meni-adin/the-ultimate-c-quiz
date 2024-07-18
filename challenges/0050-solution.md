The `strcmp` function perform the comparison according to the value of each character, and there is no rule that says that 'B' should be greater than 'a'.
To avoid such problems you should use `strcoll` instead.

However, if the call is:
```
strcmp(“000”, “001”);
```
Since the Standard requires the values of the digits to be one more than the precious one, it's safe to compare with `strcmp`.
