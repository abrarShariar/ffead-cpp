# `ExampleController.h` #
```
#ifndef EXAMPLECONTROLLER_H_
#define EXAMPLECONTROLLER_H_
#include <iostream>
#include "Controller.h"

class ExampleController: public Controller{
public:
	ExampleController();
	virtual ~ExampleController();
	HttpResponse service(HttpRequest);
};
#endif /* EXAMPLECONTROLLER_H_ */
```


# `ExampleController.cpp` #
```
ExampleController::ExampleController()
{}
ExampleController::~ExampleController()
{}
HttpResponse ExampleController::service(HttpRequest request)
{
        /*Play with the request*/
        HttpResponse res;
        /*Modify response*/
        return res; 
}
```


# Config for controller in `application.xml` #
```
<controllers>
	<!--Custom controller handling url patterns-->
	<controller class="DefaultController" url="*.action"/>
	<controller class="DefaultController" url="*.do"/>

	<!--Internal controller handling extension conversions-->
	<controller from="*.yourext" to="*.html"/>
</controllers>        
```