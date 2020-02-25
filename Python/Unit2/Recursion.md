## Recursion

> To reduce a problem to a simpler version.

- Each recursion call to a function creates its own **scope/environment**.

- **Bindings of variable** in a scope are not changed by recursive call.

  > Using the same variable names but they are different objects in separate scopes

- Flow of control passes back to **previous scope** once function call returns value.

##### Characters

- 基例
- 链条
- 定义函数
- 判断语句（用于辨别是否为基例）

#####  Tower of Brahma puzzle (汉诺塔)

```python
def PrintMove (fr,to):
    print("Move from %s to %s"%(fr,to))
    
def Towers (n, fr, to, spare):
    if n==1:
        PrintMove(fr, to)
    else:
        Towers(n-1, fr, spare, to)
        Towers(1, fr, to, spare)
        Towers(n-1, spare, to, fr)
```

##### Fibonacci sequence (兔子数列)

```python
def Bunny(x):
    if x==1 or x==2:
        return 1
    else:
        return Bunny(x-1)+Bunny(x-2)
```

 ##### Palindrome (回文)

```python
def isPalidrome(str):
    def toChar(s):
        s=s.lower()
        ans=''
        for c in s:
            if c in "abcdefghijklmnopqrstuvwxyz":
            ans+=c
        return ans
    def isPal(s):
        if len(s)<=1:
            return True
        else:
            return s[0]==s[-1] and isPal(s[1:-1])
    return isPal(toChar(s))
```

