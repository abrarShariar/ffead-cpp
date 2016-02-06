# `ExampleDynamicView.h` #
```
#ifndef EXAMPLEDynamicView_H_
#define EXAMPLEDynamicView_H_
#include "DynamicView.h"

class ExampleDynamicView: public DynamicViewHandler {
public:
	ExampleDynamicView();
	virtual ~ExampleDynamicView();
	Document getDocument();
};
#endif /* EXAMPLEDynamicView_H_ */
```


# `ExampleDynamicView.cpp` #
```
ExampleDynamicView::ExampleDynamicView()
{}
ExampleDynamicView::~ExampleDynamicView()
{}
Document ExampleDynamicView::getDocument()
{        
        Document doc;
        /*Create a Document object*/
        return doc; 
}
```