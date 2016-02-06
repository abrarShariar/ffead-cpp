# Add new web application #
<font size='3' face='Georgia, Arial'>
<ul><li>Download the tar file and extract it to the location of your choice.<br>
</li><li>Visit the <a href='http://code.google.com/p/ffead-cpp/wiki/InstallationDirections'>Installation Directions</a> page for more information<br>
</li><li>Go the folder ffead-server-unix/Debug/ffead-server.<br>
</li><li>Create a new folder in ffead-server/web i.e, appname<br>
</li><li>Modify ffead-server/resources/ffead-server.prop to set the port, default application, number of server processes and other essential attributes <a href='http://code.google.com/p/ffead-cpp/wikiffead-serverProperties'>Server-Properties</a>
</li><li>Create ffead-server/resources/log.properties file to enable custom logging for the applications <a href='http://code.google.com/p/ffead-cpp/wiki/LoggerProperties'>Logger-Properties</a>
</li><li>Create new folders /lib /components /config /dcp /include under your newly created application folder (appname)<br>
<ul><li>ffead-server/web/appname<br>
<ol><li>/lib<br>
</li><li>/include<br>
</li><li>/dcp<br>
</li><li>/config<br>
</li><li>/components<br>
</li></ol></li></ul></li><li>Drop all your application level header files intended for Serialization and Reflection enabled support in the /appname/include folder. All files targeted for Web-Services, Ajax, Database mapping, Components, Controllers, Templates, Views etc should have their header definition files present in the /appname/include folder.<br>
</li><li>Drop the shared library of your application inside the /appname/lib folder.<br>
</li><li>Create/Drop your html/tpe files directly in the /appname folder <a href='http://code.google.com/p/ffead-cpp/wiki/ExampletpeFile'>Example-tpe-File</a>
</li><li>Create/Drop your dcp files in the /appname/dcp folder <a href='http://code.google.com/p/ffead-cpp/wiki/ExampledcpFile'>Example-dcp-File</a>
</li><li>Create /appname/config/cibernate.xml for ORM support <a href='http://code.google.com/p/ffead-cpp/wiki/CibernateConfig'>Cibernate-Configuration</a>
</li><li>Create /appname/config/application.xml for REST full services,Dynamic C++ pages,Templates and Dynamic view support <a href='http://code.google.com/p/ffead-cpp/wiki/ApplicationLevelConfig'>Application-Level-Configuration</a>
</li><li>Create /appname/config/afc.properties for Ajax Support <a href='http://code.google.com/p/ffead-cpp/wiki/AjaxConfig'>Ajax-Configuration</a>
</li><li>Create /appname/config/ws.xml for Web-Service Support <a href='http://code.google.com/p/ffead-cpp/wiki/WebServicesConfig'>Web-Services-Configuration</a>
</li><li>For Business Entities or Business Driven Beans create your custom <code>*</code>.cmp files and drop them inside the /appname/components folder <a href='http://code.google.com/p/ffead-cpp/wiki/ExampleComponent'>Example-Component</a>
</li><li>For Dependency Injection create a file named /appname/config/depInj.xml <a href='http://code.google.com/p/ffead-cpp/wiki/DependencyInjection'>Example depInj.xml</a>
</li><li>Create /appname/config/messaging.xml for Messaging support <a href='http://code.google.com/p/ffead-cpp/wiki/MessagingConfig'>Messaging-Configuration</a>
</li><li>Create a new HTML page named index.html and place it in your /appname folder<br>
</li><li>Restart the Web Server<br>
</li><li>Enter <a href='http://localhost:port/appname/'>http://localhost:port/appname/</a> and Watch the magic!!! </font>