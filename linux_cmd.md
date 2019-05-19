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
