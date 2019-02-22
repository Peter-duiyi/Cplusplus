## String Operations

### Compare

Compare C string: use strcmp  
Compare C++ string: use compare

a.compare(b)  
I tried to explain how it works. But what I writed was not as concise and intelligible as the definition from c++ reference.
value	relation between compared string and comparing string
* 0	They compare equal
* <0	Either the value of the first character that does not match is lower in the compared string, or all compared characters match but the compared string is shorter.
* >0	Either the value of the first character that does not match is greater in the compared string, or all compared characters match but the compared string is longer.

for example
```
s1 = "ab"
s2 = "aa"
a.compare(b) = 1
//same length, but "b" > "a"

s1 = "b"
s2 = "aaaaaaaaa"
a.compare(b) = 1
// "b" > "a"
```

It's also the same rule if you use '<' '>' and '==' to compare strings

```
s1 = "ab"
s2 = "aa"
if(s1 > s2) cout << "True";
//True

s1 = "b"
s2 = "aaaaaaaaa"
if(s1 > s2) cout << "True";
//True
```
------
### Reference
C++ Compare: http://www.cplusplus.com/reference/string/string/compare/
