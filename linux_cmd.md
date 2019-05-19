## Linux 常用命令

#### 基础命令
```
find -name “*.txt” -exec ‘cat’ {} \; > car_part.txt 合并多个文件
cp -r -d src_dir dst_dir copy的时候，copy 软链接, 只需要添加 -d
ls -al 显示所有文件（包括隐藏文件）
unlink 删除软链接, 不用 rm -rf ， rm -rf 容易删除掉原始数据
ln -s src_file des_file 添加软链接,先把原来的软链接删掉，然后再添加
find . -name “*cpp” | xargs grep -ri “str1” 查找包含某字符串的文件
```

#### cat显示文件的内容
```
cat hello_world.txt
cat filename |  option
options:
 1.tail -n 1000 显示最后1000行
 2.tail +n 1000 从1000行开始几显示，显示之后的
 3.head -n 1000  显示前面1000行
```

#### 查看文件大小
```
df -h  查看系统中文件的使用情况
du -sh * 查看当前目录下各个文件及目录占用空间大小
```

#### grep 命令
```
grep [options] ‘pattern’ filename
options:
  —version -V
  -A N 找到所有匹配行，并显示匹配行后 N行
  -B N 找到所有匹配行，并显示匹配行前 N 行
  -b 找到所有匹配行，并显示偏移地址
  -c 显示多少行被匹配到
  -e 可以使用多个正则表达式
  -f FILEA  FILEB  FILEA 在 FILEB 中的匹配
  -i 不区分大小写
  -R/r 搜索子目录
 ```
 #### 进程管理与后台执行命令
 ```
  ps、jobs,jobs的状态可以是running, stopped
  ctrl + z 挂起
  bg %job_number 将一个在后台暂停的命令，变成继续执行（在后台执行）
  fg 将后台中的命令调至前台继续运行,用 fg %jobnumber将选中的命令调出
  kill -9 pid 终止
  ps ux | grep name 进程查找. eg:ps ux | grep firefox
  ps -ef  -e 显示所有进程， -f 全格式
 ```
 
 #### nohup 命令
 > 当在前台运行某个作业时，终端呗改作业占据，可以在命令后面加上`&`实现后台运行。不过作业在
后台运行的结果一样会输出到屏幕上，干扰工作，最好进行输出重定向
 `command > out.file  2>&1  &`
 
 > 使用&命令后，作业被提交到后台运行，当前控制台没有被占用，但是一但把当前控制台关掉(退出帐户时)，作业就会停止运行。
 nohup命令可以在你退出帐户之后继续运行相应的进程。`nohup`就是不挂起的意思(no hang up)。该命令的一般形式为
 ` nohup command > myout.file 2>&1 &`
 > 使用了`nohup`之后，很多人就这样不管了，其实这样有可能在当前账户非正常退出或者结束的时候，命令还是自己结束了。
 所以在使用`nohup`命令后台运行命令之后，需要使用`exit`正常退出当前账户，这样才能保证命令一直在后台运行
 
