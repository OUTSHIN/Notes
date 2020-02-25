## Dictionary

> Key is unique 
>
> Keys and Values could be **any type** of  structure, even dictionary

```python
my_dict={}		#empty dictionary
grades={'Ana':'B','John':'A+'}		# {'<Key>':'Value'}
```

#### Operations

- `<name>['<key>']`

  > **Look up the key** and returns the value. 
  >
  > If key isn't found, get an error.

  ```python
  grades['John']		---> evaluates to "A+"
  grades['Sylvan']	---> gives a KeyError
  ```

- `<name>['key'] = '<value>'`

  > **Add** an entry. 
  >
  > If add a same key many times, the value of the key is the last one.

  ```python 
  grades['Sylvan']='A'	---> grades={'Ana': 'B', 'John': 'A+', 'Sylvan': 'A'}
  ```

- `'<key>' in <name>`

  > **Test** if the key in dictionary.

  ```python
  'John' in grades		---> returns True
  'Daniel' in grades		---> returns False
  ```

- `del ( <name> ['<key>'] )`

  > **Delete** entry.

  ```python
  del(grades['Ana'])		--->grades = {'John': 'A+', 'Sylvan': 'A'}
  ```

- `<name>. keys ()`

  > NO ORDER !!!
  >
  > Get an inerrable  that acts like a tuple of all keys.

  ```python
  grades.keys()		--->returns dict_keys(['Ana', 'John', 'Sylvan'])
  ```

- `<name>.values()`

  > NO ORDER !!!
  >
  > Get an iterable  that acts like a tuple of all values.
  >
  > It returns every keys' value, even some values are repeat.

  ```python
  grades.values()		--->returns dict_values(['B', 'A+', 'A'])
  ```

  #### Compare with list

  |                   List                   |              Dictionary              |
  | :--------------------------------------: | :----------------------------------: |
  |     **ordered** sequence of elements     |    **matches** "keys" to "values"    |
  | look up elements by **an integer index** | look up one item by **another item** |
  |        indices have an **order**         |      **no order** is guaranteed      |
  |         index is an **integer**          |  key can be any **immutable** type   |

#### Applications

- Fibonacci

  - Inefficient one

    > Already known many values, however we compute many times.
    
    ![UTOOLS1565955706626.png](https://md-imag.oss-cn-beijing.aliyuncs.com/UTOOLS1565955706626.png)
  
  - Efficient one
  
    > use dic to store value
  
  ```python
  def fib(n,d):
      if n in d:
          return d[n]
      else:
          ans=fib(n-1,d)+fib(n-2,d)
          d[n]=ans
          return ans
      
  d={1:1, 2:1}
  ```
  
  

