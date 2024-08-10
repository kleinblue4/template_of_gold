## 如何使用 git 做文件版本控制 以及使用 github 进行文件托管

### Edited by 蔡 ， Edited for 瑞 & 硕

1. 工具准备

下载 Git：[下载地址 https://git-scm.com/downloads](https://git-scm.com/downloads)

下载 VS code: [下载地址 https://code.visualstudio.com/download](https://code.visualstudio.com/download)

> ps:如果使用 vscode 编写 C++代码，记得找个靠谱的教程去配置扩展工具

2. git 的使用与常用命令

推荐的视频：[bilibili 视频链接](https://www.bilibili.com/video/BV1s3411g7PS/?spm_id_from=333.337.search-card.all.click)

使用教程：[菜鸟链接](https://www.runoob.com/git/git-tutorial.html)

- 2.1 git add

git add 命令可将该文件的修改添加到暂存区。

一般使用方式为：

1.git add . (注意后面有个点) 添加当前目录下的所有文件到暂存区

2.git add filename1 filename 2 (指定所要添加的文件)

- 2.2 git commit

将暂存区内容添加到仓库中。**一般 git add 之后使用 git commit**

一般使用方式为：

1.git commit (-m message) 括号内的可以省略，如果不省略，则 message 表示对于此次提交的说明，例如：**git commit -m 第一次提交**

2.git commit filename1 filename2 (-m message) 添加指定的文件

- 2.3 git init

用于为当前文件夹下的文件初始化一个 git 仓库，方便在后续进行版本管理

使用方式：在要创建 git 仓库的文件夹下，右击选择 Open Git Bash here，在窗口中输入 git init，随后在该文件夹内会生成一个隐藏的.git 文件夹

- 2.4 git log

在使用 Git 提交了若干更新之后，又或者克隆了某个项目，想回顾下提交历史，我们可以使用 git log 命令查看。

- 2.5 git branch

通俗的理解，就是把当前的文件复制一份，形成一个单独的分支 branch，然后在这个分支上进行文件修改等操作，这样在多人协作方面很好用

一般使用方式：

git branch 查看所有的分支

git branch new_branch_name 创建一个新的分支，分支名为：new_branch_name

- 2.6 git checkout

当我们建立了多个分支的时候，如果要编辑某个分支下的文件，使用 branch checkout 命令来转换到所要修改的分支

一般使用方式：

git checkout branch_name 转换到指定的分支下，此时文件夹里的文件也会自动变成该分支里的文件

- 2.7 git merge

git merge 用于合并多个分支里的项目，一般使用如下：

git checkout main _假设现在转到 main 这个分支_
git merge 1.1 _将 1.1 这个分支合并到 main 分支_

- 2.8 git remote

git remote 命令用于用于管理 Git 仓库中的远程仓库。命令提供了一些用于查看、添加、重命名和删除远程仓库的功能。

一般使用介绍：

git remote add origin http://github.com/kleinblue4/try.git

将向当前 Git 仓库添加一个名为 origin 的远程仓库，它的 URL 是http://github.com/kleinblue4/try.git

更多使用参考[菜鸟教程](https://www.runoob.com/git/git-remote.html)

- 2.9 git push

git push 命令用于从将本地的分支版本上传到远程并合并。使用参考：[https://www.runoob.com/git/git-push.html]，

一般使用：

git push -u origin main 将本地的 main 仓库 push 到远程仓库并合并

- 2.10 git clone

用于克隆下载别人提交在 github 或 gitee 等代码托管仓库的命令，一般使用为：

git clone URL URL 为项目仓库的地址，如https://github.com/kleinblue4/template_of_gold.git

3. 怎么把文件上传 github 项目

Dear 瑞 or 硕 ：

- 第一步：首先用 VScode 打开一个文件夹，在终端里面,cd 到当前文件夹的目录，然后输入 git init 创建一个本地仓库，

- 第二步：输入 git clone https://github.com/kleinblue4/template_of_gold.git

- 第三步：git add filename 将你要上传的文件 add 到缓存

- 第四步：git commit -m message 将缓存里面的文件提交到本地仓库，建议写好 message，如 git commit -m 图论板子

- 第五步：git branch -M main 在本地仓库建立一个名为 main 的分支

- 第六步：git remote add origin https://github.com/kleinblue4/template_of_gold.git

- 第七步：git push -u origin main
  **注意：** 此处大概率会有报错，参考[https://blog.csdn.net/weixin_45844049/article/details/123733065]进行修改，即在.git 文件夹下的 config 中 url 改成(_https://TOKEN@github.com/kleinblue4/template_of_gold.git_)的形式
  即在 github.com 前面加上 TOKEN 和@，TOKEN 后续发在群里，
