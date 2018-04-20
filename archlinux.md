## Arch linux 下关联远程**github**仓库的记录
###  打开shell终端，创建SSH Key:
```
sudo ssh-keygen -t rsa -C "email@example.com"
```
+ 注意如未找到命令需先安装openssh:
```
 sudo pacman -S openssh
```
+ 按默认安装将会在/root/.ssh/目录下创建id_rsa和id_rsa.pnb两个文件,其中id_rsa是私钥,id_rsa.pnb是公钥
### 在GitHub仓库中添加本机的KEY
+ 在SSH Keys页面点击"New SSH key"，填上任意的Title，并把id_rsa.pnb文件的内容复制到Key文本框，点击"Add SSH key"完成添加
### 关联GitHub上的远程仓库
+ 在本机上创建一个新的文件夹
```
sudo learngit && cd learngit
```
+ 初始化一个本地git仓库
```
sudo git init
```
+ 关联一个远程库
```
sudo git remote add origin git@github.com:Zyxfeng/learngit.git
```
+ 拉取关联的远程仓库到本地
```
sudo git pull origin master --allow-unrelated-histories
```
+ 对拉取下来的文件做一些更改
+ 然后尝试提交
```
sudo git add xxx
sudo git commit -m "对提交的描述"
```
>　对每个文件的更改都要进行提交和对提交描述，可以用`sudo git commit -a` 进行对所有的更改提交和描述
+ 查看工作区的状态，确认所有更改都已经提交
```
sudo git status
```
+ 从远程库fetch到更新
```
sudo git fetch origin
```
+ 推送当前分支并建立与远程上游的跟踪
```
sudo git push --set-upstream origin master
```
+ 查看提交记录
```
sudo git log
```
## LICENSE:
MIT
