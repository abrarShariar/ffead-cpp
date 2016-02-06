# ACCEPTANCE TEST FRAMEWORK #
<font size='3' face='Georgia, Arial'>
<ul><li>Since version 1.7 an acceptance testing framework has been provided that can be used to validate the ffead-server installation or can be used to create acceptance tests for any rest full applications.<br>
</li><li>The tests folder inside the /ffead-server/ folder houses the code and related files.<br>
</li><li>test.csv has all the test cases that need to be executed providing endpoint details and validation details like expected content-length, request parameters etc<br>
</li><li>testValues.prop provides all the configuration parameters like server ip, port, ssl enabled etc. Moreover it also has the request content body for the requests present in the test.csv file<br>
</font></li></ul>


# `test.csv` #
```
ENABLED = is this test enabled
SHOW_CONTENT = display content on console
REQUEST = the HTTP method followed by the request URL
RESP_STATUS = the response status code
MATCH_FILE = validate the response content length against this file's size
RESP_CONT_LEN = if no matching file is provided then the content length to validate against the response content length
REQ_CONT_TYPE = the request content type
REQ_CONTENT = the request body or a property key that has a value inside testValues.prop file
HEADERS = the header parameters to set in format like header_p1=value1;header_p2=value2
RESP_CONT_TYPE = the response content to validate against


ENABLED,SHOW_CONTENT,REQUEST,RESP_STATUS,MATCH_FILE,RESP_CONT_LEN,REQ_CONT_TYPE,REQ_CONTENT,HEADERS,RESP_CONT_TYPE
Y,N,GET /,200,../web/default/index.html,
Y,N,GET /index.yourext,200,../web/default/index.html,
Y,N,GET /flexApp/,200,../web/flexApp/index.html,
Y,N,GET /oauthApp/,200,../web/oauthApp/index.html,
Y,N,GET /indexmain.html,200,../web/default/indexmain.html,
Y,N,GET /test.tpe,200,,110
Y,N,GET /test.view,200,,138
Y,N,GET /test.dcp,200,,194
Y,N,GET /Testing.wsdl,200,,5880
Y,N,GET /bg.jpg,200,../web/default/bg.jpg,
Y,N,GET /login.html,200,../web/default/login.html,
Y,N,POST /login.html,307,,,application/x-www-form-urlencoded,_ffead_security_cntxt_username=sumeet&_ffead_security_cntxt_password=sumeet
Y,Y,GET /test.form?txtField=asd&numField=123&selField=1,200,,4
Y,Y,GET /rest/path/rest1/add/1/2,200,,9
Y,Y,GET /rest/reqparam/rest1/add?1=1&2=2,200,,9
Y,Y,GET /rest/header/rest1/add,200,,9,,,1=1;2=2
Y,Y,POST /rest/postparam/rest1/add,200,,9,application/x-www-form-urlencoded,1=1&2=2
Y,Y,GET /rest/controller/base1/power/exp2,200,,9
Y,Y,POST /restvec/tstvec,200,,17,,TSTVALUES_POSTRSTVEC_VALUES
Y,Y,POST /restobj/tstobj,200,,323,application/json,TSTVALUES_POSTJSONOBJ_VALUES
Y,Y,POST /restvecobj/tstvecobj,200,,272,application/json,TSTVALUES_POSTJSONVECOBJ_VALUES,,application/json
Y,Y,POST /restobj/tstobj.xml,200,,164,application/xml,TSTVALUES_POSTXMLOBJ_VALUES,,application/json
Y,Y,POST /restvecobj/tstvecobj.xml,200,,166,application/xml,TSTVALUES_POSTXMLVECOBJ_VALUES,,application/json
Y,N,POST /restvecobj/tstvecobj,415,,,application/xml,TSTVALUES_POSTJSONVECOBJ_VALUES,,
Y,N,GET /restvecobj/tstvecobj,405,,,,
Y,Y,POST /default,200,,,application/x-www-form-urlencoded,TSTVALUES_POSTAFCTST_VALUES
Y,Y,POST /Testing,200,,,application/soap+xml,TSTVALUES_POSTSOAP_VALUES
Y,Y,GET /flexApp/getJSON.json,200,,,,

```


# `testValues.prop` #
```

SERVER_IP_ADDRESS=
SERVER_PORT=
SERVER_SSL_ENABLED=false
TSTVALUES_POSTRSTVEC_VALUES=[1,2,3,4,5]
TSTVALUES_POSTJSONOBJ_VALUES={     "t": {         "id": "1",         "name": "test"     },     "y": "2",     "vi": [1,2,3,4,5],     "vs": ["a","b","c",""],     "vd": [1.2,2.3,4.5,6],     "vl": [2147483647,123,12345],     "vyo": [     	{         	"i": 123,             "j": "string",             "c": 1.2345         },         {         	"i": 124,             "j": "string1",             "c": 1.2346         },         {         	"i": 124,             "j": "string1",             "c": 1.2346         }     ] }
TSTVALUES_POSTJSONVECOBJ_VALUES=[{     "t": {         "id": "1",         "name": "test"     },     "y": "2",     "vi": [1,2,3,4,5],     "vs": ["a","b","c",""],     "vd": [1.2,2.3,4.5,6],     "vl": [2147483647,123,12345],     "vyo": [     	{         	"i": 123,             "j": "string",             "c": 1.2345         },         {         	"i": 124,             "j": "string1",             "c": 1.2346         },         {         	"i": 124,             "j": "string1",             "c": 1.2346         }     ] }]
TSTVALUES_POSTXMLOBJ_VALUES=<TestMany>   <t type="Test">   	<Test>       <id type="int">2</id>       <name type="string">asdsa</name>     </Test>   </t>   <y type="int">6</y>   <vi type="vector-int">     <vector-int>       <int>0</int>       <int>1</int>     </vector-int>     </vi>   <vd type="vector-double">     <vector-double>       <double>0.23</double>       <double>1.334</double>     </vector-double>     </vd>   <vs type="vector-string">     <vector-string>       <string>abc</string>       <string>def</string>     </vector-string>     </vs>   <vl type="vector-long">     <vector-long>       <long>12345</long>       <long>67890</long>     </vector-long>     </vl>   <vyo type="vector-YObject">     <vector-YObject>       <YObject>         <i type="int">2</i>         <j type="string">asdsa</j>         <c type="float">36.78</c>       </YObject>      </vector-YObject>   </vyo> </TestMany>
TSTVALUES_POSTXMLVECOBJ_VALUES=<vector-TestMany>   <TestMany>     <t type="Test">       <Test>         <id type="int">2</id>         <name type="string">asdsa</name>       </Test>     </t>     <y type="int">6</y>     <vi type="vector-int">       <vector-int>         <int>0</int>         <int>1</int>       </vector-int>       </vi>     <vd type="vector-double">       <vector-double>         <double>0.23</double>         <double>1.334</double>       </vector-double>       </vd>     <vs type="vector-string">       <vector-string>         <string>abc</string>         <string>def</string>       </vector-string>       </vs>     <vl type="vector-long">       <vector-long>         <long>12345</long>         <long>67890</long>       </vector-long>       </vl>     <vyo type="vector-YObject">       <vector-YObject>         <YObject>           <i type="int">2</i>           <j type="string">asdsa</j>           <c type="float">36.78</c>         </YObject>        </vector-YObject>     </vyo>   </TestMany> </vector-TestMany>
TSTVALUES_POSTAFCTST_VALUES=claz=Expose&method=sayHello2&paramsize=3&param_1={"i":1,"j":"adsasd","c":2.3}&param_2=2&param_3=3
TSTVALUES_POSTSOAP_VALUES=<?xml version="1.0"?><soap:Envelope xmlns:soap="http://www.w3.org/2001/12/soap-envelope" soap:encodingStyle="http://www.w3.org/2001/12/soap-encoding"><soap:Body xmlns:tns="http://www.example.org/stock"><tns:test4><arg0>IBM</arg0></tns:test4></soap:Body></soap:Envelope>
```