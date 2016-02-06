# Security Configuration #
```
<!--The list of security parameters in the application-->
<app>
    <security>
                <!--Provides a handler for authenticating and authorizing access to users-->
		<login-handler provider="file:users" url="login.html"/>
                <!--login-handler provider="class:DefaultLoginHandler"/-->
		<!--login-handler provider="db:DefaultLoginHandler"/-->
		<!--A welcome page shown right after successful authentication/authorization-->
                <welcome file="index.html"/>
                <!--All pages in the application can be accessed anonymously-->		
		<secure path="*" role="ROLE_ANONYMOUS"/>
		<!--The /rest/* path of the application can only be accessed by valid users of the application-->
                <secure path="/rest/*" role="ROLE_USER"/>
	</security>
</app>
```