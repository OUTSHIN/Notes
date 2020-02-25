#### 截图

`scort`: 直接截取全屏

`scort -d <value>` : value 秒后截图

`scort -s`: 选择截图区域

#### 获取文件

`wget <URL>`: 从URL下载文件

#### 开机自动运行脚本或程序

`sudo vim /etc/rc.local`: 修改该文件添加自动运行程序

```shell
#添加运行程序的地址，在最后加 & ，表示在后台运行
/usr/bin/python /home/pi/my_program.py &
```

#### 定期自动运行程序或脚本

`crontab -e` : 调取并编写定期运行脚本 

```shell
# m h dom mon dow command
#分钟 小时 每月的几号 月 星期几 希望运行的命令
#如果在数字位置出现 "*" 表示 “每” 
0 1 * * 1-5 cd /home/pi; python /home/pi/my_prigram.py
#如果需要切换到特定目录，可以用分号间隔多个命令
```

#### 搜索文件

`find`: 从指定目录开始搜索

#### 命令历史记录

- 上下键，CTRL+C取消选中命令操作

- `history`: 列出所有历史命令记录（包含编号）
  - `history | grep <value>`: 用管道方式显示包含<value>的命令，
  - 用`!<编号>`运行历史命令

#### 任务管理

`top` : 显示处理器内存等运行情况

`kill <PID>  `: 杀死指定的进程ID的进程

`ps -ef | grep "python"` : 查找所有Python进程

`killall python` : 中止所有匹配其参数的进程(python)

#### 列出所有USB设备

`lsusb` : 列出所有已连接的USB设备

#### 文件压缩

`tar`

-c: 建立压缩档案
-x：解压
-t：查看内容
-r：向压缩归档文件末尾追加文件
-u：更新原压缩包中的文件
-z：有gzip属性的
-j：有bz2属性的
-Z：有compress属性的
-v：显示所有过程
-O：将文件解开到标准输出
-f: 使用档案名字(必须)，这个参数是最后一个参数，后面只能接档案名

#### 连接文件

`cat <文件名0> <文件名1> <文件名2> > full_file.txt` : 将文件0，1，2连接起来并且重定向到full_file.txt文件中

#### 使用管道

`|`：将一个命令的输出传递给另一个命令

#### 隐藏输出到终端

`<command> > /dev/null`：将command的输出隐藏

#### 后台运行程序

- `python speed.py &`：需要运行的程序后面加&，后台运行并给出PID
- `fg`：使后台程序回到前台

#### 创建命令别名

1. 修改.bashrc文件，添加所需内容`alias rm='rm -i'`
2. 运行`source .bashrc`更新终端

#### 设置日期时间

`sudo date 010203042019` ：格式为MMDDHHMMYYYY, 月日小时分钟年

#### 查看硬盘剩余空间

`df -h`：查看可用空间

#### 	