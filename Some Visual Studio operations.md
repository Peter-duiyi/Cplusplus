## Some Visual Studio operations

### The differences between build, clean and rebuild

build -- compile the program  
clean -- delete any intermediate and output files  
rebuild - clean the files and then complie the program  

------
### The differences between debug mode and release mode  
* They both belong to solution configuration
* you can debug in the debug mode by watching the changes of variables
* most of optimizations will be canced, inline for example
* in release mode, some optimization will be done(you can also check then in the properties of project) and that's way it runs faster than debug mode
* we can use preprossor statement to write debug code, which will be complied in the debug mode(but we need to add modification into preprossor definition and set the project as .exe before doing that)

```
#ifdef DEBUG
int main() {
	std::cout << "This is for debugging\n";
}
#endif // DEBUG
```
------
### How to run project seperately without opening a new VS window
* add project to current solution and right click it to set it a startup project

------
### How does Compiler work 
1. preprosseor will handle all the prerossor statements before compiling(if go to properties and set preprocess to a file, a `.i` file will appear)
2. convert `.cpp` files -> `.obj` files(binary)

------
### How does linker work 

------
### Reference
How the C++ Compiler Works: https://www.youtube.com/watch?v=3tIqpEmWMLI
