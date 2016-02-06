
```
class TestBeanProp
{
private:
    string *strProp;
    DependencyBean1 *dependencyBean1;      
    DependencyBean2 *dependencyBean2;
    DependencyBean3 *dependencyBean3;
public:
    void setStrProp(string *strProp)
    {
        this->strProp = strProp; 
    }
    string* getStrProp()
    {
        return this->strProp;
    }
    
    void setDependencyBean1(DependencyBean1 *dependencyBean1)
    {
        this->dependencyBean1 = dependencyBean1; 
    }
    DependencyBean1* getDependencyBean1()
    {
        return this->dependencyBean1;
    }
    
    void setDependencyBean2(DependencyBean2 *dependencyBean2)
    {
        this->dependencyBean2 = dependencyBean2; 
    }
    DependencyBean2* getDependencyBean2()
    {
        return this->dependencyBean2;
    }
    
    void setDependencyBean3(DependencyBean3 *dependencyBean3)
    {
        this->dependencyBean3 = dependencyBean3; 
    }
    DependencyBean3* getDependencyBean3()
    {
        return this->dependencyBean3;
    }
    
    void print()
    {
        cout << *(this->strProp) << fflush;
        this->dependencyBean1->print();
        this->dependencyBean2->print();
        this->dependencyBean3->print();
    }
};

class DependencyBean1
{
public:
    void print()
    {
        cout << "Wo" << fflush;
    };
};

class DependencyBean2
{
public:
    void print()
    {
        cout << "rl" << fflush;
    };
};

class DependencyBean3
{
public:
    void print()
    {
        cout << "d!!" << fflush;
    };
};
```