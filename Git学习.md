# Git学习

### 基础学习

#### 区间概念

* **工作区（Working Directory）**：本地硬盘目录，一般是项目当前目录

* **暂存区（stage）**:一般餐放在（.git/index）中，也叫索引（index）

* **版本区（Respository）**:Git本地版本库，有个隐藏目录.git

* **分支（Branch）**：Git为我们自动创建的第一个分支master，以及指向master的一个指针叫HEAD

  ![Git工作流程图](https://typora-image-wang.oss-cn-hangzhou.aliyuncs.com/img/Git工作流程图.png)

#### 基础语法

`git init`:初始化本地库

`git status`:查看本地库状态

* 通过`git add` 从工作区提交到暂存区

* 在通过`git commit`从暂存区提交到版本区

  推荐使用`git commit -m "日志信息" 文件名`

#### 查看历史版本

`git reflog [文件名]`：查看版本历史信息

`git log [文件名]`：查看版本历史详细信息

#### 版本穿梭和撤销

**穿梭** ：

* `git reflog 文件名`：查看版本历史信息

*  `git reset --hard 版本号`：回到某版本

**撤销**：

​	未 add，未 commit：

* `git checkout --文件名`：还原为原来的文件

​	已add，未提交：

* `git reset [文件名]`：从暂存区撤回

  git版本切换，底层其实是移动的head指针
  
  ![指针操作原理](https://typora-image-wang.oss-cn-hangzhou.aliyuncs.com/img/指针操作原理.png)
  

### 分支

分支可以理解为副本，能够让多个任务共同推进而互不影响，即使某一个分支开发失败也不会影响到其他分支，底层原理是head指针指向的改变。

#### 基础操作

`git branch 分支名`：创建分支

`git branch -v`：查看分支

`git checkout 分支名`：切换分支



#### 合并分支

`git merge 分支名 `：将指定分支合并到当前分支

**产生冲突原因**：合并分支时，同一个文件在同一个链表位置产生不同的修改，Git无法决定使用哪一个，必须人为选择。

![合并冲突](https://typora-image-wang.oss-cn-hangzhou.aliyuncs.com/img/合并冲突.png)

**解决冲突**

1. 先修改冲突的文件
2. 在`git add`提交
3. 最后使用`git commit -m "日志"`提交，**末尾不能带文件名**。

**减少冲突的习惯**

* 先`pull`在修改，修改完立即`commit`和`push`
* 确保自己正在修改的文件是最新版的
* 各自开发各自模块，修改公共文件时要先确认有没有人正在修改
* 下班前提交代码，上班先拉取新代码
* 不要擅自修改他人代码

### Github操作

`git remote -v`：查看当前所有远程库别名

`git remote add 别名 远程库地址`：起别名

`git push 别名 分支`：推送本地分支所有内容到远程仓库

`git pull 远程库地址别名 远程分支名`：拉取远程库最新内容并合并到本地库

`git clone 远程库别名 远程分支名`：将远程库的内容拷到本地）

```
git clone 会做如下操作。1、拉取代码。2、初始化本地仓库。3、创建别名
```



