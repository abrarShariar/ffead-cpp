## Binary Downloads ##
Starting from v1.9, all downloads are actively maintained at https://github.com/sumeetchhetri/ffead-cpp, for all release downloads visit https://github.com/sumeetchhetri/ffead-cpp/releases. All downloads will now be maintained at github as goodle code has stopped allowing downloads on the project site.

## Testing Frameworks ##
You can use the [GATF](https://github.com/sumeetchhetri/gatf) framework for API test executions of all you REST/SOAP endpoints.


## Release Notes version 1.9 ##
  * Fix for the socket select issue (when number of connections increases 64)
  * Added support for autotools build system
  * The intermediate libraries (libinter/libdinter) can also be built at run-time using ./configure/make

## Release Notes version 1.8 ##
  * CORS Filter support for corss origin resource sharing
  * Changes to XML/JSON/Binary Serialization
  * Moved common code to a new SerializeBase class
  * Modified the AMEF Protocol classes for better binary serialization support
  * Added support for handling namespaces and nested classes in Reflection
  * Fixed the Date/DateFormat classes for all issues related to parsing/formatting/updating dates
  * Added new Multipartcontent object for handling multipart requests
  * Added gzip/deflate compression for responses
  * Added chunked transfer encoding support
  * Added Last Modified/If-Modified-Since header based cache support
  * Moved request/response headers to a map instead of properties
  * Fixed the HttpResponseParser class
  * Fixed the JSONUtil class for error in json parsing
  * Introduced a new LoggerFactory class to handle multiple loggers, fixed the Logger class
  * Introduced Futures based Thread pooling support
  * Fixed various web service issues/problems
  * Introduced JobScheduler class for job scheduling
  * Added a new CronTimer class for handling cron times
  * Introduced stream based single/multi File upload support in Rest Controllers
  * Added a few new html pages for testing/sanity
  * Fixed the accpetance test related files
  * Added a couple of new classes in the default app for testing new features
  * Fixed the afc.js file to resolve existing issues
  * Fixed an existing issue with namespace handling within the Element class
  * Introduced new properties for connection keep-alive, transfer encoding chunk size, default content encoding method, max number of input headers and max file upload size to the server.prop config file
  * Changed the web-service related template files for better web service support


## Introduction ##
<font size='3' face='Georgia, Arial'>
The framework is developed for rapid development of Enterprise application on the C++ platform. It is a c++ web framework, c++ application framework, c++ rest framework, c++ security framework and c++ soap framework all bundled into one.<br>
It consists of the following and is currently implemented for <b>LINUX/FREEBSD/WINDOWS(Cygwin)/SOLARIS</b>.<br>
It is the <b>first and only</b> C++ Application framework to provide <b>non-intrusive Dependency Injection and Business Driven Component Logic and POCO based Development</b>.<br>
Most of the features are controlled by configuration files.<br>
</font>
## Features ##
<font size='3' face='Georgia, Arial'>
<ul><li>Easy to use <b>View Framework</b>
</li><li><b>SSL Support</b> available<br>
</li><li><b>Web Server</b> (Multi process, Multi Threaded – EPOLL based)<br>
</li><li>Inbuilt Authentication handlers and <b>OAUTH</b> support<br>
</li><li>Configuration driven URL mapping<br>
</li><li><b>Dependency Injection</b> (constructor and setter injection)<br>
</li><li><b>ORM</b> library (currently implemented for MySQL, Integrated with STL, Table mappings through configuration files –> One – Many, Many – Many ,One – One. The ORM Can be easily extended to other Databases).<br>
</li><li><b>SOAP Integration</b> (Web Service implementation through configuration file –> Methods in a C++ header file exposed as Web-Services)<br>
</li><li><b>REST</b> Controller framework (pretty URL's) and RESTFULL acceptance test framework<br>
</li><li><b>AJAX</b> Integration (Using property based configuration - On the lines of DWR for Java –> Just define C++ header files and Methods will be exposed as AJAX calls)<br>
</li><li><b>EJB styled Beans</b> (Remote and Local Interfaces exposed -> C++ files have the services, and the methods to be exposed are defined in a configuration file)<br>
</li><li><b>Universal Object type</b> for C++ (intelligent pointer - no need of extending any class – identifies the object type)<br>
</li><li>Binary, XML and JSON based <b>Serialization</b> (Limited -> only for single level /no nesting of objects - header files required)<br>
</li><li><b>Reflection</b> (Limited –> header files required)<br>
</li><li><b>Dynamic C++ Pages</b> (Mix HTML and C++ code to produce run time views without web server restart)<br>
</li><li><b>Template Engine</b> and <b>Dynamic Views</b> generated from C++ objects.<br>
</li><li><b>Controller Pattern</b> (Implement controllers mapped with URL patterns to define custom behaviors)<br>
</li><li><b>Request/Response Filters</b> (Implement a chain of custom Filters for Pre/Post processing of request/response)<br>
</li><li><b>Thread Pool</b> Implementation<br>
</li><li><b>C++ Interpreter</b> (Limited support)<br>
</li><li><b>Rule based WEB</b> Behavior(idea can be expanded to other areas application wide)<br>
</li><li>XML Parser (DOM Styled)<br>
</li><li>Database Connection Pooling<br>
</li><li><b>Internationalization</b> support<br>
</li><li>Utilities such as Timer, Logging, Property Files etc.<br>
</li><li>File Upload<br>
</li><li>FTP Server<br>
</li><li><b>ROLE based Security</b> features for Method access (Web Services, AJAX calls, C++ Bean service calls, Server URL’s)<br>
</li><li><b>Module</b> for Integration of the framework with <b>Apache Web Server</b>
</li><li><b>Method Invoker</b> Server for cross platform Method Invocation (A daemon per language/platform approach – XML based Serialization/De- Serialization)</li></ul>

Also hosted at <a href='https://github.com/sumeetchhetri/ffead-cpp'>https://github.com/sumeetchhetri/ffead-cpp</a>
</font>