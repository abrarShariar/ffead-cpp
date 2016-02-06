# Example Dynamic C++ Page #
```
<DCPH>
#include "string"
#include <iostream>
using namespace std;
</DCPH>
<html>
<head>
</head>
<body>
<input type="text"/>
lsdflsdkfjsdlflk
<DCPB>
string h;
h = "Hello World!!";
</DCPB>
<import>/home/sumeet/server/web/default/dcp/testheader.dcp</import>
<input type="submit"/>
<input type="text"/>

<DCPB>
//Goes to the server console
cout << h << flush;
</DCPB>

<DCPB>
for(int i=0;i<10;i++)
{
</DCPB>
<input type="text"/>
<DCPB>
}
</DCPB>
<DCPF>
void printscrn()
{
        //Goes to the server console
	cout << "Hello World from function!!" << flush;
}
</DCPF>

</body>
</html>

```