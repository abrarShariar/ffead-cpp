# FreeBSD based Installation #
<font size='3' face='Georgia, Arial'>
<ul><li>Follow <a href='http://code.google.com/p/ffead-cpp/wiki/WindowsCygwinInstallationDirections'><b>Windows/Cygwin Install</b></a> for directions on how to install on Windows and Cygwin<br>
</li><li>Download the tar file and extract it to the location of your choice.<br>
</li><li>Install <b>Unix-ODBC</b> and required odbc files for <b>MySQL</b> dependency<br>
</li><li>Install <b>Open-SSL</b> as well<br>
</li><li>Also included <b>prototype.js</b> in source for AJAX support<br>
</li><li>Go to the ffead-server-freebsd/Release or ffead-server-freebsd/Debug depending on whether you need to debug the server code<br>
</li><li>Open terminal and type "gmake all" and "gmake build-apps" to build the server and the default applications provided ("gmake all" will build ffead with all modules enabled)<br>
</li><li><b>From version 1.8 onwards you can also select modules to build within ffead using the gmake modules={comma separated module list} all command, for a complete list of modules names please refer <a href='http://code.google.com/p/ffead-cpp/wiki/Modules'>Modules</a>, for e.g, to only build modules webservice,binserialize and distocache use the command "gmake modules=webservice,binserialize,distocache all"</b>
</li><li>This will create the distribution folder named ffead-server inside ffead-server/Release or ffead-server/Debug folders accordingly<br>
</li><li>Type ./server.sh when inside the ffead-server/Release/ffead-server folder to start the application server<br>
</li><li>Go to the ffead-server/Release/ffead-server/tests folder and run ./runTests.sh, this will do an initial sanity of the capabilities of the framework and also validate the same<br>
</li><li>A default application is already provided for your reference inside the ffead-server/web folder, this application is served at urlpath /<br>
</li><li>2 other applications are provided, urlpath /flexApp and /oauthApp<br>
</li><li>To compile the default application shared library go to the ffead-server/Release/ffead-server/web/default/src/Debug folder and run "gmake all"<br>
</li><li>Copy the libdefault library to the ffead-server/Release/ffead-server/lib folder<br>
</li><li>Place your application shared library inside the ffead-server/Release/ffead-server/lib or ffead-server/Debug/ffead-server/lib folder.<br>
</li><li>Place your web application specific files inside the ffead-server/Release/ffead-server/web folder inside a folder with your application name<br>
</li><li>Remember all installation files(makefile,subdir.mk) assume the ports are installed to the /usr/local/lib directory, in case you choose custom settings during installation of dependencies then make sure to change all files to include the -L/usr/local/lib to -L/location/of your/choice<br>
</font>