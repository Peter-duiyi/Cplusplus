## Static

### Static - outside of a class
* if you define static variable in a .h file and include it in different .cpp files, you will create static variable in each cpp files
* static variables or functions can only be seen from the file that you define the variables and files which include that file

### Static - inside of a class

#### Static Variable
Suppose we have a Student class
```
class Student {
public:
	Student() {}
	static int _stuNum;
};
```
Since static variables must be defined somewhere: 
```
//define static
int Student::_stuNum;
```
then we can use it in the main function
```
int main() {
	Student::_stuNum = 5;
}
```
* static variable in the class has nothing to do with any kind of allocation when instances are created
* it is normally used to store some data that you may want ot share with other instances of the class

#### Static Function
So in the previous example, we can add a static functions to the code.
```
class Student {
public:
	Student() {}
	static int _stuNum;
	static void Print() {
		cout << _stuNum << " ";
	}
};
//define static
int Student::_stuNum;
```
And in the main function:
```
int main() {
	Student::_stuNum = 5;
	Student::Print_1();
}
```
* Since static method doesn't have a class instance, we cannot get nonstatic variable from a static method. 
* Static method in the class can only have access to static variables. 

#### Local Static
If we have a static variable initialized in a function, for example, 
```
function1(){
	static int a = 5;
}
```
then a is only a local static variable in the function, so it cannot be visited in other place beside that function.


------
### Reference
Static in C++: https://www.youtube.com/watch?v=f3FVU-iwNuA  
Static for Classes and Structs in C++: https://www.youtube.com/watch?v=V-BFlMrBtqQ
Local Static in C++ :https://www.youtube.com/watch?v=f7mtWD9GdJ4&list=PLlrATfBNZ98dudnM48yfGUldqGD0S4FFb&index=23  

