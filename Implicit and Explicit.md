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
Then you will find the statement before will not work anymore unless you call it constructor `explicitly` as below.
```
Student c = Student(std::string("Ming"));
Student d = Student(24);
```

Our professor fawcett calls it `promotion constructor` and I don't know why. Anyway, I searched online and found a usefull video on Yutube and for the purpose of learning, I write down this article to `explicitly` remember it.

------
### Reference
Implicit Conversion and the Explicit Keyword in C++: https://www.youtube.com/watch?v=Rr1NX1lH3oE  
