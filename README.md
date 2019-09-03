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