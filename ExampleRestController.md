# `DefaultRestController.h` #
```
#ifndef DEFAULTRESTCONTROLLER_H_
#define DEFAULTRESTCONTROLLER_H_

#include "RestController.h"
#include <math.h>
#include <iostream>
#include "vector"
#include "TestMany.h"

class DefaultRestController: public RestController {
public:
	DefaultRestController();
	virtual ~DefaultRestController();
	void addNumbers(int,int);
	void power(int,int);
	void testVector(vector<int>);
	void testObject(TestMany);
	void testVectorObject(vector<TestMany> param);
	void testUploadFile(ifstream* ifs, string param);
	void testUploadFileMulti1(ifstream* ifs1, ifstream* ifs2, ifstream* ifs3, string param);
	void testUploadFileMulti2(vector<ifstream*> vifs, string param);
};

#endif /* DEFAULTRESTCONTROLLER_H_ */
```


# `DefaultRestController.cpp` #
```
#include "DefaultRestController.h"

DefaultRestController::DefaultRestController() {
	// TODO Auto-generated constructor stub

}

DefaultRestController::~DefaultRestController() {
	// TODO Auto-generated destructor stub
}

void DefaultRestController::addNumbers(int a, int b)
{
	int c = a + b;
	response->setHTTPResponseStatus(HTTPResponseStatus::Ok);
	response->setContent_type(ContentTypes::CONTENT_TYPE_TEXT_PLAIN);
	response->setContent_str(CastUtil::lexical_cast<string>(a) + " + " + CastUtil::lexical_cast<string>(b) + " = " +
			CastUtil::lexical_cast<string>(c));
	cout << "Processed input request inside DefaultRestController..." << endl;
}

void DefaultRestController::power(int base, int exponent)
{
	int c = pow((double)base, (double)exponent);
	response->setHTTPResponseStatus(HTTPResponseStatus::Ok);
	response->setContent_type(ContentTypes::CONTENT_TYPE_TEXT_PLAIN);
	response->setContent_str(CastUtil::lexical_cast<string>(base) + " ^ " + CastUtil::lexical_cast<string>(exponent) + " = " +
			CastUtil::lexical_cast<string>(c));
	cout << "Processed input request inside DefaultRestController..." << endl;
}

void DefaultRestController::testVector(vector<int> param)
{
	string temvec = "vector[";
	for (int var = 0; var < param.size(); ++var) {
		temvec += CastUtil::lexical_cast<string>(param.at(var));
		if(var!=param.size()-1)
			temvec += ",";
	}
	temvec += "]";
	response->setHTTPResponseStatus(HTTPResponseStatus::Ok);
	response->setContent_type(ContentTypes::CONTENT_TYPE_TEXT_PLAIN);
	response->setContent_str(temvec);
	cout << "Processed input request inside DefaultRestController..." << endl;
}

void DefaultRestController::testObject(TestMany testMany)
{
	buildResponse(HTTPResponseStatus::Ok, "TestMany", &testMany);
	cout << "Processed input request inside DefaultRestController..." << endl;
}


void DefaultRestController::testVectorObject(vector<TestMany> param)
{
	buildResponseVector(HTTPResponseStatus::Ok, "TestMany", &param);
	cout << "Processed input request inside DefaultRestController..." << endl;
}
}

void DefaultRestController::testUploadFile(ifstream* ifs, string param)
{
	string vals;
	unsigned int siz = 0;
	if (ifs!=NULL && ifs->is_open())
	{
		ifs->seekg(0, ios::end);
		siz = ifs->tellg();
	}
	vals = "Uploaded File Size = " + CastUtil::lexical_cast<string>(siz);
	vals += "\nField value passed = " + param;

	response->setHTTPResponseStatus(HTTPResponseStatus::Ok);
	response->addHeaderValue(HttpResponse::ContentType, ContentTypes::CONTENT_TYPE_TEXT_PLAIN);
	response->setContent(vals);
	cout << "Processed input request inside DefaultRestController for testUploadFile..." + response->generateResponse() << endl;
}

void DefaultRestController::testUploadFileMulti1(ifstream* ifs1, ifstream* ifs2, ifstream* ifs3, string param)
{
	string vals;
	unsigned int siz = 0;
	if (ifs1!=NULL && ifs1->is_open())
	{
		ifs1->seekg(0, ios::end);
		siz = ifs1->tellg();
	}
	vals = "Uploaded File1 Size = " + CastUtil::lexical_cast<string>(siz);
	siz = 0;
	if (ifs2!=NULL && ifs2->is_open())
	{
		ifs2->seekg(0, ios::end);
		siz = ifs2->tellg();
	}
	vals += "\nUploaded File2 Size = " + CastUtil::lexical_cast<string>(siz);
	siz = 0;
	if (ifs3!=NULL && ifs3->is_open())
	{
		ifs3->seekg(0, ios::end);
		siz = ifs3->tellg();
	}
	vals += "\nUploaded File3 Size = " + CastUtil::lexical_cast<string>(siz);
	vals += "\nField value passed = " + param;

	response->setHTTPResponseStatus(HTTPResponseStatus::Ok);
	response->addHeaderValue(HttpResponse::ContentType, ContentTypes::CONTENT_TYPE_TEXT_PLAIN);
	response->setContent(vals);
	cout << "Processed input request inside DefaultRestController for testUploadFileMulti1..." + response->generateResponse() << endl;
}

void DefaultRestController::testUploadFileMulti2(vector<ifstream*> vifs, string param)
{
	string vals;
	for(int i=0;i<(int)vifs.size();++i) {
		ifstream* ifs = vifs.at(i);
		unsigned int siz = 0;
		if (ifs!=NULL && ifs->is_open())
		{
			ifs->seekg(0, ios::end);
			siz = ifs->tellg();
		}
		vals += "Uploaded File" + CastUtil::lexical_cast<string>(i) + " Size = " + CastUtil::lexical_cast<string>(siz) + "\n";
	}
	vals += "Field value passed = " + param;

	response->setHTTPResponseStatus(HTTPResponseStatus::Ok);
	response->addHeaderValue(HttpResponse::ContentType, ContentTypes::CONTENT_TYPE_TEXT_PLAIN);
	response->setContent(vals);
	cout << "Processed input request inside DefaultRestController for testUploadFileMulti2..." + response->generateResponse() << endl;
}
```


# Config for rest service in `application.xml` #
```
<restcontrollers>
		<restcontroller class="DefaultRestController" urlpath="/rest/path/" name="rest1">
			<restfunction name="addNumbers" alias="add/{1}/{2}" meth="GET">
				<param type="int" name="1" from="path"/>
				<param type="int" name="2" from="path"/>
			</restfunction>
		</restcontroller>
		<restcontroller class="DefaultRestController" urlpath="/rest/reqparam/" name="rest1">
			<restfunction name="addNumbers" alias="add" meth="GET">
				<param type="int" name="1" from="reqparam"/>
				<param type="int" name="2" from="reqparam"/>
			</restfunction>
		</restcontroller>
		<restcontroller class="DefaultRestController" urlpath="/rest/postparam/" name="rest1">
			<restfunction name="addNumbers" alias="add" meth="POST">
				<param type="int" name="1" from="postparam"/>
				<param type="int" name="2" from="postparam"/>
			</restfunction>
		</restcontroller>
		<restcontroller class="DefaultRestController" urlpath="/rest/header/" name="rest1">
			<restfunction name="addNumbers" alias="add" meth="GET">
				<param type="int" name="1" from="header"/>
				<param type="int" name="2" from="header"/>
			</restfunction>
		</restcontroller>
		<restcontroller class="DefaultRestController" urlpath="/rest/path1/" name="rest2">
			<restfunction name="addNumbers" alias="+/{1}/{2}" meth="GET">
				<param type="int" name="1" from="path"/>
				<param type="int" name="2" from="path"/>
			</restfunction>
		</restcontroller>
		<restcontroller class="DefaultRestController" name="rest3">
			<restfunction name="addNumbers" alias="ad/{1}/{2}" meth="GET">
				<param type="int" name="1" from="path"/>
				<param type="int" name="2" from="path"/>
			</restfunction>
		</restcontroller>
		<restcontroller class="DefaultRestController">
			<restfunction name="power" meth="GET" baseUrl="/rest/controller/base{1}/power/exp{2}">
				<param type="int" name="1" from="path"/>
				<param type="int" name="2" from="path"/>
			</restfunction>
		</restcontroller>
		<restcontroller class="DefaultRestController">
			<restfunction name="addNumbers" meth="GET" alias="addNumbers/{1}/{2}">
				<param type="int" name="1" from="path"/>
				<param type="int" name="2" from="path"/>
			</restfunction>
		</restcontroller>
		<restcontroller class="DefaultRestController" name="restvec">
			<restfunction name="testVector" alias="tstvec" meth="POST">
				<param type="vector-of-int" from="body"/>
			</restfunction>
		</restcontroller>
		<restcontroller class="DefaultRestController" name="restvecobj">
			<restfunction name="testVectorObject" alias="tstvecobj" meth="POST" icontentType="application/json">
				<param type="vector-of-TestMany" from="body"/>
			</restfunction>
		</restcontroller>
		<restcontroller class="DefaultRestController" name="restobj">
			<restfunction name="testObject" alias="tstobj" meth="POST" icontentType="application/json" ocontentType="application/json">
				<param type="TestMany" from="body"/>
			</restfunction>
		</restcontroller>
		<restcontroller class="DefaultRestController" name="restvecobj">
			<restfunction name="testVectorObject" alias="tstvecobj.xml" meth="POST" icontentType="application/xml">
				<param type="vector-of-TestMany" from="body"/>
			</restfunction>
		</restcontroller>
		<restcontroller class="DefaultRestController" name="restobj">
			<restfunction name="testObject" alias="tstobj.xml" meth="POST" icontentType="application/xml">
				<param type="TestMany" from="body"/>
			</restfunction>
		</restcontroller>
		<restcontroller class="DefaultRestController" name="restupload">
			<restfunction name="testUploadFile" alias="uploadFile" meth="POST" icontentType="multipart/form-data">
				<param type="filestream" name="file" from="multipart-content"/>
				<param type="string" name="field" from="multipart-content"/>
			</restfunction>
		</restcontroller>
		<restcontroller class="DefaultRestController" name="restupload">
			<restfunction name="testUploadFileMulti1" alias="uploadFileMulti1" meth="POST" icontentType="multipart/form-data">
				<param type="filestream" name="file1" from="multipart-content"/>
				<param type="filestream" name="file2" from="multipart-content"/>
				<param type="filestream" name="file3" from="multipart-content"/>
				<param type="string" name="field" from="multipart-content"/>
			</restfunction>
		</restcontroller>
		<restcontroller class="DefaultRestController" name="restupload">
			<restfunction name="testUploadFileMulti2" alias="uploadFileMulti2" meth="POST" icontentType="multipart/form-data">
				<param type="vector-of-filestream" name="files" from="multipart-content"/>
				<param type="string" name="field" from="multipart-content"/>
			</restfunction>
		</restcontroller>
	</restcontrollers>
```