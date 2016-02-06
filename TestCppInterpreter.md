# `TestCppInterpreter.cpp` #

```

#include "CppInterpreter.h"

int main()
{
	/*Create Interpreter Instance*/
	CppInterpreter cpi;

	/*Declare Local variables*/
	int a = 0,b=10;
	string b = "hello!!";

 	/*Bind the desired variables to the Interpreter*/
	cpi.bind<int>("a",a);
	cpi.bind<int>("b",b);

	/*Evaluate the Code String*/
	cpi.eval("while(a<15){a+=3;if(b<50){b+=10;}}");
	cpi.eval("while(a<15){a+=3;}");
	cpi.eval("int y=2;string h=\"fsdfsdfsdfsdf\";for(a=20;a>0;a--){b+=10;y++;}");
	cpi.eval("if(a==2){a=8;}else if(b==11){a=90;}else while(a<50){a++;}");
	cpi.eval("a=10-2+8-6;");
	
	/*Display the Modified variables*/
	cout << a << flush;
	cout << "\n" << flush;
	cout << b << flush;
	cout << "\n" << flush;
	return 1;
}

```