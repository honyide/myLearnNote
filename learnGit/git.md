# git

**git不记录文件只记录修改**



使用Windows的童鞋要特别注意：

千万不要使用Windows自带的**记事本**编辑任何文本文件。原因是Microsoft开发记事本的团队使用了一个非常弱智的行为来保存UTF-8编码的文件，他们自作聪明地在每个文件开头添加了0xefbbbf（十六进制）的字符，你会遇到很多不可思议的问题，比如，网页第一行可能会显示一个“?”，明明正确的程序一编译就报语法错误，等等，都是由记事本的弱智行为带来的。建议你下载[Visual Studio Code](https://code.visualstudio.com/)代替记事本，不但功能强大，而且免费！

## 常用git命令

git add 把工作区的修改添加到暂存区

git commit 把暂存区中的修改提交

git log命令显示从最近到最远的提交日志

git reset 回退版本，也可以撤销暂存区中的修改（unstage）

git state 查看当前状态

git checkout --撤销修改（用版本库的版本替换工作区中的版本）

git rm 删除版本库中的文件

关联一个远程库，使用命令`git remote add origin git@server-name:path/repo-name.git`

关联后，使用命令`git push -u origin master`第一次推送master分支的所有内容

使用命令`git push origin master`推送最新修改

Git还提供了一个`stash`功能，可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作

Git专门提供了一个`cherry-pick`命令，让我们能复制一个特定的提交到当前分支



### 分支策略

在实际开发中，我们应该按照几个基本原则进行分支管理：

首先，`master`分支应该是非常稳定的，也就是仅用来发布新版本，平时不能在上面干活；

那在哪干活呢？干活都在`dev`分支上，也就是说，`dev`分支是不稳定的，到某个时候，比如1.0版本发布时，再把`dev`分支合并到`master`上，在`master`分支发布1.0版本；

你和你的小伙伴们每个人都在`dev`分支上干活，每个人都有自己的分支，时不时地往`dev`分支上合并就可以了。

所以，团队合作的分支看起来就像这样：



Git专门提供了一个cherry-pick命令，让我们能复制一个特定的提交到当前分支









