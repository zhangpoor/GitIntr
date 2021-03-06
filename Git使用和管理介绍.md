#Git使用和管理介绍
aaaa
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
aaaa
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
git branch branchname  创建一个分支,需要注意，此处只是创建分支，不进行分支切换  
例：git branch block001  
git branch   不带参数,列出本地已经存在的分支，并且在当前分支的前面加“*”号标记  
例：  
$ git branch  
&nbsp;&nbsp;block001  
* master  
  
git branch -r 列出远程分支    
git branch -a 列出本地分支和远程分支  
git branch -m | -M oldbranch newbranch 重命名分支   
git branch -d | -D branchname 删除branchname分支  
git branch -d -r branchname 删除远程branchname分支


###git merge  
git merge的基本用法为把一个分支或或某个commit的修改合并现在的分支上。  
例：  
＃ 切换到Master分支  
git checkout master  
＃ 对Develop分支进行合并  
git merge --no-ff block001 
 

结果，block001的内容，合并到了master


##Git可视化工具SourceTree
SourceTree 是 Windows 和Mac OS X 下免费的 Git 和 Hg 客户端，同时也是Mercurial和Subversion版本控制系统工具。支持创建、克隆、提交、push、pull 和合并等操作。  
SourceTree拥有一个精美简洁的界面，大大简化了开发者与代码库之间的Git操作方式，这对于那些不熟悉Git命令的开发者来说非常实用。  
SourceTree拥有完整的Git功能：  
通过一个简单的用户界面即可使用所有的Git命令  
通过一次单击，即可管理所有的Git库，无论是托管的还是本地的  
通过一次单击，即可进行commit、push、pull、merge等操作  
一些先进的功能，如补丁处理、rebase、shelve、cherry picking等  
可以连接到你托管在Bitbucket、Stash、Microsoft TFS或GitHub中的代码库
###下载地址
<https://www.sourcetreeapp.com>  
###创建仓库
####添加本地仓库:  
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_001.png)  
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_002.png)  
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_003.png)
####根据远程仓库创建仓库:  
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_004.png)  
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_005.png)  
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_006.png)  
###基本界面
####分支选择界面
可以查看该分支下的提交历史
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_007.png) 
####文件状态界面
可用于提交更新内容
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_008.png) 
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_009.png) 
####搜索界面
可根据不同条件筛选提交记录查看节点
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_010.png) 
####配置界面
可以对sourcetree进行设置，如提交时候的用户名、忽略文件等。
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_011.png) 
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_012.png) 
####文件提交的流程
一般文件提交更新的流程为：  
1.先拉去远程的更新内容  
2.添加本地更新内容并提交（若有冲突，合并解决冲突）  
3.推送前再次拉去远程的更新内容（推荐做法）  
4.推送本次提交内容至远程服务器  
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_013.png) 
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_014.png) 
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_015.png) 
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_016.png)
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_017.png) 
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_018.png)
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_019.png)
####创建分支
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_020.png)
####合并分支
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_021.png)
####重置修改
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_022.png)
####一些其它操作
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_023.png) 
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_024.png)
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_025.png) 
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_026.png)
![](/Users/zhangpoor/Desktop/Git使用和管理介绍/sourcetree/st_027.png)


##常见问题处理


##App打包管理流程
第二轮回归包之前统一在主开发分支上开发（部分比较大或者不确定的项目，单独建立分支，在第一轮回归测试之前，合并入主分支）。

第二轮回归包发出之后开始建立封板分支，命名规则例：Block_4_3_2_20160719

封板分支创建之后，要求修复的bug同步提交封板分支和主开发分支

每两天将封板分支代码merge到主开发分支中去

发布AppStore之后,将封板分支代码merge到主开发分支中去，打tag

完毕