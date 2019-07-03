# 1、常用命令

* git init——初始化一个Git仓库
* git add——可反复多次使用，添加多个文件
* git commit -m——真正提交，完成操作
* git status——查看工作区状态
* git diff——查看修改内容
* git reset --hard commit_id——回退到某个版本HEAD指的是当前版本^指上一个~n指上n个
* git log——可以查看提交历史
* git reflog——查看命令历史
* git checkout -- file——丢弃工作区的修改（或者是将错删的文件从提交的版本库中替换回来）
* git rm（从版本库中删除文件）然后git commit

# 2、辅助配图

![git-repo](http://cdn.pidaye.top/git-repo.jpg)
![git-stage](http://cdn.pidaye.top/git-stage.jpg)
![git-stage-after-commit](http://cdn.pidaye.top/git-stage-after-commit.jpg)

# 3、远程仓库

* 建立远程仓库认证
	* ssh-keygen -t rsa -C "用户邮箱"
	* 将公钥添加到github上
	* git config --global user.name ""
	* git config --global user.email ""
* git remote add origin git@server-name:path/repo-name.git——关联远程库
* git remote remove <name>——删除远程关联
* git remote show <name>——显示当前远程库的状态
* git push -u origin master——第一次推送master分支的所有内容，之后可以用git push origin master推送最新修改
* git clone——克隆远程仓库
* git branch——查看分支
* git branch <name>——创建一个新分支
* git checkout <name>——切换分支
* git checkout -b <name>——创建和切换分支
* git merge <name>——合并某分支到当前分支
* git branch -d <name>——删除分支
* git log --graph——查看分支记录
* git merge --no-ff <name>——使用普通模式合并分支到当前分支
* git stash——将当前工作现场储存起来
* git branch -D <name>强行删除
* git remote -v——查看远程库信息
* git push origin branch-name——从本地推送分支，如果失败可以先用git pull抓取远程的新提交
* git checkout -b branch-name origin/branch-name——在本地创建和远程分支对应的分支
* git branch --set-upstream branch-name origin/branch-name——建立本地分支和远程分支的关联
* git rebase——可以把本地未push的分支提交历史整理成直线
* git push origin <tagname>——可以推送一个本地标签
* git push origin --tags——推送全部未推送过的本地标签
* git tag -d <tagname>——可以删除一个本地标签
* git push origin :refs/tags/<tagname>——可以删除一个远程标签
* .gitignore——忽略文件，可以对它做版本管理

# 4、自定义git指令

* git config --global alias.st status
* git config --global alias.co checkout
* git config --global alias.ci commit
* git config --global alias.br branch
* git config --global alias.last 'log -1'
* git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
* 每个仓库的Git配置文件都放在.git/config
* 当前用户的Git配置文件放在用户主目录下的一个隐藏文件.gitconfig
