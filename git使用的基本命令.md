##### 1.检出仓库

git clone 

本地克隆  

```
git clone  sourcePath targetPath
```

远程克隆

```
ssh方式： git clone git@github.com:sword/StudyNote.git

https方式：git clone https://github.com/sword/StudyNote.git
```

##### 2.创建仓库

```
git init
```

##### 3.添加工作区（working dir）新的或者改动的文件到暂存区（Index）

```
git add <filename> 

git add * 

git add -A  提交所有变化

git add -u  提交被修改(modified)和被删除(deleted)文件，不包括新文件(new)

git add .  提交新文件(new)和被修改(modified)文件，不包括被删除(deleted)文件
```

##### 4.从暂存区删除添加或改动的文件

```
仅删除暂存区的文件 git rm --cache <filename> | *
工作区和暂存区的文件都删除 git rm <filename> | *
```

##### 5.忽略文件

创建.gitignore文件，可以将让一些文件无需纳入到git管理中

##### 6.查看当前仓库的状态

```
git status
```

##### 7.查看和对比修改的内容

```
git diff
```

##### 8.查看提价的历史记录版本（添加参数： -pretty=oneline,用于输出少量信息）

```
git log
```

##### 9.提交到当前分支master HEAD区

```
git commit -m '提交的备注信息'
```

##### 10.版本回退

HEAD表示当前版本，上一个版本就是HEAD^，上上一个版本就是HEAD^^，往上100个版本HEAD~100，如回退到上一个版本，则命令如下：

```
git reset --hard HEAD^
```

其中–hard参数表示撤销工作区与暂存区的修改，回退到指定历史版本，可使用如下命令：

```
git reset --hard 20038
```

其中20038为提交版本的前五位ID号（原始：20038c521d4e81aca8ec8bca9f05d50ebb4fb835），查看时可使用如下命令：

```
git reflog
```

##### 11.撤销操作

```
将这一次提交覆盖到前一次的提交中，最终只会留下一条提交记录：
git commit -amend
把暂存区的修改撤销掉，重新放回工作区
git reset <filename> | *
丢弃工作区的修改，已添加到暂存区的文件不受影响
git checkout -- <filename> | *
```

##### 12.远程仓库

```
推送到远程仓库
git push -u <remote-name> <branch-name>
如果你还没有克隆现有仓库，并欲将你的本地仓库连接到某个远程服务器
git remote add <remote-name> <url>
```

##### 13.分支

```
创建分支并切换到该分支
git checkout -b <branch>

创建分支
git branch <branch>

切换分支
git checkout <branch>

列出分支
git branch

合并指定分支到当前分支上
git merge <branch>

删除分支
git branch -d <branch>
```

##### 14.更新和合并

```
查看远程信息：
git remote -v

从远程获取最新版本到本地仓库，并自动merge到本地分支：
git pull <remote-name> <branch>

从远程获取最新版本到本地仓库，不自动merge到本地分支：
git fetch

合并分支前先到另外一个分支更新代码，然后本地合并后提交到远程仓库； 当有冲突时，可使用$ git diff或$ git status命令查看分支的差异，手工解决后，再执行$ git add <filename>命令以将它们标记为合并成功。查看提交记录图形信息：
$ git log --graph --pretty=oneline --abbrev-commit
```

##### 15.丢弃所有的本地改动与提交

```
抓取远程分支
git fetch <remote-name>
撤回到远程分支
git reset --hard origin/master
```

