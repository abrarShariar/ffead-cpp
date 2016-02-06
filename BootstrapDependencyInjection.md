
```
#include "FFEADContext.h"
#include "TestBeanProp.h"
#include "TestBeanCons.h"
#include "TestBeanIntf.h"

int main()
{
    FFEADContext *cntxt = new FFEADContext("/path/to/depInj.xml");

    //Get the testBeanProp from the container 
    TestBeanProp *testBeanProp = (TestBeanProp*)cntxt->getBean("testBeanProp");
    testBeanProp->print();

    //Get the testBeancons from the container 
    TestBeanCons *testBeanCons = (TestBeanCons*)cntxt->getBean("testBeanCons");
    testBeanCons->print();

    //Get the testBeanPIntf from the container 
    TestBeanIntf *testBeanIntf = (TestBeanIntf*)cntxt->getBean("testBeanIntf");
    testBeanIntf->print();
 
    //Clean up resources
    cntxt->clear();
    return 1;
}

/*
The output of the following program would be
Hello World!!Hello World 1234Hello World!!
*/
```