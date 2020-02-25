## Branching &Looping

### If

- `if`

  ```python
  if  <condition>:	# When true, execute following expressions.(Include the last one)
  	<expression>		# When false, skip these expressions,
  	<expression>		# and execute the last expression.
  	...
  <expression>
  ```
  
- `if else`

  ```python
  if  <condition>:		##Two options only execute one.
  	<expression>
  	<expression>
  	...
  else:
  	<expression>
  	<expression>
  	...
  ```

- `if elif`

  ```python
  if  <condition>:		#Three options only execute one.
  	<expression>
  	<expression>
  	...
  elif <condition>:
  	<expression>
  	<expression>
  	...
  else:
  	<expression>
  	<expression>
  	... 
  ```

### While

```python
 while <condition>:		#if true, do all the stepps.
  	   <expression>	#then check ,condition> again.
  	   <expression>	#repeat until it is false 
  	   ...
```



### For
- When variable is **number**

  ```python
  for <variable> in range(<some_num>):
  	<expression>
  	<expression>
  	...
  ###
  #	first time, <variable> starts at the smallest value
  #	next time, <variable> gets the prev value+1
  #	until at the <some_num>-1
  ###
  ```
  
  > range(***start***, ***stop***, ***step***)	#**must be integer**
  >
  > example : range(1, 5, 1) create a sequence [1,2,3,4] 
  >
  > ​				  range(1, 5, 2) create a sequence [1,3] 	
  
- When variable is **string or list**

  ```python
  #string
  
  for n in "hello":
      print(n)
      
  """
  OP:
  h
  e
  l
  l
  o
  """
  ```

  ```python
  #list
  
  list=['hello','hi','how']
  for n in list:
      print(n)
      
  """
  hello
  hi
  how
  """
  ```
  
  > We can use it to detect if there are some specific numbers or characters in  a string.
  
  ```python
  s="if i or u in here"
  for char in s:
  	if char=="i" or char=="u":
  		print("There is an i or u.")
  	else:
  		print("There isn't an i or u.")
  ```
  
  

### Break

> Exit the loop in which the statement is located

### for VS while LOOPS

|                      for                      |                            while                             |
| :-------------------------------------------: | :----------------------------------------------------------: |
|        **known** number of iterations         |               **unknown** number of iterations               |
|          can **end early** via break          |                 can **end early** via break                  |
|              **uses a counter**               | **can use a counter**, but must initialize before loop and increment in inside loop |
| **can rewrite** a for loop using a while loop | **may not be able to rewrite** a while loop using a for loop |

