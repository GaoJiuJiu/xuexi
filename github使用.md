##### Github使用

##### 主要命令

![Screenshot from 2020-08-20 14-47-59](/home/dell/Pictures/Screenshot from 2020-08-20 14-47-59.png)

###### 创建分支并进入：

git branch [branchName] ,git  checkout [branchname] 

git checkout -b [branchname] 创建一个分支并将其检出

###### 合并：

git merge:

1. git checkout bugFix
2. git commit
3. git checkout master //切换到bugFix上，把bugFix合并到master上
4. git commit
5. git merge //
6. git checkout bugFix
7. git merge master   //让bugFix和master保持一致，现在均为最新

<img src="/home/dell/Pictures/Screenshot from 2020-08-20 15-01-03.png" alt="Screenshot from 2020-08-20 15-01-03" style="zoom:25%;" />
<img src="/home/dell/Pictures/Screenshot from 2020-08-20 15-01-17.png" alt="Screenshot from 2020-08-20 15-01-17" style="zoom:25%;" />

Rebase

当前处在自己分支如bugFix下面

git rebase master //会将自己的bugFix上新提交的接在master所在头部的后面

转到master下面

git rebase bugFix    //这样master和bugFIx一样

###### 在git中移动：

head概念：head是当前已检出的提交符号名称，本质上就是自己正在处理的提交。head指向的是当前分支（i think），随着checkout的变化而变化

head始终指向工作树上反映的最新提交，想要更改工作树的命令，都要从head开始。通常head指向分支名称

1. git **checkout** fixBug  //通过制定分支直接将head定位到那个地方，此时head指向fixBug

2. git **checkout** bugFix;    git checkout HEAD^; //此时head指向bugFix的父亲提交,同理还可以通过^^来定位到祖父提交
3. git **branch** -f master HEAD~3(n)   //强迫移动分支，将master强制移动到head后面的三个父级。

###### 逆转git

git reset:个人使用，随时回到之前的版本

git revert：企业使用，可以让别人也知道撤销了哪个更改。会产生新的提交

###### 四处移动

##### 远程库相关命令

可以对远程库进行操作？不能直接对origin/master分支进行操作

git commit的时候head也会跟着移动

git fetch