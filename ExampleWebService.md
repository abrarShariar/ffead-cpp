# `Testing.h` #
```
#ifndef Testing_H_
#define Testing_H_

class Testing {
public:
	Testing();
	virtual ~Testing();
	void test1(string);
	string test2();
	void test3(Test);
	Test test4(string);
};
#endif /* Testing_H_ */
```


# `Testing.cpp` #
```
#include "Testing.h"

Testing::Testing() {
	// TODO Auto-generated constructor stub

}

Testing::~Testing() {
	// TODO Auto-generated destructor stub
}

void Testing::test1(string in)
{
	cout << "in Webservice Req for test1 --\n" << in << flush;
}
string Testing::test2()
{
	cout << "in Webservice Req for test2 --\n" <<  flush;
	return "success";
}
void Testing::test3(Test t)
{
	cout << "in Webservice Req for test3 --\n" << t.getName() << flush;
}
Test Testing::test4(string in)
{
	Test g;
	g.setId(1);
	g.setName("Ffead-cpp");
	cout << "in Webservice Req for test4 --\n" << in << flush;
	return g;
}
```



# `TestingWS.h` #
```
#ifndef TESTINGWS_H_
#define TESTINGWS_H_
#include "string"
#include "vector"
#include "TestObject.h"
#include "TestObject1.h"
#include "iostream"
#include "CastUtil.h"
using namespace std;

namespace ws {
	namespace test {
		class TestingWS {
		public:
			TestingWS();
			virtual ~TestingWS();
			void wsmeth1(int a, string, long);
			string wsmeth2(string b, vector<int> c);
			TestObject wsmeth3(string);
			com::obj::TestObject wsmeth4(bool);
			string wsmeth5(TestObject);
			long wsmeth6(com::obj::TestObject);
		};
	}
} /* namespace ws */
#endif /* TESTINGWS_H_ */
```


# `Testing.cpp` #
```
#include "TestingWS.h"

namespace ws {
	namespace test {
		TestingWS::TestingWS() {
			// TODO Auto-generated constructor stub

		}

		TestingWS::~TestingWS() {
			// TODO Auto-generated destructor stub
		}

		void TestingWS::wsmeth1(int a, string b, long c) {
			cout << ("WS Method wsmeth1 called with args - " + CastUtil::lexical_cast<string>(a) + " " + b + " " + CastUtil::lexical_cast<string>(c)) << endl;
		}

		string TestingWS::wsmeth2(string b, vector<int> c) {
			string out(b + " ");
			for (int var = 0; var < (int)c.size(); ++var) {
				out.append(CastUtil::lexical_cast<string>(c.at(var)) + " ");
			}
			cout << ("WS Method wsmeth2 called with args - " + out) << endl;
			return out;
		}

		TestObject TestingWS::wsmeth3(string a) {
			TestObject obj;
			obj.setA(3);
			obj.setB(4);
			obj.setC(a);
			obj.setD(5.0);
			obj.setE(6.0);
			obj.setF(true);
			obj.setG(13);
			obj.setH(2);
			obj.setI(-2);
			obj.setJ(-3);
			obj.setK(-4);
			obj.setL(-13);
			cout << ("WS Method wsmeth3 called with args - " + obj.toString()) << endl;
			return obj;
		}

		com::obj::TestObject TestingWS::wsmeth4(bool bol) {
			com::obj::TestObject obj;
			vector<short> a;
			a.push_back(2);
			obj.setA(a);
			vector<int> b;
			b.push_back(3);
			obj.setB(b);
			vector<long> c;
			c.push_back(4);
			obj.setC(c);
			vector<long long> d;
			d.push_back(13);
			obj.setD(d);
			vector<unsigned short> e;
			e.push_back(-2);
			obj.setE(e);
			vector<unsigned int> f;
			f.push_back(-3);
			obj.setF(f);
			vector<unsigned long> g;
			g.push_back(-4);
			obj.setG(g);
			vector<unsigned long long> h;
			h.push_back(-13);
			obj.setH(h);
			vector<float> i;
			i.push_back(5.0);
			obj.setI(i);
			vector<double> j;
			j.push_back(6.0);
			obj.setJ(j);
			vector<bool> k;
			k.push_back(2);
			obj.setK(k);
			vector<string> l;
			l.push_back("string");
			obj.setL(l);
			cout << ("WS Method wsmeth4 called with args - " + obj.toString()) << endl;
			return obj;
		}

		string TestingWS::wsmeth5(TestObject obj) {
			cout << ("WS Method wsmeth5 called with args - " + obj.toString()) << endl;
			return obj.toString();
		}

		long TestingWS::wsmeth6(com::obj::TestObject obj) {
			cout << ("WS Method wsmeth6 called with args - " + obj.toString()) << endl;
			return 13;
		}
	}
} /* namespace ws */
```



# Config for web-service in ws.xml #
```
<web-services>
	<web-service location="testing" class="Testing" namespace="ws.testing.service">
		<test1 outname="result"/>
		<test2 outname="result"/>
		<test3 outname="result"/>
		<test4 outname="result"/>
	</web-service>
	<web-service location="testingWS" class="ws::test::TestingWS">
		<wsmeth1 outname="result"/>
		<wsmeth2 outname="result"/>
		<wsmeth3 outname="result"/>
		<wsmeth4 outname="result"/>
		<wsmeth5 outname="result"/>
		<wsmeth6 outname="result"/>
	</web-service>
</web-services>
```