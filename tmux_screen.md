# TMUX　窗口管理
### tmux:
```
   tmux ls 
   tmux new -s  xxx 创建session
   tmux a -t   xxx  恢复session
   tmux ,  重命名窗口
   tmux kill-session -t name
```
#### 会话
```
   <C-b> s 列出所有会话
   <C-b> $ 重命名当前会话
```

#### 窗口快捷键
```
   <C-b> c  创建新窗口
   <C-b> w  列出所有窗口
   <C-b> ,  重命名当前窗口	
   <C-b> x  关闭当前窗口
```
	
#### 杂项
```
   <C-b> d  退出 tmux（tmux 仍在后台运行）
   <C-b> t  窗口中央显示一个数字时钟
   <C-b> ?  列出所有快捷键
   <C-b> :  命令提示符
```
### screen:
```
    screen -ls
    screen -S  xxx   create session
    <C-a> k  关闭当前窗口
    <C-a> c  创建窗口 
    <C-a> d  (detach)  离开当前session, 仍到后台执行```
	
bufexplore:
		用于管理vim 的buffer
		参考链接:		https://blog.csdn.net/icycolawater/article/details/77946139
		\be 当前窗口显示
		\bs\bv 上下/左右建立新窗口显示
