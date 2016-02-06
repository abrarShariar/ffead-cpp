# `TestComponent.cpp` #

```
/*
Client code can use a Remote Bean to invoke Business Logic
Local Applications/Modules can use the Local Bean instance
Trying to get Local Bean instance from client code will throw exception
*/
#include "BeanContext.h"
#include "Component_TEST_BEAN_Remote.h"
#include "Component_TEST_BEAN.h"

int main()
{
        /*Declare the BeanContext with the remote component listening host and port*/
	BeanContext cntxt("localhost",7001);

        /*Get the Remote Bean Instance*/
	Component_TEST_BEAN_Remote *remote = (Component_TEST_BEAN_Remote*)cntxt.lookup("TEST_BEAN");

	string a ="Hello Business Logic!!";
	if(remote!=NULL)
        {
                /*Invoke the remote method on the Bean*/
                cout << remote->mySecondService(a) << flush;
        }

        /*The Below line should throw exception*/
        Component_TEST_BEAN local;
	return 1;
}
```