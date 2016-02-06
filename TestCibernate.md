
```
#include "Cibernate.h"
#include "Test.h"
#include "Timer.h"
#include "Object.h"

int main()
{
	Cibernate chib("MySQL-test","sumeet","sumeet");
	int i=2,j=4,k;
	Object oi;
	oi << i;
	Object oj;
	oj << j;
	Object ok;
	ok << k;
	chib.addParam("i","in",oi);
	chib.addParam("j","inout",oj);
	chib.addParam("k","out",ok);
	Timer tim;
	tim.start();
	chib.procedureCall("func1");
	vector<Test> tec = chib.getARAC<Test>();
	int id1=1;
	string name1 = "sumeet";
	oi << id1;
	oj << name1;
	chib.addParam("id",oi);
	chib.addParam("name",oj);
	tec = chib.getARACW<Test>();
	Test tec1 = chib.getOR<Test>(1);
	tec1 = chib.getOR<Test>(2);
	tec1 = chib.getOR<Test>(3);
	vector<int> tec2 = chib.getAROC<int>("id");
	vector<string> tec3 = chib.getAROC<string>("name");
	id1 = 4;
	name1 = "amit1233";
	oi << id1;
	oj << name1;
	chib.addParam1("id",oi);
	chib.addParam1("name",oj);
	int wid1 = 4;
	oi << wid1;

	Test tr;
	tr.setId(5);
	tr.setName("sumit");
	vector<string> cols;
	cols.push_back("id");cols.push_back("name");
	chib.insertORSC<Test>(tr,cols);
	tr.setId(6);
	chib.insertORAC<Test>(tr);
	tec.clear();
	Test *tp = new Test;
	tp->setId(7);
	tec.push_back(*tp);
	tp = new Test;
	tp->setId(8);
	tec.push_back(*tp);
	chib.bulkInsertRAC<Test>(tec);
	cols.erase(cols.begin()+1);
	string ns = "";
	Object on;
	on << ns;
	chib.addParam("name",on);
	//chib.getARSCW<Test>(cols);
	//chib.getARSC<Test>(cols);
	tp->setName("kriss");
	id1 = 8;
	oi << id1;
	chib.addParam("id",oi);
	//chib.updateRsAC<Test>(*tp);
	tim.end();
	cout << "\ndone" << flush;
	return 1;
}

```