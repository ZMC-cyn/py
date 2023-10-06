# 实验一 Git和MarkDown基础
班级：21计科04
学号：B20210302425
姓名：陈宥男
Gitte地址：https://gitee.com/ZMC_cyn
GitHub地址：https://github.com/ZMC-cyn/py_work
---

## 实验目的
1. Git基础，使用Git进行版本控制
2. Markdown基础，使用Markdown进行文档编辑
   ## 实验目的

1. Git基础，使用Git进行版本控制
2. Markdown基础，使用Markdown进行文档编辑

## 实验环境

1. Git
2. VSCode
3. VSCode插件

## 实验内容和步骤

### 第一部分 实验环境的安装

1. 安装git，从git官网下载后直接点击可以安装：[git官网地址](https://git-scm.com/)
2. 从Github克隆课程的仓库：[课程的仓库地址](https://github.com/zhoujing204/python_course)，运行git bash应用（该应用包含在git安装包内），在命令行输入下面的命令（命令运行成功后，课程仓库会默认存放在Windows的用户文件夹下）

```bash
git clone https://github.com/zhoujing204/python_course.git
```

如果你在使用`git clone`命令时遇到SSL错误，请运行下面的git命令(这里假设你的Git使用了默认安装目录)：

```bash
git config --global http.sslCAInfo "C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt"
```

或者运行下面的命令:

```bash
git config --global http.sslVerify false
```

如果遇到错误：`error setting certificate file`，请运行下面的命令重新指定git的安全证书：

```bash
git config --global --unset http.sslCAInfo
git config --global http.sslCAInfo "C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt"
```

该仓库的课程材料后续会有更新，如果需要更新课程材料，可以在本地课程仓库的目录下运行下面的命令：

```bash
git pull
```

在本地的仓库内容有更新后，可以运行下面的命令，将本地仓库的内容和远程仓库的内容同步：

```bash
git push origin main
```

3. 注册Github账号或者Gitee帐号，创建一个新的仓库，使用上面同样的方法将该仓库clone到本地，用于存放实验报告和实验代码，使用`git pull`和`git push`命令保持远程仓库和本地仓库的同步。
4. 安装VScode，下载地址：[Visual Studio Code](https://code.visualstudio.com/)
5. 安装下列VScode插件
   - GitLens
   - Git Graph
   - Git History
   - Markdown All in One
   - Markdown Preview Enhanced
   - Markdown PDF
   - Auto-Open Markdown Preview
   - Paste Image
   - markdownlint

### 第二部分 Git基础

教材《Python编程从入门到实践》P440附录D：使用Git进行版本控制，按照教材的步骤，完成Git基础的学习。

### 第三部分 learngitbranching.js.org
####使用git commit命令
创建一个新的提交记录
```bat
git commit
```
创建一个新的分支并将其交替
```bat
git branch bugFix
git checkout bugFix
git commit
```
合并分支
```bat
git branch bugFix //创建新分支
git checkout bugFix //切换带该分支
git commit//运行一次
git checkout main//切换回main
git commit//再提交一次
git merge bugFix//合并
```
另一种合并方法
```bat
git branch bugFix
git checkout bugFix
git commit
git checkout main
git commit
git checkout bugFix
git rebase main
```
# 高级篇
### 1. 分离head
```
git checkout c4 //head指向c4
```
### 2. 相对引用
- 使用 ^ 向上移动 1 个提交记录
- 使用 ~<num> 向上移动多个提交记录，如 ~3
```
git checkout bugFix^
```
### 3. 相对引用2
```
git branch -f main C6
git checkout C1
git branch -f bugFiX HEAD^
```
### 4. 撤销变更 
两种方法用来撤销变更:
1.git reset(本地)，2.git revert(远程)
pushed 是远程分支，local 是本地分支 
```
git reset HEAD
git checkout pushed
git revert HEAD
```
```
显示效果如下：
```bat
git init
git add .
git status
git commit -m "first commit"
```
### 第四部分 Markdown基础

查看[Markdown cheat-sheet](http://www.markdownguide.org/cheat-sheet)，学习Markdown的基础语法

使用Markdown编辑器（例如VScode）编写本次实验的实验报告，包括[实验过程与结果](#实验过程与结果)、[实验考查](#实验考查)和[实验总结](#实验总结)，并将其导出为 **PDF格式** 来提交。

如何将markdown文件转换为pdf格式的文件？

- 安装vscode插件Markdown PDF，安装后重启vscode，打开markdown文件，按下`Ctrl+Shift+P`，输入`Markdown PDF: Export (pdf)`，回车即可导出pdf文件。
- 使用Google Chrome浏览器，在Github网站或者Gitee网站打开你的仓库，浏览你的markdown文件，按下`Ctrl+P`，选择`打印`，选择`目标打印机`为`另存为PDF`，点击`保存`即可导出pdf文件。

## 实验过程与结果

请将实验过程中编写的代码和运行结果放在这里，注意代码需要使用markdown的代码块格式化，例如Git命令行语句应该使用下面的格式：

![Git命令](/Experiments/img/2023-07-26-22-48.png)

显示效果如下：

```bash
git init
git add .
git status
git commit -m "first commit"
```

代码运行结果的文本可以直接粘贴在这里。

**注意：不要使用截图，Markdown文档转换为Pdf格式后，截图可能会无法显示。**

## 实验考查

请使用自己的语言回答下面的问题，这些问题将在实验检查时用于提问和答辩，并要求进行实际的操作。

1. 什么是版本控制？使用Git作为版本控制软件有什么优点？
版本控制是一种跟踪和管理项目文件和代码变化的系统。。它主要用于协作开发，跟踪项目的历史记录，恢复先前的版本，以及解决多人同时编辑代码可能引发的冲突。
优点：分布式控制，分支管理，历史追踪，团队协作，开源和社区支持。

2. 如何使用Git撤销还没有Commit的修改？如何使用Git检出（Checkout）已经以前的Commit？（实际操作）
要撤销还没有 commit 的修改，可以使用 git checkout 命令来实现。你可以使用以下命令将工作区的修改恢复到最近一次 commit 的状态：
git checkout .
这个命令会抛弃当前工作区所有的修改，回到最近一次 commit 时的状态。
如果你只想撤销某个文件的修改，可以使用以下命令：
git checkout -- <文件路径>
这个命令会将指定文件恢复到最近一次 commit 时的状态。
要检出已经以前的 commit，可以使用 git checkout 命令并指定 commit 的哈希值或分支名，例如：
git checkout <commit 哈希值或分支名>
这个命令会将工作区的状态切换到指定的 commit，并且将 HEAD 指向该 commit。这样你就可以查看以前的代码或者进行相应的操作。
需要注意的是，使用 git checkout 命令切换到以前的 commit 时，会进入“分离头指针（detached HEAD）”状态。在这个状态下，你的修改不会作为新的 commit，所以如果要继续工作或者提交改动，最好先创建一个新的分支来保存你的修改。

3. Git中的HEAD是什么？如何让HEAD处于detached HEAD状态？（实际操作）
在 Git 中，HEAD 是指向当前所在分支或指向最新的提交（commit）的指针。它通常位于当前活动分支的最新提交上。
要让 HEAD 处于 detached HEAD 状态，可以通过以下命令实现：
git checkout <commit 哈希值>

4. 什么是分支（Branch）？如何创建分支？如何切换分支？（实际操作）
在 Git 中，分支（Branch）是指向提交（commit）的可变指针。它可以用来在代码仓库中同时进行不同的开发工作。
要创建分支，可以使用以下命令：
git branch <分支名>
其中 <分支名> 是你想要创建的分支名称。这个命令会在当前 commit 上创建一个新的分支。
要切换分支，可以使用以下命令：
git checkout <分支名>
其中 <分支名> 是你要切换到的目标分支的名称。

5. 如何合并分支？git merge和git rebase的区别在哪里？（实际操作）
合并分支可以使用 git merge 或 git rebase 命令。它们的区别如下：
git merge：将其他分支的修改合并到当前分支，并产生一个新的合并提交。这会在提交历史中保留合并的痕迹。
git merge <要合并的分支>
git rebase：将当前分支的修改基于其他分支的最新提交进行重播。它会将当前分支的修改应用到目标分支的最新提交之后，形成一条线性提交历史。不会产生合并提交。
git rebase <目标分支>
一般来说，如果你希望保留分支合并的历史信息，推荐使用 git merge。如果你希望提交历史保持线性，可以选择使用 git rebase。

6. 如何在Markdown格式的文本中使用标题、数字列表、无序列表和超链接？（实际操作）
标题使用 # 符号，一个 # 表示一级标题，两个 # 表示二级标题，以此类推，例如：
# 一级标题
## 二级标题
### 三级标题
数字列表可以使用数字加点的形式，例如：
1. 第一项
2. 第二项
3. 第三项
无序列表可以使用 - 或 * 符号，例如：
- 第一项
- 第二项
- 第三项
超链接可以使用 [链接文本](链接地址) 的形式，例如：
[百度](https://www.baidu.com)
## 实验总结

基本掌握git的使用方法。