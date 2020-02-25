## Compound data types

### Tuple

- an order sequence of elements, can **mix element type**

- cannot change element values, **immutable**

- represented with parentheses`"()"`

  ```python
  te=()			#empty tuple
  t=(2,"mit",3)
  #################
  t[0]	--->2
  
  #some operations
  (2,"mix",3)+(5,6)	--->(2,"mit",3,5,6)
  
  #slice
  t[1:2]				--->("mit",)	#","tells python this is a tuple with one element
  t[1;3]				--->("mit",3)
  len(t)				--->3
  t[1]=4				--->error!!
  ```

- Usage
  - **swap variable values**

  ```python
  #common
  tmp=x
  x=y
  y=tmp
  #by tuples
  (x,y)=(y,x)
  ```

  - **return more value from a function**

  ```python
  def f(x,y):
  	q=x//y
  	r=x%y
  	return(q,r)
  (quto,rem)=f(4,5)
  ```

  - can iterate over tuples 

  ```python
  ((),(),())
  ```

---

### List

- Same as `tuples `, but you can change the value, **mutable**	
  ```python
	a_list=[]	--->empty list
  L=[2,'a',4,[1,2]]
  len(L)		--->4
  L[0]		--->2
  L[2]+1		--->5
  L[3]		--->[1,2]
  L[4]		--->error!!
  i=2
  L[i-1]		--->'a'
  ```
  
- Usage

  - iterate(迭代) over list elements

    ```python
    #The following two code blocks are the same
    total=0
    	for i in range(len(L)):
            total += L[i]
        print total
    #############################
    total=0
    for i in L:				#i have the same value in the list L
    	total += i
    print total
  #list elements are indexed 0 to len(L)-1
    #range (n) goes from 0 to n-1
    ```
  
- Operations
  
  - **Add** elements
  
     - `L.append ( <object>)`
  
       > Add an element in the end of the list. (as one object)
  
       ```python
       L=[2]
       L.append ( [1,3] )		---> L is [2,[1,3]
       L.append ( 5 )		---> L is [2,[1,3],5]
       ##########
       L += [5]		---> L is [2,[1,3],5,5]
       L += [6,]		---> L is [2,[1,3],5,5,6]
       ```
       
     - `L.extend ( <sequence>)`
  
       > Add elements in the end of the list. 
       >
       > When you use extend, think of the <sequence> as a sequence, merging the sequence with the L sequence and following it.
       
       ```python
       L.extend ( [1,3] )		---> L[2, [1, 3], 5, 5, 6, 1, 3]
       ```
  
  - **Remove**
  
       > `L=[2,1,3,6,3,7,0]`
  
     - `L.remove ( element )`
     
       > Remove a **specific element** 
       >
       > - If element occurs multiple times, removes first occurrence
       > - If element not in list, give an error
     
       ```python
       L.remove(2)		---> L is [1,3,6,3,7,0]
       L.remove(3)		---> L is [1,6,3,7,0]
       ```
     
     - `del ( L [index] )`
     
       > Delete element at a **specific index**
     
       ```python
       del(L[1])		---> L is [1,3,7,0]
       ```
       
      - `L.pop()`
     
        > Remove element at end of list, returns the removed element
     
        ```python
        L.pop()			---> returns 0 and L is [1,3,7]
        ```
     
  - **Convert** to and from **strings**
  
       > s = "I<3 cs"		---> s is a string
       >
       > L = ['a', 'b', 'c']
  
       - `list( )`
  
            > Convert **string to list**
  
            ```python
            list(s)		---> returns ['I','<', '3', ' ', 'c', 's']
            ```
  
       - `s.split ( )`
  
            > Split a string on a character parameter, **splits on space if called without a parameter**
  
            ```python
            s.split('<')		---> returns ['I', '3 cs']
            ```
  
       - `''.join`
  
            > Turn a list of characters into a string, can give a character in quotes to add char between every elements
  
            ```python
            ''.join(L)		---> returns  "abc"
            ' '.join(L)		---> returns  "a b c"
            '_'.join(L)		---> returns "a_b_c"
            ```
  
  
  - Sort list
  
    > L=[9,6,0,3]
  
  
    - `sorted ( )`&`L.sort ( )`
  
      > Return sorted list. (Positive sorting正向排序)
  
      ```python
      sorted(L)		--->returns sorted list,  doesn't  mutate L , L is [9,6,0,3 ]
      L.sort( )		---> mutate L = [0,3,6,9], returns nothing
      ```
  
    - `reverse ( )`
  
      ```python
      L.reverse( )	---> mutate L = [9,6,3,0], returns nothing, List inversion sort
      ```
      
  
- Side effects

  -   Can have nested list

    > When you use nested list, it just point to the other list.
    >
    > If you change the value of the inner list, the outer list changes.

    ```python
    L=['yello','blue','pink']
    h=['red']
    v='red'
    bright=[L]
    bright.append(h)
    print(bright)
    bright.append(v)
    print(bright)
    ##################
    OP:
    [['yello', 'blue', 'pink'], ['red']]
    [['yello', 'blue', 'pink'], ['red'], 'red']
    ```

  - Avoid mutating a list as you are iterating over it

    - Python use an internal counter to keep track of index it is in the loop

    - Mutating change the list length but Python doesn't update the counter

    - Loop never sees elements 2 

      > (Just though the list L1 into a constant number's range, and each round the index of e is increasing. When you delete 1 at the 0 position, the next loop the 0 position changes into 2, but the e contained index is 1. So loop never see element 2)

    ```python
    def remove_dups (L1, L2):
        #L1_copy=L1[:]	      right one
        for e in L1:
        #for e in L1_copy	right one
            if e inL2:
                L1.remove(e)
    L1=[1,2,3,4]
    L2=[1,2,5,6]
    remove_dups(L1,L2)
    # L1 is [2,3,4] ot [3,4]
    ```

    