# git笔记

[TOC]

## git与svn的区别：

git本地仓库包含代码库还有历史库，在本地的环境开发就可以记录历史
svn历史库存在中央仓库，每次对比与提交代码都必须连接到中央仓库才能进行。每一次commit都需要连网。
这样的好处在于：
​    1.自己可以在脱机环境查看开发的版本历史
​    2.多人开发时如果充当中央仓库的git仓库挂了，任何一个开发者的仓库都可以座位中央仓库进行服务。

## git常用命令

- git pull的用法：

> git pull <远程名> <远程分支名>:<本地分支名>
>
> 比如：张三管理整个项目的master分支，他每天下班前将dev1,dev2,dev3三个分支merge到master分支上，然后推送到远程master分支。
> ​	李四管理着dev1分支，他每天上班前将master分支上dev2,dev3更新的东西同步到dev1上。此时处理方式就是git pull origin master:dev1
> ​	如果是本地dev1分支想要拿到远程dev1分支的更新,并且本地dev1和远程dev1分支建立追踪关系。我们只需要git pull就好了。
>
> 多人合作开发：
> 问题一：比如有个远程分支dev,张三在本地建立一个dev分支和远程dev关联，李四也在本地建立一个dev分支和远程dev关联，当张三提交并且push到远程dev分支，
> 李四也想提交并且push到远程dev分支，此时会报错，李四需要pull远程dev分支，如果两人修改的东西有重叠的话需要解决冲突提交后才能push。没有冲突的话直接push.
>
> 问题二：同样的张三和李四都在本地创建dev分支和远程dev分支相对应，张三已经push了，李四手中的活还没做完但是想要获取最新的远程dev分支此时李四做法：
> ​	做法一：直接用git checkout -- <file> 放弃本地的修改
> ​	做法二：将修改的东西commit,然后pull，会自动将你做的修改和拉下来的代码合并。
> ​	做法三：git stash暂存你的修改,此时git pull后就是远程dev的代码了，如果可以用git stash pop将你的代码取出来合并到拉下来的代码中。

- git branch -D dev 删除本地dev分支
- git branch -m oldbranchName newbranchName  本地分支重命名
- git push origin :dev删除远程dev分支 还可以用git push -d origin dev 
- git在本地回退到某一个版本用：git reset --hard 版本号
- git revert <commit-id> 表示将这次的提交反向操作，比如某一次提交是增加了一行代码，用revert这次提交的版本号，表示删除这行代码提交到本地仓，然后push操作，就可以达到撤销远程的这次提交了。
- git reset HEAD <file> 可以把暂存区的修改撤销掉，重新放回到工作区： git reset HEAD readme.txt
- gitk命令可以图形化界面展示分支信息 -----哇，第一次知道这个东西，还挺好用的
- 当远程有相对应的分支，本地没有对应的分支，想要拉下这个分支最新的代码。 只要git checkout DZS-26413就可以了，千万不要加上-b 。 加上-b表示在本地新建分支。

在本地创建.gitignore文件后，将要过滤的文件名或后缀名放入到这个文件中，这个文件不会提交到仓库中，但是如果远程仓库中有这个文件，可以拉下来并且会覆盖
了本地同名文件。可以使用git check-ignore -v App.class 来查看.gitignore中对应的规则

当用git remote add origin git@github.com:hj605635529/code2.git 去关联一个远程仓库时，出现远程origin已经存在这个错误时可以用：
 git remote rm origin



默认安装下git会将中文文件名进行转码:

![image-20181114012652602](https://ws1.sinaimg.cn/large/006tNbRwly1fx6yaq6qbjj31ja0p2n6o.jpg)

方法：

```java
 git config --global core.quotepath false
 git config core.quotepath false
```

之后再git status显示如下:

![image-20181114012843042](https://ws4.sinaimg.cn/large/006tNbRwly1fx6y7paqkkj30zi0j0tej.jpg)

