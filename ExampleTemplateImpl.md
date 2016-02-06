# `ExampleTemplate.h` #
```
#ifndef EXAMPLETEMPLATE_H_
#define EXAMPLETEMPLATE_H_
#include "TemplateHandler.h"

class ExampleTemplate: public TemplateHandler {
public:
	ExampleTemplate();
	virtual ~ExampleTemplate();
	Context getContext();
};
#endif /* EXAMPLETEMPLATE_H_ */
```


# `ExampleTemplate.cpp` #
```
ExampleTemplate::ExampleTemplate()
{}
ExampleTemplate::~ExampleTemplate()
{}
Context ExampleTemplate::getContext()
{        
        Context cntxt;
        /*Add template variables to Context*/
        return cntxt; 
}
```