字符串和字符串函数
---
### 在程序中定义字符串
#### 字符串字面量
> 用双引号括起来的内容称为字符串字面量，也叫作字符串常量。双引号中的字符和编译器自动加入末尾的\0字符

- 从ANSI C标准起，如果字符串字面量直接没有间隔，或者用空白字符分隔，C会将其视为串联起来的字符串字面量 例如：
```c
char greeting [50] = "Hello, and"" how are" " you"" today!";
char greeting [50] ="Hello, and how are you today!";
/*两式等价*/
```
- 如果要在字符串内部使用双引号，必须在双引号前加一个反斜杠（\）
- 用双引号括起来的内容被视为指向该字符串储存位置的指针
```c
printf (" %s, %p, %c\n", "We", "are", *"space farers");
// *"space farers"表示该字符串所指向地址上储存的值
```
```c
/*输出：*/
We, 0x12848f2, s
```

#### 字符串数组和初始化
```c
char [4]="hi"
char [4]={'h','i','\\0'};
```
**注意**最后的**空字符**。如果没有空字符这就不是字符串而是字符数组

- 指定数组大小时，要确保数组元素个数至少比字符串长度多1
- 所有**未被使用的元素**都**自动初始化为'\\0'**
- 声明数组时大小必须是可求值的整数

##### 用指针创建字符串
```c
const char *pt1 = "something is pointing at me.";
const char ar1[ ] = "something is pointing at me.";
```
> 
两种声明**几乎**相同（不完全相同）

#### 数组和指针
##### 数组形式

字符串储存在***静态存储区***中，只有程序开始**运行时**才会为该数组**分配内存**

 > 此时字符串有两个副本
    1. 在静态内存的字符串字面量
    2. 存储在ar1数组中的字符串

在数组形式中，ar1为**地址常量**，不能更改ar1。可以进行`ar1+1`这样的操作，但是不允许进行`++ar1`这样的操作

##### 指针形式
也在***静态存储区***预留空间，一旦开始执行程序，它会为指针变量pt1留出一个储存位置，并把字符串的地址储存在指针变量中。该变量最初指向字符串的首字符，但是他的值可以改变。可以使用`++pt1`

##### 注意
- 字符串常量被视为const数据，由于pt1指向const数据，应把pt1声明为指向const数据的指针
- 初始化数组把静态存储区的字符串拷贝到数组中，而初始化指针只把字符串地址拷贝给指针
- 数组名是常量，指针名是变量
- 如果**打算修改**字符串，就**不要使用指针 **指向字符串字面量

#### 字符串数组
```c
char str[2][10] = { "hellowor","asdasca" };
const char*  ptr[2]= { "hellowor","asdasca" };
```
- str数组是内含2个数组的数组，每个数组含10个char类型值，共占20个字节
- ptr数组是内含2个**指针的数组**，在系统中共占8个字节

> str中的数组存着字符串字面量的副本，所以每个字符串被存储了两次
ptr中的指针指向初始化时所用的字符串字面量的位置

- 因此，为字符串数组分配内存的使用率低
- 事实上，ptr数组的指针元素所指向的字符串不必储存在连续的内存中
- 如果要用数组表示一系列待**显示**的字符串，请使用**指针数组**
- 要**改变**字符串或为字符串输入预留空间，**不要使用**指向字符串常量的**指针**


