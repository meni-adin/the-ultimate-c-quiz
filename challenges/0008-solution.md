It depends on the base used:

```c
strtol("0x10", NULL, 0);  // 16     - The '0x' prefix identifies the representation as hexadecimal, so it's ignored and the value is 16.
strtol("0x10", NULL, 2);  // 0      - The '0' is identified as 0, and the conversion stops at 'x' as it's not a digit in base 2.
strtol("0x10", NULL, 3);  // 0      - Same as 2.
...
strtol("0x10", NULL, 15); // 0      - Same as 2.
strtol("0x10", NULL, 16); // 16     - same as 0.
strtol("0x10", NULL, 17); // 0      - Same as 2.
...
strtol("0x10", NULL, 33); // 0      - Same as 2.
strtol("0x10", NULL, 34); // 38182  - The 'x' is a digit.
strtol("0x10", NULL, 35); // 40460  - The 'x' is a digit.
strtol("0x10", NULL, 36); // 42804  - The 'x' is a digit.
```
