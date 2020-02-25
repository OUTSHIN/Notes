文件结尾
----
- C语言中getchar()和scanf()检测到文件结尾会返回EOF(end of file)
- EOF定义在stdio.h头文件，值为-1
- `while((ch=getchar())!=EOF)`代码内容中ch为整型变量，因为char类型只能表示0~255无符号整数，但EOF值是-1

### 重定向输入
```
./main < words  //命令行命令
/*main为程序，words为文件*/
```
- 该运算符使words与stdin流相关联
- 因为C把文件和I/O设备放在一个层面，所以文件就是现在的I/O设备

### 重定向输出
```
./main > words  //命令行命令
```
- 会创建words文件，然后把输出重定向至文件
（如果已有则擦除该文件内容）
- 重定向把stdout从显示设备赋给words文件

### 组合重定向
>制作mywords副本，命名为savewords

  ```
./main < mywordd > savewords
./main > savewords < mywords
```

输入验证
---
```c
while (scanf("%d",&n)==1)   //验证输入是否为数字
{
       //处理n
}
```