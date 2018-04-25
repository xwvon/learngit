# Git 常用命令
## :blush: 起步
```Bash
git init #初始化一个空的git仓库
git add filename #追踪新文件
git commit -m "submit instructions" #把添加到仓库的文件正式提交上去，并提供提交说明
git commit -a #跳过使用暂存区域，直接提交所有已建立追踪关系的修改文件
git status #查看仓库当前状态，是否存在尚未被提交的修改
git diff #查看文件修改的具体内容
git log #查看所有的提交日志
git reset --hard HEAD^ #回退到上一个版本
git reset --hard commit_id #回退到指定commit_id号的版本
git reflog #查看命令历史，用以返回到指定版本
git checkout -- filename #放弃工作区文件的修改
git reset HEAD filename #放弃对已经添加到暂存区文件的修改
git rm filename #删除某个文件
```
## :smile: 远程仓库相关
```bash
git remote add origin git@github.com:Zyxfeng/learngit.git #把本地仓库与指定的远程仓库关联,并把远程库命名为origin
git push origin master #把本地仓库的所有内容推送到远程master分支
git clone git@github.com:xxx/xxx.git #克隆一个远程仓库到本地
git pull origin master #拉取远程仓库master分支
git remote show origin #查看指定远程仓库的详细信息
git push -f origin branchname #将远程仓库的某个分支回退到指定版本
git remote #查看远程仓库
git remote -v #查看远程仓库的详细信息
git remote rename oldOrigin newOrigin #重命名远程仓库
git remote rm origin  #删除远程仓库
```
## :smirk: 分支管理
```bash
git branch #查看当前本地分支
git branch branchname #创建某个分支
git checkout branchname #切换到某个分支
git branch -a #查看所有的分支，白色代表仅存在本地的分支，红色表示存在远程仓库的分支
git branch -r #查看远程的所有分支
git merge branchname #合并某个分支
git branch -d branchname #删除某个分支
git push origin branchname #推送某个分支到远程仓库
git push -d origin Zyxfeng-patch-1 #删除某个远程分支
git branch -D branchname    #强制删除某个分支
git branch branchname   #创建某个分支
git branch --track branch remote/branchname #新建一个分支并与指定的远程分支建立追踪关系
git branch --set-upstream branchname origin/branchname #将本地的某个分支与指定的远程分支建立连接
```
# 参考
+ [廖雪峰老师网站Git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)  
 :man: 廖老师的网站能学到很多东西 :relaxed:
+ [justjavac的博文](http://justjavac.com/tags.html#git-ref)  