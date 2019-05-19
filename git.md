## Git CodeMangement
#### 常用操作
```
	git init  创建一个新的仓库(用于最初的初始化)
	git remote add origin https://github.com/xxx.git 查看远程仓库的信息
	git remote  -v
    	修改远程仓库地址  (3种)
    	1.git  remote set-url origin [url]
	2.git remote rm origin
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
	git branch 查看本地分支， *为当前分支
	git branch -a  查看全部分支(包含本地和远程）
	git branch dev  创建dev分支　
	git checkout dev 　切换到dev分支
	git checkout -b dev    创建并切换到dev分支
	git branch -d dev 删除dev分支
	git merge dev 将dev 分支的合并到master 分支上，前提是在master 分支上
	git log 查看提交历史	
	git log filename 获取该文件的所有commit 历史
	git branch  -a --contains commitid  查看包含提交该id的所有分支
```   
#### 代码提交与追踪
```
	git add 对文件建立跟踪、查看状态
	git commit 提交
	git status 查看工作区状态，
	git push 推送到远程github上, 可以check冲突的文件
```    

#### 代码冲突(
```
	远程版本库包含本地尚不存在的提交如何解决：
	   a) git pull 把最新的代码拉下来，合并冲突
   	   b) git status
```


#### 代码撤销与回滚
```
	git reset --hard e377f60e28c8b84158	回滚到指定版本
	git push -f origin master　强制提交
	1.git commit 之前
	  git add 之前 (未添加到暂存区)
		git checkout -- file name 撤销修改
		git checkout -- . 多个文件
	  git add 之后
		git reset HEAD  filename 从暂存区撤销
		git reset HEAD 将所有暂存区文件撤销

	2.git commit 之后
	  git revert 撤销某次操作，而在此次操作之前和之后的提交记录都会保留,  可以通过git log 查看 
	  git revert commitid  
	  git reset commitid  回退到某次提交，覆盖是不可逆的
```
#### 本地分支和远程分支操作
```
	git fetch 更新远程代码到本地仓库
	git fetch origin branch1 #-- FETCH_HEAD
	git fetch origin branch1:branch2  创建本地分支branch2
	git log -p master.. origin/master 比较本地和远程的区别
	git merge origin/master 远程下载的代码合并本地仓库
```
```
	git 推送本地分支到远程分支并建立关联关系的三种不同方式:
	都需要切换到需要push 的本地分支上。
	1.直接git push
			远程已有remote_branch分支并且已经关联本地分支local_branch且本地已经切换到local_branch
	2.git push -u origin/remote_branch
			远程已有remote_branch分支但未关联本地分支local_branch且本地已经切换到local_branch
	3.git push origin local_branch:remote_branch
			远程没有remote_branch分支，本地已经切换到local_branch
```

#### bare库
```
	初始化版本库，只用于记录版本库历史记录的.git目录下的文件，
	不包含实际项目源文件的拷贝，不是工作目录
	git intit --bare 
```

#### 全部远程分支转为本地分支
```
	mkdir local_repo
	cd local_repo	
	git clone --bare  https://xxx.git  .git
	git config --unset core.bare
	git reset --hard
```

#### 其他命令
```
	git show <commit_id>   查看对应的修改
	git log -p filename    查看对应文件的修改历史日志
	git stash   暂存工作内容，可以把修改了没有commit的内容保存起来
	git diff  branch1 branch2 查看branch之间的文件差异
```	
