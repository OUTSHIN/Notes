- 读取Excel表格
```
%读取有效数据
D = xlsread ( '文件名', '标签页名称' )
%D为变量
```
```
%读取指定范围数据
D = xlsread ( '文件名', '标签页名称', '范围')
%范围示例：A1:S7
```
```
%读取列标签存放到T中，D中依然存储数据
[D,T] = xlsread ( '文件名', '标签页名称' )
```

- 写入Excel表格
```
% Cell:起始单元格
xlsread = ( 'fileName', Matrix, 'Sheet', 'Cell' )
%成功的话返回值为1
```


- 

- 

- 

- 