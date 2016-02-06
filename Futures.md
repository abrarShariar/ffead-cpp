# `ThreadPoolTest.cpp` #
```
using namespace std;
#include "ThreadPool.h"
#include "CastUtil.h"

class myFuturetask : public FutureTask
{
	float j;
public:
	myFuturetask(float j){this->j = j;}
	~myFuturetask(){}
	void* call()
	{
		cout << "FutureTask run " << j << "\n"<< flush;
		return new string(toString());
	}
	string toString()
	{
		return ("FutureTask No "+CastUtil::lexical_cast<string>(j));
	}
};

void testDirectFutureTaskExecution()
{
	/*Declare a Thread Pool with Min 2 and Max 5 Threads*/
	ThreadPool pool(1,5,true);
	pool.start();
	/*Create a Task*/
	myFuturetask*task1 = new myFuturetask(1);
	myFuturetask task2(2);
	myFuturetask task3(3);
	myFuturetask task4(4);
	myFuturetask task5(5);
	/*Execute The Task*/
	pool.submit(*task1);
	cout << *(string*)task1->getResult() << endl;
	cout << "add done" << endl;
	pool.submit(task2);
	pool.submit(task3);
	pool.submit(task4);
	pool.submit(task5);
	cout << *(string*)task5.getResult() << endl;
	cout << *(string*)task4.getResult() << endl;
	cout << *(string*)task3.getResult() << endl;
	cout << *(string*)task2.getResult() << endl;
	/*Wait for completion of all Tasks*/
	pool.joinAll();
}



int main()
{
	/*Test the Futures based Direct Thread Pooling mechanism*/
	testDirectFutureTaskExecution();
	return 0;
}
```