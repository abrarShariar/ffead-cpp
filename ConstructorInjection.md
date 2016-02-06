
```
class TestBeanCons
{
private:
    int *intProp;
    bool *boolProp;
    DependencyBean4 *dependencyBean4; 
public:
    TestBeanCons(int *intProp,bool *boolProp,DependencyBean4 *dependencyBean4)
    {
        this->intProp = intProp;
        this->boolProp = boolProp; 
        this->dependencyBean4 = dependencyBean4; 
    }
    
    int* getIntProp()
    {
        return this->intProp;
    }

    bool* getBoolProp()
    {
        return this->boolProp;
    }
    
    DependencyBean4* getDependencyBean4()
    {
        return this->dependencyBean4;
    }

    void print()
    {
        if(*(this->boolProp))
        {
            this->dependencyBean4->print();
            cout << *(this->intProp) << fflush;
        }
    }
};

class DependencyBean4
{
public:
    void print()
    {
        cout << "Hello World " << fflush;
    }    
};
```