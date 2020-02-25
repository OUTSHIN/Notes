##  String Manipulations

- Index

  - A character

    ```python
    s="abc"
    s[0]="a"
    s[-1]="c"
    ```

  - Slice

    > [start: stop: step], default step is 1

    ```
    s="abcdefgh"
    s[3:6]="def"
    s[3:6:2]="df"
    s[::]="abcdefgh"	#same as s[0:len(s):1]
    s[::-1]="hgfedcba"	#same as s[-1:-(lens(s)+1):-1]
    s[4:1:-2]="ec"
    ```

    

- Function

  - `len()`

    > output the characters in a string
