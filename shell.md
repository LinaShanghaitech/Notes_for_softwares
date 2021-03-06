## Shell 语法
#### 命令传递参数
[参考链接](https://blog.csdn.net/a515983690/article/details/51554297)  
`xargs`: 从管道或者 `stdin`中读取数据，或者从文件的输出中读取数据

#### 三种引号的用法及区别
[参考链接](https://blog.csdn.net/vip_wangsai/article/details/72592649)

- 双引号 `“”`   对字符串中出现的`$`、`”、`和`\`进行替换
  `echo`会将输入的字符串送往标准输出，并在最后加上换行号  
  `-ne. -n` 不换行 `-e` 转义,启用反斜杠转义解释 `-E` 禁用反斜杠转移解释(默认)

- 单引号 `‘’`   不进行替换，将字符串中所有字符作为普通字符输出
- 反引号 \`\` 在反引号中的字符串将解释成shell命令来执行
  反引号是一个老的用法,`$()`才是新的用法，如例程中的`$(seq 10)`. 无论是在学习中，还是在实际工作中，`$()`都是被推荐的用法
  `$TestString=“$(echo $HOME) $”`,另外`echo`什么都不加，不会转义，但会对`$`进行替换

#### 括号的使用
- shell 中各种括号的作用 `()  (()) []  [[]] {}`
- 单小括号 `()`，`$()` 完成引号里的命令行，然后将其结果替换出来，再重组命令行  
  还可用于初始化数组，如 `array=(a b c d)`

- 双小括号`(())`
  只要括号中的运算符、表达式符合C语言运算规则，都可用在`$((exp))`中，甚至是三目运算符  
  重定义变量值 `a=5; ((a++))` 则将 `$a` 重定义为6  
  算术运算比较，双括号中的变量可以不使用$符号前缀, `for((i=0;i<5;i++))`

 

#### shelll 中的if语句 

```
  if -z -n -f -eq -ne -lt
  if condition
  then
    Command
  else
    Command
  fi
```
 
#### if用法
- `if Command then.` 命令执行成功，继续`then`,这里的`Command` 可以是多条指令，中间换行
- `if  函数 then`
- `if [expression_r_r] then` 或者 `if  test expression_r_r then`, `test` 和 `[]` 是等价的  
  更简略:`if [-f “/etc/shadow”] && echo “right”`
  

#### 其他
- 开头 `#! /bin/bash`
- 变量标准写法 `${BASH_SOURCE[0]}`
- 其中常用的命令获取某个文件所在的根目录，可用 
  `$(dirname $(readlink -f ${BASH_SOURCE[0]}))`
  
- `readlink` 查看符号链接所指向的位置， `-f` 选项可以递归跟随给出文件名的所有符号链接以标准化
- 查看完整路径的时候不要忘记添加 `-f` 变量赋值方式,等号左右两边不能出现空格，比如路径
- `$?` 指上一条命令的执行状态，0就是正常

