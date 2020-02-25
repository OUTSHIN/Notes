## String

> Closing in " " or ' ' . (as long as it's in the same quotations.) 

### Operators

- `+`

  - Connection string

    ~~~python
    hi="hello "
    name='python'
    total=hi+name
    # total is 'hello python'
    ~~~

- <string>  `* ` <number x >

  - Repeat the string with x times

    ```python
    hi='hello'
    total=hi*3
    # OP is 'hellohellohello'
    ```



### Functions

- `print( )`

  - When you use  `,`  in ( ), this function will automatically **add a space character**.  However, the type in () can be mixed.

    ```python
    print("hello",3,'hello')
    # OP: hello 3 hello
    ```

  - When you use `+`  in () , the output will not add space character.  However the type **must be string**.

    ```python
    print("hello"+'hello')
    #OP: hellohello
    ```

- `str()`

  - Change the data structure type into string

- `input("")`

  - In default, python think any input as string

  - You can cast this into any type you want, by using this `<type> ( input(" ") )`

  ```python
  text=input("Type anything...")
  print(5*text)
  text=int(input("Type anything..."))
  print(5*text)
  ###
  OP: 
  Type anything...5
  55555
  
  Type anything...5
  25
  ###
  ```

