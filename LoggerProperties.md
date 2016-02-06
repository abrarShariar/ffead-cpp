# Logger Properties #
```
<loggers>
        <!--The default logger-->
	<logger name="DEFAULT" mode="CONSOLE" level="INFO"/>
        <!--The custom logger with name JOB, writes to file jobs.log-->
	<logger name="JOB" mode="FILE" level="INFO">
		<file>jobs.log</file>
	</logger>
</loggers>
```