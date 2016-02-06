# `ExampleAJAXService.h` #
```
#ifndef ExampleAJAXService_H_
#define ExampleAJAXService_H_
#include "PropFileReader.h"
#include "YObject.h"

class ExampleAJAXService{
public:
	ExampleAJAXService();
	virtual ~ExampleAJAXService();
	YObject sayHello(string,int,float);
	string sayHello1(string,int,float);
	YObject sayHello2(YObject,int,float);
};

#endif /* ExampleAJAXService_H_ */
```


# `ExampleAJAXService.cpp` #
```
ExampleAJAXService::ExampleAJAXService()
{}
ExampleAJAXService::~ExampleAJAXService()
{}
YObject ExampleAJAXService::sayHello(string j,int i,float c)
{
	YObject yobj;
	yobj.i = i;
	yobj.j = j;
	yobj.c = c;
	return yobj;
}
string ExampleAJAXService::sayHello1(string j,int i,float c)
{
	return "Hi There";
}
YObject ExampleAJAXService::sayHello2(YObject arg,int i,float j)
{
	YObject yobj;
	yobj = arg;
        return yobj;
}
```