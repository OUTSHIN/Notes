 ## Define a class (Recap)

![UTOOLS1566112253887.png](https://md-imag.oss-cn-beijing.aliyuncs.com/UTOOLS1566112253887.png)

#### Use getter and setter

- `get_<sttribute> ()`&`set_<sttribute> ()`

  > Use them to hide the attribute.
  >
  > Users just need to know how to use.

  ```python
  class cat (object):
      def __init__(self, age):
          self.year=age
      def get_age(self):
      	return self.year
      def set_age(self, new_age):
      	self.year=new_age
          
  a=cat(3)
  print(a.age)		---> error! no sttribute 'age'
  print(a.get_age())		---> 3
  ```

#### Python not great at information hiding

- allows you to **access data** from outside class definition 

  > `print(a.age)`

- allows you to **write to data** from outside class definition 

  > `a.age='infinite'`

- allows you to **create data attributes** for an instance from outside class defination

  > a.size="tiny"

- **Don not do any of these !!!**

#### Default argument

> Is used when no parameters are given.
>
> Allows you call it with no argument.

```python
def set_name(self, newnamae=""):
    self.name=newname
```



## Inheritance

![UTOOLS1566115718595.png](https://md-imag.oss-cn-beijing.aliyuncs.com/UTOOLS1566115718595.png)

#### Parent Class (Superclass)

> animal

```python
class animal(object):
    def __init__(self, age)：
    	self.age=age
    	self.name=None
    def get_age(self):
        return self.age
    def get_name(self):
        return self.name
    def set_age(self, newage):
        self.age=newage
    def set_age(self, newname=""):
        self.age=newname
    def __str__(self):
        return "animal:"+str(self.name)+":"+str(self.age)
```

#### Child class (Subclass)

> person, student, cat, rabbit

1. **Inherits** all data and behavious of parent class
1. **Add** more **info**
1. **Add** more **behavior**
1. **Override** behavior

----

- Class Cat

![UTOOLS1566116798222.png](https://md-imag.oss-cn-beijing.aliyuncs.com/UTOOLS1566116798222.png)

- Class Person

![UTOOLS1566117297116.png](https://md-imag.oss-cn-beijing.aliyuncs.com/UTOOLS1566117297116.png)

- Class student

![UTOOLS1566117759662.png](https://md-imag.oss-cn-beijing.aliyuncs.com/UTOOLS1566117759662.png)

#### Class variable

> Class varialble and their values are shared between all instance of a class

![UTOOLS1566118234380.png](https://md-imag.oss-cn-beijing.aliyuncs.com/UTOOLS1566118234380.png)

![UTOOLS1566118445584.png](https://md-imag.oss-cn-beijing.aliyuncs.com/UTOOLS1566118445584.png)

![UTOOLS1566118832905.png](https://md-imag.oss-cn-beijing.aliyuncs.com/UTOOLS1566118832905.png)

#### Your operations

- Add

  ![UTOOLS1566119188099.png](https://md-imag.oss-cn-beijing.aliyuncs.com/UTOOLS1566119188099.png)

- Equal

  > Compairing with ID.

  ![UTOOLS1566119256016.png](https://md-imag.oss-cn-beijing.aliyuncs.com/UTOOLS1566119256016.png)