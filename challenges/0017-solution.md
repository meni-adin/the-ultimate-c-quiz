Only `sizeof(arr)` and `_Alignof(arr)`, as it's forbidden to do address-related operation on objects that are `register` qualified, and array element access is address-related.
