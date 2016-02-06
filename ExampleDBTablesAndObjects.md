# `Person.h` #
```
#ifndef PERSON_H_
#define PERSON_H_
#include "string"
using namespace std;

class Person {
	int id;
        int age;
	string name;
public:
	Person();
	virtual ~Person();
        int getId() const;
        void setAge(int);
        int getAge() const;
        void setId(int);
        string getName() const;
        void setName(string);
        bool operator<(Person t) const;
};

#endif /* PERSON_H_ */

create table person (id int,int age,name varchar(255));
```


# `Life.h` #
```
#ifndef LIFE_H_
#define LIFE_H_
#include "string"
using namespace std;

class Life {
	int id;
	strin type,desc;
public:
	Life();
	virtual ~Life();
        int getId() const;
        void setId(int id);
        string getType() const;
        void setType(string);
        string getDesc() const;
        void setDesc(string);
};

#endif /* LIFE_H_ */

create table life (id int,desc varchar(255),type varchar(50));
```


# `Interest.h` #
```
#ifndef INTEREST_H_
#define INTEREST_H_
#include "string"
using namespace std;

class Interest {
	int id;
	strin type,desc;
public:
	Interest();
	virtual ~Interest();
        int getId() const;
        void setId(int id);
        string getType() const;
        void setType(string);
        string getDesc() const;
        void setDesc(string);
};

#endif /* INTEREST_H_ */

create table interest (id int,desc varchar(255),type varchar(50));
```


# `PersonInterest.h` #
```
#ifndef PERSONINTEREST_H_
#define PERSONINTEREST_H_
#include "string"
using namespace std;

class PersonInterest {
	int person_id;
        int interest_id;
public:
	PersonInterest();
	virtual ~PersonInterest();
        int getPersonId() const;
        void setPersonId(int personId);
        int getInterestId() const;
        void setInterestId(int interestId);
};

#endif /* PERSONINTEREST_H_ */

create table person_interest(person_id int,interest_id int);
```


# `Test.h` ##ifndef TEST_H_
#define TEST_H_
#include "string"
using namespace std;

class Test{
	int id;
        int age;
	string name;
public:
	Test();
	virtual ~Test();
        int getId() const;
        void setId(int);
        string getName() const;
        void setName(string);
        bool operator<(Test t) const;
};

#endif /* TEST_H_ */

create table test (id int,name varchar(255));



= {{{Test4.h}}} =
{{{
#ifndef TEST4_H_
#define TEST4_H_
#include "Date.h"
#include "BinaryData.h"

class Test4 {
	Date date;
	Date datt;
	Date dattm;
	BinaryData binar;
public:
	Test4();
	virtual ~Test4();
	Date getDate() const;
        void setDate(Date date);
        Date getDatt() const;
        void setDatt(Date datt);
        Date getDattm() const;
        void setDattm(Date dattm);
        BinaryData getBinar() const;
        void setBinar(BinaryData binar);
};
#endif /* TEST4_H_ */

create table test4 (date date,datt datetime,dattm timestamp,binar blob);
}}}```