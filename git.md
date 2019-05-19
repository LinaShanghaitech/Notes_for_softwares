## Git CodeMangement
#### 常用操作
```
	git init  //创建一个新的仓库(用于最初的初始化)
	git remote add origin https://github.com/xxx.git 查看远程仓库的信息
	git remote  -v
    	修改远程仓库地址  (3种)
    	1. git  remote set-url origin [url]
	2. git remote rm origin
	   git remote add origin [url]
	3. 修改config文件,覆盖本地所有文件
	   git fetch --all
	   git reset --hard origin/master
```

#### 仓库管理原理
```
	git fetch  远程代码下载
	git merge  分支合并
	git pull == git fetch + git merge
	git rev-parse (--short) HEAD 获取从commitid
```	
#### 分支处理
```
	git branch		查看本地分支， *为当前分支
	git branch  -a  查看全部分支(包含本地和远程）
	git branch dev  创建dev分支　
	git checkout dev 　切换到dev分支
	git checkout -b dev    创建并切换到dev分支
	git branch -d dev 删除dev分支
	git merge  dev 将dev 分支的合并到master 分支上，前提是在master 分支上
	git log 查看提交历史	
	git log filename 获取该文件的所有commit 历史
	git branch  -a --contains commitid  查看包含提交该id的所有分支
```   
#### 代码提交与追踪
```
	git add 对文件建立跟踪、查看状态
	git commit 提交
	git status　　查看工作区状态，
	git push 推送到远程github上, 可以check冲突的文件
```    

####关于代码冲突(必须手动解决冲突后再重新提交）:
```
	远程版本库包含本地尚不存在的提交
	如何解决：
		a)  git pull 把最新的代码拉下来，合并冲突
		b) gjt status
```
#### 代码回滚:
```
	git reset --hard e377f60e28c8b84158	回滚到指定版本
	git push -f origin master　强制提交
```
