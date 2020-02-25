### 指针和字符串

> 程序在处理相同字符串时通常不拷贝字符串，而是用指针指向字符串来提高效率。如果确实需要拷贝整个数组，可以使用strcpy()或strncpy()函数

### 字符串输入

##### fgets()函数
- fgets()函数返回指向char的指针。如果一切顺利，该函数返回的地址与传入的第一个参数相同。
- 如果函数读到文件结尾，它将返回一个*空指针*
- 如果读入数据出现某项错误也会返回NULL

### 自定义输入输出函数
> 如果标准函数不满足要求，可以在getchar()和putchar()的基础上自定义所需函数

```c
int put(const char *string)    //不修改字符串
{
    int count=0;
    while(*string)
    {
        putchar(*string++);
        count++;
    }
    putchar('\n');    //不统计换行符
    return (count);    
}

```
- `++`的优先级高于`*`，因此`putchar(*string++)`打印string指向的值，递增string本身，而不是指向的字符
- 当string指向空字符，`*string`值为0，即测试条件为假
- 形参用`const char *string`而不用数组是提醒用户处理的参数可以是数组名，用双引号括起来的字符串，或声明为`char*`的类型的变量

### 字符串函数
> C库提供多个处理字符串的函数，放在string.h头文件中

#### strlen()函数
> 用于统计字符串的长度

```c
void fit(char *string, unsigned int size)
{
    if (strlen(string) > size)
        string[size] = '\0';
}
```
```c
int main(void)
{
    char mesg[] = "Things should be as simple as possible,"
    " but not simpler.";
    
    puts(mesg);
    fit(mesg,38);
    puts(mesg);
    puts("Let's look at some more of the string.");
    puts(mesg + 39);
    
    return 0;
}

```
> 输出结果

```c
Things should be as simple as possible, but not simpler.
Things should be as simple as possible                                    
Let's look at some more of the string.                                  
 but not simpler.
```
- fit函数把第39个元素换成'\0'。puts()函数在空字符出停止
- 然而这些字符还在缓冲区，puts(mesg+39)函数把这些字符打印出来了

#### strcat()函数
> - strcat()（用于拼接字符串）函数接受两个字符串作为参数

- 函数把第二个字符串的备份附加在第一个字符串末尾，然后把形成的新字符串作为第一个字符串，第二个字符串不变
- 返回值为拼接后的**第一个字符串的地址**

    > 在手机上实验的返回值与第一个字符串地址一致（修改前后都一致）
- **！！！**该函数不能检查第一个数组能否容纳第二个字符串。如果第一个字符串空间不够大，多出来的字符串会溢出。要给拼接后字符串长度加一，或者用strncat()函数

#### strncat()函数
> 该函数增加了第三个参数，指定最大**添加**字符数。(参数超出范围依然会溢出)

#### strcmp()函数
> strcmp()函数（用于字符串比较）

- 如果两个字符串参数相同，该函数就返回0，否则返回非0值。
- strcmp()函数比较的是字符串，不是整个数组
- 该函数只会比较数组中第一个空字符前面的部
- 可以用该函数比较储存在**不同大小数组**的字符串
- strcmp()函数比较的是字符串，不是字符，所以参数应为字符串

##### 返回值
- 如果第一个字符串在第二个字符串前面，返回**负数**
- 如果两个字符串相等，返回0
- 如果第一个字符串在第二个字符串后面，返回**正数**

#### strncmp()函数
> 比较两字符串时可以比较到指定位置

```c
strncmp(a,b,7);
/*比较两字符串a，b前7个字符数*/
```
#### strcpy()和strncpy()函数

##### strcpy()
> 拷贝字符串

- 可以把指向源字符串的第2个指针声明为指针，数组或字符串常量
- 指向源字符串副本的第1个指针应指向一个数据对象，且有足够的空间储存源字符串的副本
- **！！！**声明数组将分配存储空间，声明指针只分配存储一个地址的空间
- 返回值为第一个参数的地址
- **！！！**第一个参数不必指向数组的开始
- 不会检查目标空间是否能容纳源字符串的副本
-------
##### 更谨慎的选择：strncpy()
> 该函数第三个参数指定可以拷贝的最大字符数

```
strncpy(target,source,n);
```
- 把source中的n个字符或空字符之前的字符（哪个先满足就拷贝到哪个地方）拷贝到target中
- 如果可以存下，则拷贝整个字符串，包括空字符
- 如果拷贝到第n个还未拷贝完整个源字符串，就不会拷贝空腹字符串
- 拷贝的副本不一定有空字符

#### sprintf()函数
> 声明在stdio.h中，该函数和printf类似，但是它把数据写入字符串，而不是打印在显示屏上。可以把多个元素组合成一个字符串。第1个参数是目标字符串的地址，其余与printf相同

```
char formal[666];
char first[]="hello";
char last[]="hi";
double price=12.3;
sprintf(formal,"%s, %s, %0.2f.",first,last,price);
```
结果：
```
hello, hi, 12.30
```

 





