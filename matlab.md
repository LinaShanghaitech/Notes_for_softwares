## Matlab

[参考1](https://blog.csdn.net/rushkid02/article/details/7929189)
[参考2](https://blog.csdn.net/jwh_bupt/article/details/11079229)
#### 基本函数和用法
```
    class(var) 获取变量的类型 
    size(var) 获取变量的维度  
    cell(size) 创建cell
    cell2mat() 将元胞数组转换为矩阵
    str2num 将str格式的数值转换为num格式的
    matlab 的索引都是从1开始, 使用() 来进行访问,  数组中 end 为最后一个值
    判定是否为空, 可以为 if size(x, 1) > 0
    fprintf() 文件输出
    sprintf() 输出得到字符串，eg:fname = sprintf(‘examples’) 
    true, false 也可用这创建数组
    matlab 中的 logical / bool 类型
```
#### Cell 操作
```
  获取cell array 中的指定位置的数:
    1. {} 提取到对应的值
    2. () 返回对应的cell
  注意:
    ()  必须放在最后,不允许继续索引
    比如 一个 cell array  a= {1, 4, 4}, a(1){} 这种方式是错误的
 ```

    
   


#### 文件操作
```
    fid=fopen(文件名,打开方式)
    COUNT=fprintf(fid,format,A)
    dir() 获取文件夹内的子文件
    mkdir() 创建文件夹
    exist() 判断是否存在, 判断条件取反操作 ～
    fileparts() 获取指定路径的目录和文件名, eg:[pathstr,name,ext] = fileparts(filename)
```
