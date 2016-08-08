#Git使用和管理介绍

Git是一个开源的分布式版本控制系统，可以有效、高速的处理从很小到非常大的项目版本管理。

分布式相比于集中式的最大区别在于开发者可以提交到本地，每个开发者通过克隆（git clone），在本地机器上拷贝一个完整的Git仓库。

###图例
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/001.jpg)


##Git的安装

##Git基础命令使用
###git --help
这个不多说了，显示git命令的内容，以及一些解释。  
也可以这么实用 git init -help，用来查看某条命令的帮助文本。

###git init
创建一个空的Git仓库或初始化现有。  
例：  
$ cd /Users/zhangpoor/Desktop/Git使用和管理介绍  
$ git init  
Initialized empty Git repository in /Users/zhangpoor/Desktop/Git使用和管理介绍/.git/
###git status  
查看当前Git仓库中的文件状态。  
可以列出当前目录所有还没有被git管理的文件和被git管理且被修改但还未提交(git commit)的文件。  
例：  
$ git status  
On branch master  
Initial commit  
Untracked files:  
(use "git add <file>..." to include in what will be committed)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;001.jpg  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"Git\344\275\277\347\224\250\345\222\214\347\256\241\347\220\206\344\273\213\347\273\215.md"  
     
&nbsp;&nbsp;&nbsp;&nbsp;nothing added to commit but untracked files present (use "git add" to track)
###git log  
在提交了若干更新之后，又或者克隆了某个项目，想回顾下提交历史，可以使用 git log 命令查看。  
例：  
$ git log  
fatal: your current branch 'master' does not have any commits yet
###git clone
###git checkout
###git add  
主要用于把我们要提交的文件的信息添加到索引库中。  
当我们使用git commit时，git将依据索引库中的内容来进行文件的提交。  
git add <path>  
例：  

###git rm
###git mv
###git reset
###git commit
###git pull
###git push
###git diff
###git branch
###git merge  
git merge的基本用法为把一个分支或或某个commit的修改合并现在的分支上。  
例：  
＃ 切换到Master分支  
git checkout master  
＃ 对Develop分支进行合并  
git merge --no-ff develop  

结果，develop的内容，合并到了master
###git tag

##Git可视化工具SourceTree


##常见问题处理


##Git管理流程