# `TestCronBasedJob.h` #
```
#ifndef TESTCRONBASEDJOB_H_
#define TESTCRONBASEDJOB_H_
#include "string"
#include <iostream>
#include "CastUtil.h"
using namespace std;

class TestCronBasedJob {
	int counter;
public:
	TestCronBasedJob();
	virtual ~TestCronBasedJob();
	void runJob();
};

#endif /* TESTCRONBASEDJOB_H_ */
```


# `TestCronBasedJob.cpp` #
```
#include "TestCronBasedJob.h"

TestCronBasedJob::TestCronBasedJob() {
	counter = 0;
}

TestCronBasedJob::~TestCronBasedJob() {
	// TODO Auto-generated destructor stub
}

void TestCronBasedJob::runJob() {
	cout << "Job process run number - " + CastUtil::lexical_cast<string>(++counter) << endl;
}
```


# Config for jobs in `application.xml` #
```
<job-procs>
		<job-proc cron="* * * * *" name="testCronJob" class="TestCronBasedJob" method="runJob"/>
</job-procs>
```