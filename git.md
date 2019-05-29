# 1.配置GIT
	- git config --global user.name "用户名"
	- git config --global user.emali "邮箱"
----
# 2.工作区域，暂存区与，git仓库
	- 1.working directory
	- 2.stage
	- 3.Repository（HEAD）
----
# 3.git管理文件的三种状态
	- 已修改（modified）
	- 已暂存（staged）
	- 已提交（committed）
----
# 4.初始化
	- git init
	
----
# 5.提交到缓存区
	- git add 文件名/.(全部)
----
# 6.提交到仓库
	- git commit -m "说明"
----
# 7.查看状态
	- git status
----
# 8.暂存回滚到本地
	- git checkout -- 文件名
	- 把暂存区域的文件还原到本地
----
# 9.回滚快照（版本）
	- git reset 文件名~数字（前几个版本）

	- git reset --mixed 文件名~数字  （默认）
		- 移动文件的只想，将其指向上一个快照
		- 将文件移动后指向的快照回滚a's'd到暂存区域

	- git reset --soft 文件名~数字
		-移动文件的指向，将其指向上一个快照

	- git reset --hard 文件名~数字
		- 移动文件的指向，将其指向上一个快照
		- 将文件移动后指向的快照回滚到暂存区
		- 将暂存区的文件还原到本地

	- 回滚指定快照
		- git reset 快照id 文件名
	- 回滚个别文件
		- git reset 快照id 文件名/路径

	- 前滚
		- git reset 快照id 文件名
----	
# 10.比较暂存区和本地目录
	- git diff

	- 比较两个历史快照
		- git diff 快照id1 快照id2
----
# 11.比较暂存区和仓库
	- git diff --chche 快照id
----
# 12.比较本地和仓库
	- git diff HEAD
----
# 13.修改最后一次提交
	- git commit --amend
----
# 14.删除文件a's'da's'd
	- git rm 文件名 

	- git rm -f 文件名 强制删除本地和暂存区的文件
	- git rm --eachead 文件名 只删除暂存区的文件
----
# 15.重命名文件
	- git mv 旧的文件名 新的文件名
----

# 16.分支*
## 1.创建分支
	- git branch 分支名称
		- git log --decorate 显示指向这个提示的所有引用 --oneline()（精简显示）--graph(图形化显示)--all(显示全部)
## 2.切换分支
	- git checkout 分支名
## 3.分支合并
	- git merge 分支名
## 4.删除分支
	- git branch -d 分支名



如何用命令将本地项目上传到git
1、（先进入项目文件夹）通过命令 git init 把这个目录变成git可以管理的仓库

git init
2、把文件添加到版本库中，使用命令 git add .添加到暂存区里面去，不要忘记后面的小数点“.”，意为添加文件夹下的所有文件

git add .
3、用命令 git commit告诉Git，把文件提交到仓库。引号内为提交说明

git commit -m 'first commit'
4、关联到远程库

git remote add origin 你的远程库地址
如：

git remote add origin https://github.com/githubusername/demo.git
5、获取远程库与本地同步合并（如果远程库不为空必须做这一步，否则后面的提交会失败）

git pull --rebase origin master
6、把本地库的内容推送到远程，使用 git push命令，实际上是把当前分支master推送到远程。执行此命令后会要求输入用户名、密码，验证通过后即开始上传。

git push -u origin master





如果希望保留生产服务器上所做的改动,仅仅并入新配置项, 处理方法如下:

git stash
git pull
git stash pop
然后可以使用git diff -w +文件名 来确认代码自动合并的情况.



反过来,如果希望用代码库中的文件完全覆盖本地工作版本. 方法如下:

git reset --hard
git pull


















# 三者之间的联系

	working(本地)--- add  --->stage(暂存区)------commit------>Respository(仓库)
	working(本地)<--- checkout  ---stage(暂存区)<------reset------Respository(仓库)

