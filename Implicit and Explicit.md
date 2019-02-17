## Implicit and Explicit

### Implicit

Suppose we have a class as below
```
class Student {
public:
	Student(const std::string &name)
		:_stuName(name) {}
	Student(int num)
		:n_stuNum(num) {}
	void showName();
	void setName(std::string name);
private:
	std::string _stuName;
	int n_stuNum;
};
```
And people usually initialize instances in this way
```
Student a("Ming");
Student b(24);
```
But, actually we can also do it in another way
```
Student c = std::string("Ming");
Student d = 24;
```
It may seem weird, but it will work. And the reason is just like this Yutuber said in his video(link will be put at the end of the article), 
the STD string or the number will be `implicitly` converted into an instance of Student class. 
And it happens because we have defined two constructors, which receive integer or string. 
Since it may cause potential problems sometimes, even most people never initilize objects in this way, we need to solve that problem and that's why we need `explicit`.

### Explicit

Explicit will disable this implicit functionality by simply adding `Explicit` in front of the constructor. 
```
class Student {
public:
	explicit Student(const std::string &name)
		:_stuName(name) {}
	explicit Student(int num)
		:n_stuNum(num) {}
	void showName();
	void setName(std::string name);
private:
	std::string _stuName;
	int n_stuNum;
};
```



Just like  it looks weird and most people never do that. But it still may cause problems and for the purpose of 


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
### Brief explanations of compiling and linking
1. preprosseor will handle all the prerossor statements before compiling(if go to properties and set preprocess to a file, a `.i` file will appear)
2. convert `.cpp` files -> `.obj` files(binary)
3. link all the libraries, `.h` files and `.cpp` files

------
### Two main ways to link to an existing project that you want to use in your solution(From Ammar Salman, who worked as TA and RA in Syracuse University)

Before we start, you need to make sure you copy the project, follow these steps:

1) Copy and paste the project directory that you wish to use and put in under your solution's directory.
2) In Visual Studio, right-click the solution, go to "Add" and select "Add Existing Project". Browse the location of the copied project and select it. The Project should appear now under the solution in VS.

This is to make sure the project you want to import is under the directory of your solution. 

Now you can start and you have two following options.

1) Static Library.
2) Add file shortcuts.

----------------------------------------------------------------------------------------------------------------

#### Static library: (requires changes to both the user and the used projects)

a) Right-click the project you wish to use -> Properties -> General -> Project Defaults -> Configuration Type -> choose "Static Library (.lib)"

b) In the same properties window of the project you wish to use -> C/C++ -> Preprocessor -> Preprocessor Definitions -> Replace TEST_PACKAGENAME with TEST_PACKAGENAME_NO.

c) In the user project, right click References -> Add Reference -> Select the project you wish to use (the one you set to build as Static Library). 

d) Build both projects and you should be ready.

Note: step (b) above is used to make sure the test stub of the project you wish to use is not compiled which can cause linker issues otherwise since you cannot have two '::main' functions in C++ as '::main' is the entry point of the resulting assembly. 

----------------------------------------------------------------------------------------------------------------

#### Add file shortcuts: (requires changes only to the user project, used project can be left untouched)

Right-click user project -> Add -> Existing Item.. -> Select all source code files (.h and .cpp) of the project you wish to use. 

Note: if the used project depends upon another project, you will also have to add the latter's files as shortcuts. 

----------------------------------------------------------------------------------------------------------------
Each approach has its own benefits, you may choose either. 

------
### Reference
Implicit Conversion and the Explicit Keyword in C++: https://www.youtube.com/watch?v=Rr1NX1lH3oE  
