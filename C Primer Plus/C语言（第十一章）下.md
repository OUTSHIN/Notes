### 字符串示例：字符串排序

#### 排序指针而非字符串
> 使用指向字符串的指针数组来进行交换排序

不仅简单，而且保留了原始顺序

### ctype.h字符函数和字符串
> 可以利用其函数对字符串进行处理

例如：
- toupper()函数把字符变为大写 
- ispunct()函数统计字符串中的标点符号个数

### 命令行参数

> C编译器允许main()没有参数或者有两个参数（一些甚至更多）

```c
#include <stdio.h>
int main(int argc, char *argv[])
{
    int count;
    
    printf("The command line has %d arguments:\\n", argc - 1);
    for (count = 1; count < argc; count++)
        printf("%d: %s\\n", count, argv[count]);
    printf("\\n");
    
    return 0;
}
```
命令
```c
./ main 3 hello i am
```
```c
结果
The command line has 4 arguments:
1: 3                                                                 
2: hello                                                           
3: i                                                              
4: am
```
- 当main()有两个参数时第1个参数是命令行中的字符串数量
- 系统用空格表示字符串的结束和字符串的开始（可以用双引号表示带空格的字符串）

### 把字符串转换为数字
> 如果你编写的程序需要数值命令参数，但是命令参数被读取为字符串。因此要把字符串转换为数字

- 如果需要整数，可以使用**atoi()函数**，该函数接收字符串，并返回相应的整数值
  - 如果字符串仅以整数开头，它只会把开头整数字符转换为整数值
  - 然而如果命令行参数不是数字，函数返回0
  - C标准规定这种情况下的行为是未定义的
- atof()函数把字符串转换成double类型值
- atol()函数把字符串转换成long类型值

- strtol()把字符串转换成long类型值（可以指定进制）
- 最多可以转换三十六进制，'a'~'z'字符都可以用作数字
- strtoul()把字符串转换成unsigned long类型值（可以指定进制）
- strtod()把字符串转换成double类型值（只能以十进制转换，只有两个参数）

```
long strtol ( const char * restrict nptr , char ** restrict endptr , int base )
/*nptr是指向字符串的指针，endptr指向设置为标识输入数字结束字符的地址，base表示以什么进制写入数字*/
```


