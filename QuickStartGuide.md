# Quick Start Guide #
<font size='3' face='Georgia, Arial'>
<blockquote>BINARY FILE<br>
</blockquote><ul><li>Download the ffead-server-{os}-bin-v{version}.zip file and extract it to the location of your choice.<br>
</li><li>Visit the <a href='http://code.google.com/p/ffead-cpp/wiki/InstallationDirections'>Installation Directions</a> page for more information<br>
</li><li>Go to the folder ffead-server.<br>
</li><li>Modify ffead-server/resources/server.prop to set the port, default application, number of server processes and other essential attributes <a href='http://code.google.com/p/ffead-cpp/wikiffead-serverProperties'>Server-Properties</a>
</li><li>Modify ffead-server/resources/log.properties file to enable custom logging for the applications <a href='http://code.google.com/p/ffead-cpp/wiki/LoggerProperties'>Logger-Properties</a>
</li><li>chmod 777 ffead-server/server.sh<br>
</li><li>Execute ./server.sh start the Web Server<br>
</li><li>Go to the ffead-server/tests folder and run ./runTests.sh, this will do an initial sanity of the capabilities of the framework and also validate the same<br>
</li><li>Enter <a href='http://localhost:port/index.html'>http://localhost:port/index.html</a> and Watch the magic!!!<br>
</li><li>A sample test page is provided at <a href='http://localhost:port/indexmain.html'>http://localhost:port/indexmain.html</a></li></ul>

<blockquote>SOURCE FILE<br>
</blockquote><ul><li>Download the ffead-server-v{version}.zip file and extract it to the location of your choice.<br>
</li><li>Visit the <a href='http://code.google.com/p/ffead-cpp/wiki/InstallationDirections'>Installation Directions</a> page for more information<br>
</li><li>Go the folder ffead-server/Debug or ffead-server/Release folder.<br>
</li><li>chmod 777 makeAll.sh<br>
</li><li>Execute the ./makeAll.sh file, it will compile and build the complete project and all required web applications<br>
</li><li>Go to the ffead-server/Debug/ffead-server or ffead-server/Release/ffead-server folder<br>
</li><li>Modify ffead-server/resources/server.prop to set the port, default application, number of server processes and other essential attributes <a href='http://code.google.com/p/ffead-cpp/wikiffead-serverProperties'>Server-Properties</a>
</li><li>Modify ffead-server/resources/logging.xml file to enable custom logging for the applications <a href='http://code.google.com/p/ffead-cpp/wiki/LoggerProperties'>Logger-Properties</a>
</li><li>chmod 777 ffead-server/server.sh<br>
</li><li>Execute ./server.sh start the Web Server<br>
</li><li>Go to the ffead-server/tests folder and run ./runTests.sh, this will do an initial sanity of the capabilities of the framework and also validate the same<br>
</li><li>Enter <a href='http://localhost:port/index.html'>http://localhost:port/index.html</a> and Watch the magic!!!<br>
</li><li>A sample test page is provided at <a href='http://localhost:port/indexmain.html'>http://localhost:port/indexmain.html</a>
</font>