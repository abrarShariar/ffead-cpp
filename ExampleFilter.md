
```

ExampleRequestFilter.cpp
#include "Filter.h"

class ExampleRequestFilter : public Filter
{
    void doInputFilter(HttpRequest *request)
    {
        //Pre/Post Processing of request
        request.set....        
    }
};


ExampleResponseFilter.cpp
#include "Filter.h"

class ExampleResponseFilter : public Filter
{
    void doOutputFilter(HttpResponse *response)
    {
        //Pre/Post Processing of response
        response.set....        
    }
};


application.xml
<app>
	<filters>
		<filter class="ExampleRequestFilter" type="in"/>
		<filter class="ExampleResponseFilter" type="out"/>
	</filters>
</app>
```