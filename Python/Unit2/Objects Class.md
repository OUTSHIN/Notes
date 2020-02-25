### Define your own type

> `class <name> ( <objects> ):`

```python
class Coordinate ( object ):
    def __init__ (self, x, y):	
    #"_" twice
	#special method to create an instance
	#"self" refers to the instance of the class that was created later
        self.x=x
        self.y=y
    def Distance(self, other):
        x_diff_sq=(self.x - other.x)**2
        y_diff_sq=(self.y - other.y)**2
        return (x_diff_sq+y_diff_sq)**0.5
    def __str__(self):
        return "<"+str(self.x)+","+str(self.y)+">"
```

```python
c=Coordinate(3,4)	
#Self can be omitted, and python automatically fills c into the self position
zero=Coordinate(0,0)
print(c.Distance(zero))
#same as
print(Coordinate.Distance(c, zero))
```

![UTOOLS1566025309114.png](https://md-imag.oss-cn-beijing.aliyuncs.com/UTOOLS1566025309114.png)

![UTOOLS1566026163631.png](https://md-imag.oss-cn-beijing.aliyuncs.com/UTOOLS1566026163631.png)

#### Printing Expression of an Object

> ```python
> def __str__(self):
>         return "<"+str(self.x)+","+str(self.y)+">"
> ```

![UTOOLS1566026247204.png](https://md-imag.oss-cn-beijing.aliyuncs.com/UTOOLS1566026247204.png)

#### Type of Different Order

![UTOOLS1566027106203.png](https://md-imag.oss-cn-beijing.aliyuncs.com/UTOOLS1566027106203.png)

#### Special Operators

![UTOOLS1566027315839.png](https://md-imag.oss-cn-beijing.aliyuncs.com/UTOOLS1566027315839.png)