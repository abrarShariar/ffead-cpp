
```
#include "Reflector"
#include "Test.h"

int main()
{
	Reflector reflector;
	ClassInfo clas = reflector.getClassInfo("Test");
	args argus;
	argus.push_back("int");
	vals valus;
	int ids = 1;
	valus.push_back(&ids);
	Method meth = clas.getMethod("setId",argus);
	reflector.invokeMethod<void*>(clas.getInstance(),meth,valus);
	argus.clear();
	meth = clas.getMethod("getId",argus);
	int id = reflector.invokeMethod<int>(clas.getInstance(),meth,valus);
	cout << id << flush;cout << "\n" << flush;
	Field fld = clas.getField("id");
	void* idp = reflector.getField(clas.getInstance(),fld);
	Test *p = new Test;
	cout << p->getId() << flush;cout << "\n" << flush;
	cout << reflector.instanceOf(clas.getInstance(),"Test") << flush;
	bool fl;
        cout << "static::" << Object::instanceOf(*p,"Test") << "\n" << flush;
	cout << reflector.instanceOf(reflector,"Test") << flush;
	cout << reflector.instanceOf(clas,"Test") << flush;
}
```