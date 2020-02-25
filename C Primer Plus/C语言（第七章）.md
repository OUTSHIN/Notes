C语言控制语句：分支和跳转
---- 

if 语句
---
```
if (expression)
    statement;
```
- 如果条件为真，执行statement，否则跳过statement

if else 语句
---
```
if (expression)
        statement1;
else
        statement2;
```
- 如果条件为真，执行statement1，如果为假，执行statement2

多重选择 else if
---
```
if (expression1)
        statement1;
else if (expression2)
        statement2;
        ………
else
        statement;
```
- 只有所有条件都不满足才执行else
- 如果没有花括号，else与最近的if配对
- 

continue语句
---
####注意

- 对于**while**和**do while**循环，执行continue语句后的下一个行为是**对循环测试表达式求值**
- 对于**for**循环，执行continue后的下一个行为是**对更新表达式求值**

break语句
--- 
 #### 注意
- 在**for**循环内执行完break语句后会直接执行循环后面下一个语句，**跳过更新部分** *（与continue语句不同）*

多重选择
--- 
```
switch (number)
{
case 1: statement1;
              break;
case 2: statement2;
              break;
case 3: statement3;
              break;
default: statement4;
}
```
#### 注意

- 如果没有匹配项并且没有default，程序继续执行switch后面的语句
- 如果没有break语句，会从匹配标签开始执行到switch末尾
- 根据浮点类型的变量或表达式来选择，无法使用switch

goto 语句
--- 
```
goto lable；
.
.
.
lable : statement;  //处于goto上下均可
```
#### 注意

- 避免使用goto
- 可以接受的用法----出现问题时从一组嵌套循环中跳出
- 标签语句可以出现在goto的前面或后面