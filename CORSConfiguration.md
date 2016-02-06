# Cross Origin Resource Sharing ([CORS](http://www.w3.org/TR/cors/)) #
```
<app>
	<cors-config>
		<allow-origins>*</allow-origins>
		<allow-methods>GET, POST, HEAD, PUT, DELETE</allow-methods>
		<allow-headers>content-type, origin</allow-headers>
		<expose-headers>content-type, origin</expose-headers>
		<allow-credentials>true</allow-credentials>
		<max-age>1023</max-age>
	</cors-config>
        ...
</app>
```