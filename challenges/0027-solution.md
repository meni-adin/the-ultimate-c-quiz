Seems like there is no agreement between different compilers - clang (macOS) and GCC (Ubuntu) vs Visual Studio (Windows).

## 1

clang and GCC:
```
1, 2
sizeof(struct MyStruct): 8
```

Visual Studio: compilation error

The relevant paragraphs from C11 Standard (draft N1570):

§6.7.9.9
> Except where explicitly stated otherwise, for the purposes of this subclause unnamed members of objects of structure and union type do not participate in initialization. Unnamed members of structure objects have indeterminate value even after initialization.

§6.7.9.13
> The initializer for a structure or union object that has automatic storage duration shall be either an initializer list as described below, or a single expression that has compatible structure or union type. In the latter case, the initial value of the object, including unnamed members, is that of the expression.

As the last sentence specifically talks about the latter case, we can understand that this exception does not apply to the former one, hence the rule from §6.7.9.9 is still relevant.

## 2

clang and GCC:
```
1, 2
sizeof(struct MyStruct): 8
```

Visual Studio:
```
1, 0
sizeof(struct MyStruct): 12
```

## 3

clang and GCC:
```
1, 0
sizeof(struct MyStruct): 12
```

Visual Studio:
```
1, 0
sizeof(struct MyStruct): 12
```

It seems that when the struct is't tagged another rule takes place:

§6.7.2.1.13
> An unnamed member whose type specifier is a structure specifier with no tag is called an anonymous structure; an unnamed member whose type specifier is a union specifier with no tag is called an anonymous union. The members of an anonymous structure or union are considered to be members of the containing structure or union. This applies recursively if the containing structure or union is also anonymous.

This explains clang and GCC, while Visual Studio seems to ignore the Standard.
