
```
class TestBeanIntf 
{ 
private: 
    DependencyIntf1 *dependencyIntf1; 
    DependencyIntf2 *dependencyIntf2; 
public: 
    void DependencyIntf1(DependencyIntf1 *dependencyIntf1) 
    { 
        this->dependencyIntf1 = dependencyIntf1;  
    } 
    DependencyIntf1* getDependencyIntf1() 
    { 
        return this->dependencyIntf1; 
    } 
    
    void DependencyIntf2(DependencyIntf2 *dependencyIntf2) 
    { 
        this->dependencyIntf2 = dependencyIntf2;  
    } 
    DependencyIntf2* getDependencyIntf2() 
    { 
        return this->dependencyIntf2; 
    }  

    public void print()
    {
        this->getDependencyIntf1()->print1(); 
        this->getDependencyIntf2()->print2();
    }
};

class DependencyIntf1
{
public:
    virtual void print1()=0;
};

class DependencyIntf2
{
public:
    virtual void print2()=0;
};

class DepDependencyBean1Impl : public DependencyIntf2
{
public:
    void print1()
    {
        cout <<"Hello " << fflush;
    }
};

class DepDependencyBean2Impl : public DependencyIntf2
{
public:
    void print2()
    {
        cout "World!!" << fflush;
    }
};
```