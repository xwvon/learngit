# Git 常用命令
## :blush: 起步
```Bash
git init #初始化一个空的git仓库
git add filename #添加文件到仓库
git commit -m "submit instructions" #把添加到仓库的文件正式提交上去，并提供提交说明
git commit -a #合并上面两条命令，提交所有更改并提供提交说明
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
## :smile: 远程仓库

