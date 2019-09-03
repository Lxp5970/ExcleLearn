# ExcleLearn
#Git
git branch name 创建分支
git checkout name 切换分支
mkdir folder  分支下创建目录
touch folder/file2.txt 创建文件
git fetch origin master
git log -p master..origin/master
git merge origin/master 下载最新分支比较后合并
 
 提交变化  git add name
 git rm -- cached 命令将暂存区中的文件
 
 
 git init  初始化一个本地仓库
 git add .
 git status
 git commit -m"First commit" 将文件提交本地库
 git push origin master 将本地项目上传到github远程仓库 git push -u origin master（第一次提交）给git push -f 强制提交     git pull --rebase origin master
 git pull --rebase origin master 把远程同步到本地 git clone +链接@
 git push origin master 同步
 git remote add origin +链接http  将本地仓库和远程仓库进行关联
删除本地分支： git branch -d name
删除远程分支：git push origin --delete
如果删除不了可以强制删除，git branch -D name

把本地已有的项目提交到新的远程仓库。
touch README.md
git init
git remote add origin git@github.com:XXX.git
git add .
git commit -m "init"
git push -u origin master
将a仓库中的项目转移到b仓库中并保留原有的提交记录
git branch //查看一下本地有几个分支，如果有多个分支要先选一个主分支
git remote -v // 查看一下原有的仓库中有没有远程库，如果有origin,可以进入步骤3，没有进入步骤4
git remote rm origin // 删除掉远程库名
git remote add origin git@github.com:XXX.git
git push -u origin master

git mv -f oldfolder newfolder  重命名
未提交的更改，是不能git pull的

解决： 
先执行git stash 
初次提交：
- 通过git add 将文件 工作区 ---》暂存区 (本地)
- 通过git commit 将文件 暂存区 ---》分支 (本地)
- 通过git push 将文件 分支 ---》远程库 (github)

提交改动：
- 通过git commit将文件 暂存区 ---》分支 (本地)
- 通过git push 将文件 分支 ---》远程库 (github)

pull&push
- 通过git pull 将文件 远程库 ---》分支 (本地)
- 通过git push 将文件 分支 ---》远程库 (github)
第一种方法：（简单易懂）

1、git add .（后面有一个点，意思是将你本地所有修改了的文件添加到暂存区）
2、git commit -m""(引号里面是你的介绍，就是你的这次的提交是什么内容，便于你以后查看，这个是将索引的当前内容与描述更改的用户和日志消息一起存储在新的提交中)
3、git pull origin master 这是下拉代码，将远程最新的代码先跟你本地的代码合并一下，如果确定远程没有更新，可以不用这个，最好是每次都执行以下，完成之后打开代码查看有没有冲突，并解决，如果有冲突解决完成以后再次执行1跟2的操作
4、git push origin master 将代码推至远程就可以了

第二种方法：

1、git stash （这是将本地代码回滚值至上一次提交的时候，就是没有你新改的代码）
2、git pull origin master（将远程的拉下来）
3、git stash pop（将第一步回滚的代码释放出来，相等于将你修改的代码与下拉的代码合并）
然后解决冲突，你本地的代码将会是最新的代码
4、git add .
5、git commit -m""
6、git push origin master
这几步将代码推至了远程
最后再git pull origin master 