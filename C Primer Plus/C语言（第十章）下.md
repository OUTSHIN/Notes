指针和多维数组（难点）
---
> 假设有以下声明：`int zippo [4][2];`

- zippo的首元素是一个（内含两个int值的）数组，所以zippo是这个内含两个int值的数组的地址
- 给指针或地址加1，其值会增加对应类型大小的数值。zippo和zippo[0]不同，因为zippo指向对象占用了两个int大小，而zippo[0]指向的对象只占用一个int大小（加1后zippo+1指向zippo[1][0]，zippo[0]+1指向zippo[0][1]）
- `*zippo[0]`表示储存在`zippo[0][0]`的值，`**zippo`与`*&zippo[0][0]`等价。zippo是地址的地址，必须解引用两次才能获得原始值

### 指向多维数组的指针
> 因为zippo首元素是一个内含两个int类型的一维数组，因此，指针变量pz必须指向一个内含两个int类型值的数组，而不是指向一个int类型值，声明如下：

```c
int ( *pz ) [2];
/*pz指针指向一个内含两个int类型值的数组*/
```
- []优先级高，所所以要加括号，否则pz就是一个内含两个指针元素的数组
- 虽然pz是一个指针，不是数组名，但是也可以使用pz[2][1]这样的写法

### 指针的兼容性
> 指针不存在隐式类型转换

假设有此声明
```c
int * pt;
int (*pa) [3];
int ar1 [2] [3];
int ar2 [3] [2];
int **p2;    //一个指向指针的指针
```
有如下的语句

```c
pt = &ar1 [0] [0];    //都是指向int的指针
pt = ar1 [0];    //都是指向int的指针
pt = ar1;    //无效
pa = ar1;    //都是指向内含三个int类型元素数组的指针
pa = ar2;    //无效
p2 =&pt;    //都是指向int *
*p2 = ar2[0];    //都是指向int的指针
p2 = ar2;    //无效
```
> 以上无效的赋值表达式语句中涉及的两个指针都是指向不同的类型 例如：
- pt指向一个int类型值，而ar1指向一个内含三个int类型的数组
- pa指向一个内含3个int类型元素的数组，所以它与ar1的类型兼容，但是ar2指向一个内含2个int元素的数组，所以pa与ar2不兼容

> 最后两个指例子：
- 变量p2是指向指针的指针，它指向的指针指向int，而ar2是指向数组的指针，所以不匹配
- *p2是指向int的指针，与ar2[0]兼容。因为ar2[0]是指向该数组首元素（ar2 [0] [0]）的指针，所以ra2 [0] 也是指向int的指针

#### 两级解引用是把非const指针赋值给const指针也**不安全**（难点）

```c
const int **pp2;
int *p;
const int n = 13;
pp2 = &p1;    //有效，但导致const限定符失效
*pp2 = &n;    //有效，但是这导致p1指向n
*p = 10;    //有效，但改变了n值
```
- 上文事例给出的编译结果未定义。如：gcc编译n为13，clang编译，n为10
- C++允许在声明数组大小时使用const整数而C却不允许
- C++指针赋值检查更严格

### 函数和多维数组
> 编写二维数组函数的声明
```c
void somefunction ( int (* pt ) [4] );
void aomefunction ( int pt [ ] [4] );
/*空的方括号表明pt是一个指针*/
/*也可以在第1对方括号内写上大小，但是编译器会忽略该值*/
```

- 一般而言，声明一个N维向量指针时，只能省略最左边方括号中的值
```c
int sum ( int ar [ ] [12] [20] [30]);
int sum ( int (*ar) [12] [20] [30]);
/*两个声明等价*/
```
- 第一对方括号只用于表明这是一个指针，而其他的方括号则用于描述指针所指向数据对象的类型

### 变长数组(VLA)
- 过去，C规定数组的维度必须是常量
- C99新增了VLA，允许使用变量表示数组的维度
- 变长数组是自动存储类别，而且不能在声明中初始化
```c
int sum (int rows, int cols, int ar [rows] [cols] );
```
因为ar的声明要使用rows和cols，所以在形参列表中必须在声明ar之前先声明这两个参数

- C99/C11标准规定，可以省略原型中的形参名，但是在这种情况下，必须用星号来代替省略的维度
```c
int sum ( int ,int, int [*] [*]);
```

- 以变长数组作为形参的函数既可以处理传统C数组，也可以处理变长数组

### 复合字面量

> C99新增了复合字面量。字面量是除符号表示外的常量。例如：5是int的数组常量，'n'是char的字面量

`( int [2] ) {10,20}    //复合字面量`
- 去掉声明中的数组名，留下的int [2]即是复合字面量的类型名
- 复合字面量也可以省略大小，编译器会自动计算数组当前的元素个数
```c
int *pt1;
pt1 = (int [] ) {50,20,70};    //内含三个元素的复合字面量
```
复合字面量的类型也代表首元素地址，所以可以把它赋给指向int的指针。然后便可使用这个指针。例如：*ptr1是50，pt[1]是20 ...

- 还可以把复合字面量作为函数实际参数传递给带有匹配形式参数的函数
- 二维数组复合字面量
```c
( int [2] [4] ) { {1,2,3,4}, {3,4,2,7} }
```
可以省略第1对[ ]内的数值

- 复合字面量具有块作用域