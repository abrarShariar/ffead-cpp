# `ThreadPoolTest.cpp` #
```
using namespace std;
#include "ThreadPool.h"
#include "CastUtil.h"

class MyTask : public Task
{
	float j;
public:
	MyTask(float j){this->j = j;}
	~MyTask(){}
	void run()
	{
		cout << "Task run " << j << "\n"<< flush;
	}
	string toString()
	{
		return ("Task No "+CastUtil::lexical_cast<string>(j));
	}
};

void testDirectExecution()
{
	/*Declare a Thread Pool with Min 2 and Max 5 Threads*/
	ThreadPool pool(2,5,true);
	/*Create a Task*/
	mytask task1(1);
	mytask task2(2);
	mytask task3(3);
	mytask task4(4);
	mytask task5(5);
	/*Execute The Task*/
	pool.execute(task1);
	pool.execute(task2);
	pool.execute(task3);
	pool.execute(task4);
	pool.execute(task5);
	/*Wait for completion of all Tasks*/
	pool.joinAll();
}

void testPrioritizedExecution()
{
	/*Declare a Thread Pool with Min 2 and Max 5 Threads, with Low 1 and 4 High Priority*/
	ThreadPool pool(2,5,1,4,true);
	/*Create a Task*/
	mytask task1(1);
	mytask task2(2);
	mytask task3(3);
	mytask task4(4);
	mytask task5(5);
	/*Execute The Tasks on priority*/
	pool.execute(task1,2);
	pool.execute(task2,4);
	pool.execute(task3,4);
	pool.execute(task4,1);
	pool.execute(task5,4);
	/*Wait for completion of all Tasks*/
	pool.joinAll();
}

void testScheduledExecution()
{
	/*Declare a Thread Pool with Min 2 and Max 5 Threads*/
	ThreadPool pool(2,5,true);
	/*Create a Task*/
	mytask task1(1);
	mytask task2(2);
	mytask task3(3);
	mytask task4(4);
	mytask task5(5);
	/*Schedule a task to be executed after the defined delay period*/
	pool.schedule(task1,10,TimeUnit::MILLISECONDS);
	pool.schedule(task2,10,TimeUnit::SECONDS);
	pool.schedule(task3,1,TimeUnit::HOURS);
	pool.schedule(task4,10,TimeUnit::DAYS);
	pool.schedule(task5,110,TimeUnit::MILLISECONDS);
	/*Wait for completion of all Tasks*/
	pool.joinAll();
}

void testDirectScheduledExecution()
{
	/*Declare a Thread Pool with Min 2 and Max 5 Threads*/
	ThreadPool pool(2,5,true);
	mytask task1(1);
	mytask task2(2);
	mytask task3(3);
	mytask task4(4);
	mytask task5(5);
	/*Schedule a task to be executed after the defined delay period*/
	pool.schedule(task1,10,TimeUnit::MILLISECONDS);
	pool.schedule(task2,10,TimeUnit::SECONDS);
	/*Execute the task*/
	pool.execute(task3);
	pool.schedule(task4,10,TimeUnit::DAYS);
	pool.execute(task5);
	/*Wait for completion of all Tasks*/
	pool.joinAll();
}


int main()
{
	/*Test the Direct Thread Pooling mechanism*/
	testDirectExecution();
	/*Test the Scheduled Thread Pooling mechanism*/
	testScheduledExecution();
	/*Test the Priority Driven Thread Pooling mechanism*/
	testPrioritizedExecution();
	/*Test the Mixed Thread Pooling mechanism*/
	testDirectScheduledExecution();
	return 0;
}
```