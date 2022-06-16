# Git学习

### 区间概念

* **工作区（Working Directory）**：本地硬盘目录，一般是项目当前目录
* **暂存区（stage）**:一般餐放在（.git/index）中，也叫索引（index）
* **版本区（Respository）**:Git本地版本库，有个隐藏目录.git
* **分支（Branch）**：Git为我们自动创建的第一个分支master，以及指向master的一个指针叫HEAD

### 提交Git流程

1. 通过`git add` 从工作区提交到暂存区
2. 在通过`git commit`从暂存区提交到版本区


#### **其他操作**

①查看工作区和暂存区最新版本的区别：`“git diff HEAD -- filename”`

②新建过撤销**未add**： `git checkout  --filename`

③撤销**已add未commit**：先`git  reset [HEAD]  filename`，再 `git checkout -- filename`

④撤销**已add已commit**：`git reset --hard HEAD^`

![Git工作流程图](../images/Git工作流程图.png)

