According to `the integer promotions` (`C11`, `§6.3.1.1.2`), in every arithmetic operation an `unsigned int` is promoted to `unsigned int`, since an `int` can't represent all the values of `unsigned int`, hence the in the line

```c
long long int lli_ui       = 0 - myStruct.ui;
```

the `0` constant is converted to an `unsigned int` (according to the `Usual arithmetic conversions`, `C11`, `§6.3.1.8.1`) so the result of the operation is a wrap-around to `UINT_MAX`.

In the second line:

```c
long long int lli_ui_31bit = 0 - myStruct.ui_31bit;
```

the compiler knows that an `int` can represent any `unsigned int` value that uses one bit less than the width of an `int`, so the unsigned bit-field value is promoted to `int`, and the `0` constant which also has type `int` isn't converted. Hence the result isn't wrapped-around and we get `-1`.
