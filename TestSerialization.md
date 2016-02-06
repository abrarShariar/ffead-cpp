
```
#include <iostream>
#include "string"
#include "TestMany.h"
#include "TestForm.h"
#include "TestSTLs.h"
#include "BinarySerialize.h"
#include "XMLSerialize.h"
#include "JSONSerialize.h"

using namespace std;

int main() {

	TestMany tm;
	tm.t.setId(1);
	tm.t.setName("test");

	tm.y = 2;

	tm.vd.push_back(0.1);
	tm.vd.push_back(1.1);
	tm.vd.push_back(2.1);
	tm.vd.push_back(3.1);
	tm.vd.push_back(4.1);

	tm.vi.push_back(0);
	tm.vi.push_back(1);
	tm.vi.push_back(2);
	tm.vi.push_back(3);
	tm.vi.push_back(4);

	tm.vl.push_back(0);
	tm.vl.push_back(1);
	tm.vl.push_back(2);
	tm.vl.push_back(3);
	tm.vl.push_back(4);

	tm.vs.push_back("1");
	tm.vs.push_back("2");
	tm.vs.push_back("3");
	tm.vs.push_back("4");
	tm.vs.push_back("5");

	YObject yo;
	yo.i = 1;
	yo.j = "1";
	yo.c = 1.1;
	tm.vyo.push_back(yo);
	yo.i = 2;
	yo.j = "2";
	yo.c = 1.2;
	tm.vyo.push_back(yo);

	BinarySerialize ser;
	string binstr = ser.serialize<TestMany>(tm);

	TestMany tmn = ser.unserialize<TestMany>(binstr);
	cout << tmn.vi.size()<<tmn.vl.size()<<tmn.vd.size()<<tmn.vs.size()<<tmn.vyo.size()<<tmn.t.getId()<<tmn.t.getName()<<tm.y << endl;

	binstr = ser.serializeUnknown(&tm, "TestMany");
	TestMany* tmp = (TestMany*)ser.unSerializeUnknown(binstr, "TestMany");
	tmn = *tmp;
	cout << tmn.vi.size()<<tmn.vl.size()<<tmn.vd.size()<<tmn.vs.size()<<tmn.vyo.size()<<tmn.t.getId()<<tmn.t.getName()<<tm.y << endl;

	XMLSerialize xser;
	binstr = xser.serialize<TestMany>(tm);

	tmn = xser.unserialize<TestMany>(binstr);
	cout << tmn.vi.size()<<tmn.vl.size()<<tmn.vd.size()<<tmn.vs.size()<<tmn.vyo.size()<<tmn.t.getId()<<tmn.t.getName()<<tm.y << endl;

	binstr = xser.serializeUnknown(&tm, "TestMany");
	tmp = (TestMany*)xser.unSerializeUnknown(binstr, "TestMany");
	tmn = *tmp;
	cout << tmn.vi.size()<<tmn.vl.size()<<tmn.vd.size()<<tmn.vs.size()<<tmn.vyo.size()<<tmn.t.getId()<<tmn.t.getName()<<tm.y << endl;

	JSONSerialize jser;
	binstr = jser.serialize<TestMany>(tm);

	tmn = jser.unserialize<TestMany>(binstr);
	cout << tmn.vi.size()<<tmn.vl.size()<<tmn.vd.size()<<tmn.vs.size()<<tmn.vyo.size()<<tmn.t.getId()<<tmn.t.getName()<<tm.y << endl;

	binstr = jser.serializeUnknown(&tm, "TestMany");
	tmp = (TestMany*)jser.unSerializeUnknown(binstr, "TestMany");
	tmn = *tmp;
	cout << tmn.vi.size()<<tmn.vl.size()<<tmn.vd.size()<<tmn.vs.size()<<tmn.vyo.size()<<tmn.t.getId()<<tmn.t.getName()<<tm.y << endl;


	TestSTLs stls;
	stls.vli.push_back(1);
	stls.vlsh.push_back(1);
	stls.vll.push_back(1);
	stls.vld.push_back(1.1);
	stls.vlb.push_back(true);
	stls.vls.push_back("1");
	stls.vlyo.push_back(yo);

	stls.vvi.push_back(1);
	stls.vvsh.push_back(1);
	stls.vvl.push_back(1);
	stls.vvd.push_back(1.1);
	stls.vvb.push_back(true);
	stls.vvs.push_back("1");
	stls.vvyo.push_back(yo);

	Test tst;
	tst.setId(1);
	tst.setName("1");

	stls.vsi.insert(1);
	stls.vssh.insert(1);
	stls.vsl.insert(1);
	stls.vsd.insert(1.1);
	stls.vss.insert("1");
	stls.vsyo.insert(tst);

	stls.vmsi.insert(1);
	stls.vmssh.insert(1);
	stls.vmsl.insert(1);
	stls.vmsd.insert(1.1);
	stls.vmss.insert("1");
	stls.vmsyo.insert(tst);

	stls.vdi.push_back(1);
	stls.vdsh.push_back(1);
	stls.vdl.push_back(1);
	stls.vdd.push_back(1.1);
	stls.vdb.push_back(true);
	stls.vds.push_back("1");
	stls.vdyo.push_back(yo);

	stls.vqi.push(1);
	stls.vqsh.push(1);
	stls.vql.push(1);
	stls.vqd.push(1.1);
	stls.vqb.push(true);
	stls.vqs.push("1");
	stls.vqyo.push(yo);

	stls.vpppli = new list<int>;
	stls.vpppli->push_back(1);

	binstr = ser.serialize<TestSTLs>(stls);
	cout << stls.toString() << endl;

	TestSTLs stlsn = ser.unserialize<TestSTLs>(binstr);
	cout << stlsn.toString() << endl;

	binstr = xser.serialize<TestSTLs>(stls);
	cout << stlsn.toString() << endl;

	stlsn = xser.unserialize<TestSTLs>(binstr);
	cout << stlsn.toString() << endl;

	binstr = jser.serialize<TestSTLs>(stls);
	cout << stlsn.toString() << endl;

	stlsn = jser.unserialize<TestSTLs>(binstr);
	cout << stlsn.toString() << endl;
}

```