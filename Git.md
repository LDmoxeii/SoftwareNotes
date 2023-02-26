# git


## git 代码
| 功能               | 代码           |
| ------------------ | -------------- |
| **初始化本地库**   | **git init**   |
| **查看本地库状态** | **git status** |
| **添加暂存区**     | **git add**    |
|**提交本地库**|**git commit -m** 标记|
|**查看简单日志**|**git reflog**|
|**查看详细日志**|**git log**|
|**版本穿梭**|**git reset -hrad** 版本号|
|**创建分支**|**git branch**分支名|
|**查看分支**|**git branch -v**|
|**切换分支**|**git checkout**|
|**合并分支**|**git merge**分支名|
|**查看当前所有远程地址别名**|**git remote -v**|
|**创建别名**|**git remote add**别名+远程地址|
|**推送阵地分支上的内容到远程仓库**|**git push**别名+分支|
|**将远程仓库的内容克隆到本地**|**git clone**远程地址|
|**将远程仓库对于分支最新内容拉下来后与当前本地分支直接合并**|**git pull**远程库地址别名+远程分支名|
|****|****|
## git修改文件

**git**在**修改**后需要重新**添加暂存区,提交本地库**
## git 多文件
**git批量添加**:每个文件空一格；
**add.**为添加当前文件所有;
**git多文件添加**：原代码后加入--all;
## git 冲突合并
**手动修改**;
**提交本地库时不加文件名，否则报错**