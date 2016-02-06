depInj.xml

```
<beans>
    <!--Define a new Bean of type TestBeanProp and inject objects as properties
        Setter Injection
    -->
    <bean name="testBeanProp" class="TestBeanProp" injectAs="prop">
        <!--Inject bean with name dependencyBean1-->
        <inject bean="dependencyBean1">
        <!--Inject bean with name dependencyBean2-->
        <inject bean="dependencyBean2">
        <!--Inject bean with type DependencyBean3-->
        <inject name="dependencyBean3" class="DependencyBean3">
        <!--Inject a string with value-->
        <inject name="strProp" inbuilt="string" value="Hello ">
    </bean>
    <!--Define a new Bean of type DependencyBean1-->
    <bean name="dependencyBean1" class="DependencyBean1"/>    
    <!--Define a new Bean of type DependencyBean2-->
    <bean name="dependencyBean2" class="DependencyBean2"/>


    <!--Define a new Bean of type TestBeanCons and inject objects as constructor args
        Constructor Injection
    -->
    <bean name="testBeanCons" class="TestBeanCons" injectAs="cons">
        <!--Inject an integer value-->
        <inject name="intProp" inbuilt="int" value="1234">
        <!--Inject a boolean value-->        
        <inject name="boolProp" inbuilt="bool" value="true">
        <!--Inject bean with type DependencyBean4-->
        <inject name="dependencyBean4" class="DependencyBean4">
    </bean>


    <!--Define a new Bean of type TestBeanIntf and inject objects as compatible interfaces
        Interface Injection
    -->
    <bean name="testBeanIntf" class="TestBeanIntf" injectAs="intf">
        <!--Inject bean with interface type DepDependencyBean1-->
        <inject intfType="DepDependencyIntf1">
        <!--Inject bean with interface type DepDependencyBean2-->
        <inject intfType="DepDependencyIntf2">
    </bean>
    <!--Define a new Bean of type DepDependencyBean1Impl which implements DepDependencyIntf1 interface-->
    <bean name="dependencyIntfImpl1" class="DepDependencyBean1Impl"/>
    <!--Define a new Bean of type DepDependencyBean2Impl which implements DepDependencyIntf2 interface-->
    <bean name="dependencyIntfImpl2" class="DepDependencyBean2Impl"/>
</beans>
```