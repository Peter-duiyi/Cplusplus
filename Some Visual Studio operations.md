## Some Visual Studio operations

### The differences between build, clean, rebuild

build -- compile the program  
clean -- delete any intermediate and output files  
rebuild - clean the files and then complie the program  

### The differences between debug mode and release mode  

* You can debug in the debug mode by watching the changes of variables
* most of optimizations will be canced, inline for example.
* we can use preprossor statement to write debug code, which will be ran in the debug mode(but we need to add modification into preprossor definition before that)

```
#ifdef DEBUG
int main() {
	std::cout << "This is for debugging\n";
}
#endif // DEBUG
```
