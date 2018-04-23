# 折腾Linux 过程中的一些记录
## Centos重置root密码
1. 启动界面出现下面画面时按任意键：  
![centos启动界面](./CentOS9.png)
2. 在启动菜单选中系统，按“e”键继续：  
![centos启动菜单](./CentOS10.png)
3. 选中引导序列，继续按“e”编辑：  
![centos](./CentOS11.png)
4. 将光标移至结尾，输入“single”并按回车键继续：  
![centos](./CentOS12.png)
5. 在以下自动出现的界面中，按“b”键进行引导：  
![centos](./CentOS13.png)
6. 出现命令提示符后，输入“passwd root”修改根用户密码，确认密码后修改成功，输入“reboot”重启系统即可完成重置  
![centos](./CentOS14.png)
### :smile: 更加具体的内容请点击[链接](https://www.ytyzx.org/index.php/%E5%A6%82%E4%BD%95%E6%81%A2%E5%A4%8D%E6%88%96%E9%87%8D%E7%BD%AEFreeBSD_%26_Linux%E7%9A%84root%E5%AF%86%E7%A0%81)
## 配置网络
1. 查看网络配置
```
ifconfig  
```
2. 选择网卡的设置IP地址和相应的子网掩码，eth0为第一个网卡
```
ifconfig eth0 172.21.0.250 netmask 255.255.255.0
```
3. 配置默认网关
```
route add default gw 172.21.0.254
```
4. 设置dns，用vim编辑/etc目录下的resolv.conf文件
```
nameserver 8.8.8.8
```
## 配置yum源
1. 进入/etc目录下yum.repo.d目录
```
cd /etc/yum.repo.d
```
2. 备份原本的源文件
```
mv CentOS-Base.repo CentOS-Base.repo.backup
```
3. 更换网易云或阿里云或中科大等开源镜像站的源
```
wget http://mirrors.163.com/centos/5.6/Centos-base.repo
```
>+ 可能由于各大开源镜像站对低版本的centos不再提供yum源的支持，可以把CentOS-Base.repo里的mirrorlist一行注释，并把baseurl一行中`http://centos/org`改为`http://vault.centos.org`，最后还需要把`$releasever`改为相应的版本
4. 生成缓存
```
yum clean all
yum makecache
```