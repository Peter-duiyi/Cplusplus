## String Operations

### Compare

Compare C string: use strcmp
Compare C++ string: use compare

a.compare(b)
* if a is longer than b, return 1
* if a and b has same length but the first non-matching letter of a is larger than b's, return 1
* char type variables cannot be used as input

for example
```
a = "c"
b = "b"
a.compare(b) = 1

a = "aa"
b = "c"
a.compare(b) = 1
```

It's also the same rule if you use '<' '>' and '==' to compare strings

```
a = "c"
b = "b"
if(a > b) cout << "True";

a = "aa"
b = "c"
if(a > b) cout << "True";

a = "a"
b = "a"
if(a == b) cout << "True";
```
------
### Reference
C++ Compare: http://www.cplusplus.com/reference/string/string/compare/
