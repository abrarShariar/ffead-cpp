# Installation On Windows with Cygwin #
<font size='3' face='Georgia, Arial'>
<ul><li>Download Cygwin setup.exe and follow instruction to install Cygwin, proceed with default settings.<br>
</li><li>After Cygwin is successfully installed, you can open a cygwin terminal to check whether Cygwin works.<br>
</li><li>Run the setup.exe to install further dependencies whenever required.<br>
</li><li>Following are the dependencies,<br>
<ol><li>gcc<br>
</li><li>g++<br>
</li><li>autoconf<br>
</li><li>automake<br>
</li><li>openssl libraries and devel (use Cygwin_SSL_UnixOdbc_libs.zip from downloads section for version 1.0)<br>
</li><li>unixODBC libraries and devel (not found in Cygwin reposistory, use Cygwin_SSL_UnixOdbc_libs.zip from download section)<br>
</li><li>bison,yacc,flex,gdb,readline,binutils (for building and installing openssl and unixODBC)<br>
</li></ol></li><li>Copy bin/gcc-3 or bin/gcc-4 and rename it ot gcc (the already existing link file gcc sometimes gives permission errors)<br>
</li><li>You can build and install openssl and unixodbc and copy the required library files to the cygwin lib folder. The already built libraries are present in the Cygwin_SSL_UnixOdbc_libs.zip file which can be copied to the lib folder directly.<br>
</li><li>Download the latest release tar file and extract it to the location of your choice under Cygwin installation.<br>
</li><li>Install <b>Unix-ODBC</b> and required odbc files for <b>MySQL</b> dependency<br>
</li><li>Install <b>Open-SSL</b> as well<br>
</li><li>Also included <b>prototype.js</b> in source for AJAX support<br>
</li><li>Go to the ffead-server/Release or ffead-server/Debug depending on whether you need to debug the server code<br>
</li><li>Open terminal and type "make all" and "make build-apps" to build the server and the default applications provided ("make all" will build ffead with all modules enabled)<br>
</li><li><b>From version 1.8 onwards you can also select modules to build within ffead using the make modules={comma separated module list} all command, for a complete list of modules names please refer <a href='http://code.google.com/p/ffead-cpp/wiki/Modules'>Modules</a>, for e.g, to only build modules webservice,binserialize and distocache use the command "make modules=webservice,binserialize,distocache all"</b>
</li><li>This will create the distribution folder named ffead-server inside ffead-server/Release or ffead-server/Debug folders accordingly<br>
</li><li>Type ./server.sh when inside the ffead-server/Release/ffead-server folder to start the application server<br>
</li><li>Go to the ffead-server/Release/ffead-server/tests folder and run ./runTests.sh, this will do an initial sanity of the capabilities of the framework and also validate the same<br>
</li><li>A default application is already provided for your reference inside the ffead-server/web folder, this application is served at urlpath /<br>
</li><li>2 other applications are provided, urlpath /flexApp and /oauthApp<br>
</li><li>To compile only the default application shared library go to the ffead-server/Release/ffead-server/web/default/src/Debug folder and run "make all"<br>
</li><li>Copy the libdefault library to the ffead-server/Release/ffead-server/lib folder<br>
</li><li>Place your application shared library inside the ffead-server/Release/ffead-server/lib or ffead-server/Debug/ffead-server/lib folder.<br>
</li><li>Place your web application specific files inside the ffead-server/Release/ffead-server/web folder inside a folder with your application name<br>
</font>