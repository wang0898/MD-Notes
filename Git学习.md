# Git学习

### 基础学习

#### 区间概念

* **工作区（Working Directory）**：本地硬盘目录，一般是项目当前目录
* **暂存区（stage）**:一般餐放在（.git/index）中，也叫索引（index）
* **版本区（Respository）**:Git本地版本库，有个隐藏目录.git
* **分支（Branch）**：Git为我们自动创建的第一个分支master，以及指向master的一个指针叫HEAD

#### 基础语法

`git init`:初始化本地库

`git status`:查看本地库状态

* 通过`git add` 从工作区提交到暂存区

* 在通过`git commit`从暂存区提交到版本区

  推荐使用`git commit -m "日志信息" 文件名`

#### 查看历史版本

`git reflog [文件名]`：查看版本历史信息

`git log [文件名]`：查看版本历史详细信息

#### 版本回退\穿梭\撤销

**回退**：

* `git reset--hard HEAD^ `：一次回退一个版本，^代表版本个数
* `git reset --hard HEAD~n`: 回退n次操作

**穿梭** ：

* `git reflog 文件名`：查看版本历史信息

*  `git reset --hard 版本号`：回到某版本

**撤销**：

​	未 add，未 commit：

* `git checkout --文件名`：还原为原来的文件

​	已add，未提交：

* `git reset [文件名]`：从暂存区撤回

  ![指针操作原理](C:\Users\naruto\Desktop\images\指针操作原理.png)
