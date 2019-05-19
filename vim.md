#VIM　编辑器管理

vim: 快捷键
	参考链接 https://www.cnblogs.com/markleaf/p/7808817.html
	移动:
			zz/zt/zb: 移动当前行到屏幕中央/顶部/底部
			Ctrl + u / d   向上/下滚动半屏
			w/e  向后跳
			W/E 向后长跳
			b/B 向前跳/长跳
	编辑:
				o/O:  向下/上插入行,并进入编辑模式
				i:  向后位置插入	
				a:  将光标置于当前位置之后,进入插入模式
				A: XXXXXX 行尾, xxxx
				p/P: 粘贴在之后/前
				<</>>   将当前行左/右移一个tab
				==  光标跳到缩进行首位置
				~  当前字符切换大小写
				ctrl +n / ctrl+p  vim 自带得自动补全
	多文件编辑
				:split[sp] 把当前文件水平分割
				:ls  查看缓冲区编辑文件
				:b 2
	多标签编辑:
				: tabedit file  新标签中打开文件file
				gt 下一个i标签
				0gt/1gt 第一个标签
	其它:
			q: 查看vim 历史命令
	操作目录:
				c 使当前打开的目录成为当前目录
				d 创建目录
				% 创建文件
				D 删除文件/目录
				- 转到上层目录
				qf 显示文件信息
				mf - 标记文件
				mt --标记需要移动或复制到的目录
				mu - unmark all marked files
				mb gb 跳转到 bookmark 得directory
				移动mm或者复制mc都需要 先mt 再 mf
