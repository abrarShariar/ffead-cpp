# Filter Configuration #
```
<!--The list of filters configured in the application-->
<app>
    <filters>
        <!--A filter configured for request level filtering and the first filter in the request chain 
will server all request patterns-->
        <filter type="request" class="ExampleRequestFilter"/>
        <!--A filter configured for response level filtering and the first filter in the response chain
will server only *.htm-->
        <filter type="response" class="ExampleResponseFilter" url="*.htm"/>
    </filters>
</app>
```