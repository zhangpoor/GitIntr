#Git使用和管理介绍

Git是一个开源的分布式版本控制系统，可以有效、高速的处理从很小到非常大的项目版本管理。

分布式相比于集中式的最大区别在于开发者可以提交到本地，每个开发者通过克隆（git clone），在本地机器上拷贝一个完整的Git仓库。

###图例
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/001.jpg)


##Git的安装
安装方法，在Mac OS系统下，直接开启终端，打git命令，就会弹出选项框。  
&nbsp;&nbsp;&nbsp;&nbsp;1.安装命令行git。  
&nbsp;&nbsp;&nbsp;&nbsp;2.安装xcode git插件。  
&nbsp;&nbsp;&nbsp;&nbsp;3.退出。  
  
Windows操作系统下，偶没接触过，可以百度下，应该不麻烦。

##一些准备
去https://github.com网站上创建自己的账号。  
创建自己的仓库可以进行练习用。  
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/prepare.png)


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
commit 57f5480272d37c420363e108db3ea815cc42dcd6  
Author: zhangpoor <334521055@qq.com>  
Date:   Mon Aug 8 20:42:10 2016 +0800  
  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;提交完整文件  
  
commit b00f2b840d75aa96149231d915a4e818b203700c  
Author: zhangpoor <334521055@qq.com>  
Date:   Mon Aug 8 14:51:07 2016 +0800

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;first commit

###git clone
从远端服务器克隆一个仓库到本地。  
例：  
$ git clone https://github.com/zhangpoor/GitIntr test  
Cloning into 'test'...  
remote: Counting objects: 9, done.  
remote: Compressing objects: 100% (9/9), done.  
remote: Total 9 (delta 1), reused 8 (delta 0), pack-reused 0  
Unpacking objects: 100% (9/9), done.  
Checking connectivity... done.

###git checkout
检出分支，并切换到该分支进行工作。
例：  
git checkout master

###git add  
主要用于把我们要提交的文件的信息添加到索引库中。  
当我们使用git commit时，git将依据索引库中的内容来进行文件的提交。  
git add <path>  
例:  
git add Git使用和管理介绍.md  
$ git status
On branch master

Initial commit

Changes to be committed:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(use "git rm --cached <file>..." to unstage)  
  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;new file:   "Git\344\275\277\347\224\250\345\222\214\347\256\241\347\220\206\344\273\213\347\273\215.md"

Changes not staged for commit:  
&nbsp;&nbsp;&nbsp;&nbsp;(use "git add <file>..." to update what will be committed)  
&nbsp;&nbsp;&nbsp;&nbsp;(use "git checkout -- <file>..." to discard changes in working directory)

&nbsp;&nbsp;&nbsp;&nbsp;modified:&nbsp;&nbsp;&nbsp;&nbsp;"Git\344\275\277\347\224\250\345\222\214\347\256\241\347\220\206\344\273\213\347\273\215.md"

Untracked files:  
&nbsp;&nbsp;&nbsp;&nbsp;(use "git add <file>..." to include in what will be committed)

&nbsp;&nbsp;&nbsp;&nbsp;001.jpg   

###git commit
提交到本地仓库，一般要在 git add，git rm，git mv后使用 
例：
$ git commit -m "first commit"  
[master (root-commit) b00f2b8] first commit  
1 file changed, 75 insertions(+)  
create mode 100644  
"Git\344\275\277\347\224\250\345\222\214\347\256\241\347\220\206\344\273\213\347\273\215.md"

###git pull
从远程服务器拉去更新内容。  
例：  
$ git pull  
remote: Counting objects: 3, done.  
remote: Compressing objects: 100% (1/1),  
done.  
remote: Total 3 (delta 2), reused 3 (delta 2), pack-reused 0  
Unpacking objects: 100% (3/3), done.  
From https://github.com/zhangpoor/GitIntr  
&nbsp;&nbsp;&nbsp;&nbsp;57f5480..4f2a64e  master     -> origin/master  
Updating 57f5480..4f2a64e  
Fast-forward  
"Git\344\275\277\347\224\250\345\222\214\347\256\241\347\220\206\344\273\213\347\273\215.md" | 26 ++++++++++++++++++++++++--  
1 file changed, 24 insertions(+), 2 deletions(-)



###git push
将commit的内容，推送远程服务器。  
例:  
$ git push origin master  
Username for 'https://github.com': zhangpoor  
Password for 'https://zhangpoor@github.com':   
Counting objects: 3, done.  
Delta compression using up to 8 threads.  
Compressing objects: 100% (3/3), done.  
Writing objects: 100% (3/3), 1.50 KiB | 0 bytes/s, done.  
Total 3 (delta 0), reused 0 (delta 0)  
To https://github.com/zhangpoor/GitIntr.git  
* [new branch]&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;master -> master


###git reset
###git branch
###git merge  
git merge的基本用法为把一个分支或或某个commit的修改合并现在的分支上。  
例：  
＃ 切换到Master分支  
git checkout master  
＃ 对Develop分支进行合并  
git merge --no-ff develop  

结果，develop的内容，合并到了master


##Git可视化工具SourceTree


##常见问题处理


##App打包管理流程
第二轮回归包之前统一在主开发分支上开发（部分比较大或者不确定的项目，单独建立分支，在第一轮回归测试之前，合并入主分支）。

第二轮回归包发出之后开始建立封板分支，命名规则例：Block_4_3_2_20160719

封板分支创建之后，要求修复的bug同步提交封板分支和主开发分支

每两天将封板分支代码merge到主开发分支中去

发布AppStore之后,将封板分支代码merge到主开发分支中去，打tag

完毕