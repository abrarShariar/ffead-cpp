# `Service1.h` #

```
#ifndef SERVICE1_H_
#define SERVICE1_H_
#include "string"
#include "ServiceInt.h"
using namespace std;

class Service1 :public ServiceInt{
public:
	Service1();
	virtual ~Service1();
	string service1();
};

#endif /* SERVICE1_H_ */
```



# `Service2.h` #

```
#ifndef SERVICE2_H_
#define SERVICE2_H_
#include "string"
#include "ServiceInt.h"
using namespace std;
class Service2 : public ServiceInt{
public:
	Service2();
	virtual ~Service2();
	string service2(string);
};

#endif /* SERVICE2_H_ */
```