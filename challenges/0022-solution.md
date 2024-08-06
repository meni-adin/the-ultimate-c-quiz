According to `C11`, `§6.7.2.2`:

The type of the enumeration type `enum MyEnum` should be compatible with `char` or one of the signed/unsigned integer types.

The type of the enumeration constant `MyFirst` have type `int`.

It seems that compilers may not obey this and use wider types if the enumerator constant are assigned large values.
