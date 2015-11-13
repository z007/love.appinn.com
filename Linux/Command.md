# Command

* http://man.linuxde.net/
* [sudo passwd](http://jingyan.baidu.com/article/5225f26b0ac250e6fb09084e.html)
 * [Change sudo password timeout in Ubuntu](http://itsfoss.com/change-sudo-password-timeout-ubuntu/)
* https://linux.cn/article-6160-1.html
* [Linux mkdir、tar 和 kill 命令的 4 个有用小技巧](https://linux.cn/article-5863-1.html#3_3387)

# 升级 get a coffee, or 10.
 * [Upgrade](https://www.kali.org/news/kali-linux-20-released/)
  ```
  apt-get update
apt-get dist-upgrade 
  ```
 * [apt-get update;apt-get upgrade;apt-get dist-upgrade各自的作用](http://blog.163.com/sys_suweixiao/blog/static/165351502012113184248394/)
 * [upgrade.sh](http://www.vixual.net/blog/archives/3)
 ```
 讓系統每週都能自動更新一次

於 /etc/cron.weekly/ 新增一個指令檔 “upgrade.sh”，內容如下:
 #! /bin/bash
apt-get update
apt-get -y dist-upgrade
apt-get clean

chmod 755 /etc/cron.weekly/upgrade.sh
 ```
 * [update](http://www.cnblogs.com/indiepop/archive/2011/11/10/2244903.html)
 * [apt-get](http://jingyan.baidu.com/article/4853e1e53204251909f7260f.html)

  

# linux下解压命令大全
http://www.cnblogs.com/eoiioe/archive/2008/09/20/1294681.html



```

https://linux.cn/tech/ | 技术 ◆ 学习|Linux.中国-开源社区
https://linux.cn/article-6551-1.html | 使用 HTTP/2 提升性能的7个建议-技术 ◆ 学习|Linux.中国-开源社区
https://linux.cn/article-6550-1.html | RHCE 系列（六）：安装 Samba 并配置 Firewalld 和 SELinux，和 Windows 共享文件-技术 ◆ 学习|Linux.中国-开源社区
https://linux.cn/article-6565-1.html | SSL/TLS 加密新纪元-Let's Encrypt-技术 ◆ 学习|Linux.中国-开源社区
https://linux.cn/article-6160-1.html | 新手指南： Linux 新手应该知道的 26 个命令-技术 ◆ 学习|Linux.中国-开源社区
http://man.linuxde.net/ | Linux命令大全(手册)_Linux常用命令行实例详解_Linux命令学习手册
1、排查一些简单的技术问题。
2、会一些Linux的基础命令。
3、会操作 win03-12的服务器。
4、熟悉搭建Linux和win下的php环境。
 
岗位职责：
1、帮助客户解决一些简单的服务器安全问题。
2、协助或者帮助客户安装系统要求的PHP环境。
3、协助或者引导客户使用产品。
4、答疑客户提出一些合理性的问题。
5、多服务器之间的数据迁移。


rmp 模块依赖 http://www.rpmfind.net/

1、IP地址配置
[root@localhost ~]# setup
#使用setup工具
[root@localhost ~]# vi /etc/sysconfig/network-scripts/ifcfg-eth0
把ONBOOT=“no” 改为
ONBOOT=“yes“
#启动网卡
[root@localhost ~]# service network restart
#重启网络服务
2、网络yum源
[root@localhost yum.repos.d]# vi /etc/yum.repos.d/CentOS-Base.repo
 [base] 容器名称，一定要放在[]中
 name 容器说明，可以自己随便写
 mirrorlist 镜像站点，这个可以注释掉
 baseurl 我们的yum源服务器的地址。默认是CentOS官方的yum源服务
器，是可以使用的，如果你觉得慢可以改成你喜欢的yum源地
址
 enabled 此容器是否生效，如果不写或写成enable=1都是生效，写成
enable=0就是不生效
 gpgcheck 如果是1是指RPM的数字证书生效，如果是0则不生效
 gpgkey 数字证书的公钥文件保存位置。不用修改



第六章：Linux软件包管理
主讲人：沈超（http://weibo.com/lampsc)
交流论坛：http://bbs.lampbrother.net
课程大纲
6.1 软件包管理简介
6.2 RPM包管理-rpm命令管理
6.3 RPM包管理-yum在线管理
6.4 源码包管理
6.5 脚本安装包与软件包选择
6.3.1 IP地址配置和网络yum源
6.3.2 yum命令
6.3.2 光盘yum源搭建
1、常用yum命令
1）查询
[root@localhost yum.repos.d]# yum list
#查询所有可用软件包列表
[root@localhost yum.repos.d]# yum search 关键字
#搜索服务器上所有和关键字相关的包
2）安装
[root@localhost yum.repos.d]# yum –y install 包名
选项：
install 安装
-y 自动回答yes
3）升级
[root@localhost yum.repos.d]# yum -y update 包名
选项：
update 升级
-y 自动回答yes
4）卸载
[root@localhost yum.repos.d]# yum -y remove 包名
选项：
remove 卸载
-y 自动回答yes
2、YUM软件组管理命令
[root@localhost ~]# yum grouplist
#列出所有可用的软件组列表
[root@localhost ~]# yum groupinstall 软件组名
#安装指定软件组，组名可以由grouplist查询出来
[root@localhost ~]# yum groupremove 软件组名
#卸载指定软件组



6.3.2 光盘yum源搭建
光盘yum源搭建步骤
1）挂载光盘
[root@localhost ~]# mount /dev/cdrom /mnt/cdrom/
2）让网络yum源文件失效
[root@localhost ~]# cd /etc/yum.repos.d/
[root@localhost yum.repos.d]# mv CentOS-Base.repo \
CentOS-Base.repo.bak
[root@localhost yum.repos.d]# mv CentOS-Debuginfo.repo \
CentOS-Debuginfo.repo.bak
[root@localhost yum.repos.d]# mv CentOS-Vault.repo \
CentOS-Vault.repo.bak
3）修改光盘yum源文件
[root@localhost yum.repos.d]# vim CentOS-Media.repo
[c6-media]
name=CentOS-$releasever - Media
baseurl=file:///mnt/cdrom
#地址为你自己的光盘挂载地址
# file:///media/cdrom/
# file:///media/cdrecorder/
#注释这两个不存在的地址
gpgcheck=1
enabled=1
#把enabled=0改为enabled=1，让这个yum源配置文件生效
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-6



mkdir -p /temp/a 
-p 递归创建
mkdir -p /temp/a/1 /temp/a/2

cp -rp 
-r 复制目录
-p 保留文件属性



rm -rm 
	-r删除目录
	-f强制执行


语法：ln -s [原文件] [目标文件]
 -s 创建软链接
功能描述：生成链接文件
文件处理命令：ln
范例：
 $ ln -s /etc/issue /tmp/issue.soft
 创建文件/etc/issue的软链接/tmp/issue.soft
 $ ln /etc/issue /tmp/issue.hard
 创建文件/etc/issue的硬链接/tmp/issue.hard

软链接特征：类似Windows快捷方式
1、lrwxrwxrwx l 软链接
软链接文件权限都为rwxrwxrwx
2、文件大小-只是符号链接
3、/tmp/issue.soft -> /etc/issue
箭头指向原文件
硬链接特征：
1、拷贝cp -p + 同步更新
echo "this is a test" >> /etc/motd
2、可通过i节点识别
3、不能跨分区
4、不能针对目录使用



change the permissions mode of a file
chmod
权限的数字表示
 r ---- 4
 w ---- 2
 x ---- 1
rwxrw-r--
 7 6 4
$ chmod g+w testfile
 赋予文件testfile所属组写权限
 $ chmod -R 777 testdir
 -R 递归
 修改目录testfile及其目录下文件为所有用户具
 有全部权限 

change file ownership
chown
$ chown shenchao fengjie
 改变文件fengjie的所有者为shenchao

chgrp
change file group ownership

$ chgrp lampbrother fengjie
改变文件fengjie的所属组为lampbrother

命令名称：umask
命令英文原意：the user file-creation mask
命令所在路径：Shell内置命令
执行权限：所有用户
语法：umask [-S]
 -S 以rwx形式显示新建文件缺省权限
功能描述：显示、设置文件的缺省权限
范例： $ umask -S






文件搜索命令：find
命令名称：find
命令所在路径：/bin/find
执行权限：所有用户
语法：find [搜索范围] [匹配条件]
功能描述：文件搜索
 $ find /etc -name init
 在目录/etc中查找文件init
 -iname 不区分大小写
 $ find / -size +204800
 在根目录下查找大于100MB的文件
 +n 大于 -n 小于 n 等于
 $ find /home -user shenchao
 在根目录下查找所有者为shenchao的文件
 -group 根据所属组查找
文件搜索命令：find
 $ find /etc -cmin -5
 在/etc下查找5分钟内被修改过属性的文件和
 目录
 -amin 访问时间 access
 -cmin 文件属性 change
 -mmin 文件内容 modify
文件搜索命令：find
 $ find /etc -size +163840 -a -size -204800
 在/etc下查找大于80MB小于100MB的文件
 -a 两个条件同时满足
 -o 两个条件满足任意一个即可
 $ find /etc -name inittab -exec ls -l {} \;
 在/etc下查找inittab文件并显示其详细信息
 -exec/-ok 命令 {} \; 对搜索结果执行操作
文件搜索命令：find
 -type 根据文件类型查找
 f 文件 d 目录 l 软链接文件
 -inum 根据i节点查找
文件搜索命令：find




文件搜索命令：locate
命令名称：locate
命令所在路径：/usr/bin/locate
执行权限：所有用户
语法：locate 文件名
功能描述：在文件资料库中查找文件
范例：$ locate inittab
文件搜索命令：which
命令名称：which
命令所在路径：/usr/bin/which
执行权限：所有用户
语法：which 命令
功能描述：搜索命令所在目录及别名信息
范例：$ which ls 
文件搜索命令：whereis
命令名称：whereis
命令所在路径：/usr/bin/whereis
执行权限：所有用户
语法：whereis [命令名称]
功能描述：搜索命令所在目录及帮助文档路径
范例：$ whereis ls 
文件搜索命令：grep
命令名称：grep
命令所在路径：/bin/grep
执行权限：所有用户
语法：grep -iv [指定字串] [文件]
功能描述：在文件中搜寻字串匹配的行并输出
 -i 不区分大小写
 -v 排除指定字串
范例：# grep mysql /root/install.log




帮助命令：man
命令名称：man
命令英文原意：manual
命令所在路径：/usr/bin/man
执行权限：所有用户
语法：man [命令或配置文件]
功能描述：获得帮助信息
范例： $ man ls
 查看ls命令的帮助信息
 $ man services
 查看配置文件services的帮助信息
帮助命令：help
命令名称：help
命令所在路径：Shell内置命令
执行权限：所有用户
语法：help 命令
功能描述：获得Shell内置命令的帮助信息
范例： $ help umask
 查看umask命令的帮助信息



http://man.linuxde.net/useradd
http://www.jb51.net/article/45848.htm
http://man.linuxde.net/userdel 
userdel  -r sam
用户管理命令：useradd
命令名称：useradd
命令所在路径：/usr/sbin/useradd
执行权限：root
语法：useradd 用户名
功能描述：添加新用户
范例： $ useradd yangmi
用户管理命令：passwd
命令名称：passwd
命令所在路径：/usr/bin/passwd
执行权限：所有用户
语法：passwd 用户名
功能描述：设置用户密码
范例： $ passwd yangmi
用户管理命令：who
命令名称：who
命令所在路径：/usr/bin/who
执行权限：所有用户
语法：who
功能描述：查看登录用户信息
范例： $ who
用户管理命令：w
命令名称：w
命令所在路径：/usr/bin/w
执行权限：所有用户
语法：w
功能描述：查看登录用户详细信息
范例： $ w




压缩解压命令：gzip
命令名称：gzip
命令英文原意：GNU zip
命令所在路径：/bin/gzip
执行权限：所有用户
语法：gzip [文件]
功能描述：压缩文件
压缩后文件格式：.gz
压缩解压命令：gunzip
命令名称：gunzip
命令英文原意：GNU unzip
命令所在路径：/bin/gunzip
执行权限：所有用户
语法：gunzip [压缩文件]
功能描述：解压缩.gz的压缩文件
范例： $ gunzip boduo.gz 
压缩解压命令：tar
命令名称：tar
命令所在路径：/bin/tar
执行权限：所有用户
语法：tar 选项[-zcf] [压缩后文件名] [目录]
 -c 打包
 -v 显示详细信息
 -f 指定文件名
 -z 打包同时压缩
功能描述：打包目录
压缩后文件格式：.tar.gz 
压缩解压命令：tar
范例：
 $ tar -zcf Japan.tar.gz Japan
 将目录Japan打包并压缩为.tar.gz文件
压缩解压命令：tar
tar命令解压缩语法：
 -x 解包
 -v 显示详细信息
 -f 指定解压文件
 -z 解压缩
范例：$ tar -zxvf Japan.tar.gz
压缩解压命令：zip
命令名称：zip
命令所在路径：/usr/bin/zip
执行权限：所有用户
语法：
 zip 选项[-r] [压缩后文件名] [文件或目录]
 -r 压缩目录
功能描述：压缩文件或目录
压缩后文件格式：.zip 
压缩解压命令：zip
 范例：
 $ zip buduo.zip boduo
 压缩文件
 $ zip -r Japan.zip Japan
 压缩目录 
压缩解压命令：unzip
命令名称：unzip
命令所在路径：/usr/bin/unzip
执行权限：所有用户
语法：unzip [压缩文件]
功能描述：解压.zip的压缩文件
范例：$ unzip test.zip 
压缩解压命令：bzip2
命令名称：bzip2
命令所在路径：/usr/bin/bzip2
执行权限：所有用户
语法： bzip2 选项 [-k] [文件]
 -k 产生压缩文件后保留原文件
功能描述：压缩文件
压缩后文件格式：.bz2
范例：$ bzip2 -k boduo
 $ tar -cjf Japan.tar.bz2 Japan 
压缩解压命令：bunzip2
命令名称：bunzip2
命令所在路径：/usr/bin/bunzip2
执行权限：所有用户
语法： bunzip2 选项 [-k] [压缩文件]
 -k 解压缩后保留原文件
功能描述：解压缩
范例：$ bunzip2 -k boduo.bz2
 $ tar -xjf Japan.tar.bz2






网络命令：write
指令名称：write
指令所在路径：/usr/bin/write
执行权限：所有用户
语法：write <用户名>
功能描述：给用户发信息，以Ctrl+D保存结束
范例： # write linzhiling 
网络命令：wall
指令名称：wall
命令英文原意：write all
指令所在路径：/usr/bin/wall
执行权限：所有用户
语法：wall [message]
功能描述：发广播信息
范例： # wall ShenChao is a honest man!
网络命令：ping
命令名称：ping
命令所在路径：/bin/ping
执行权限：所有用户
语法：ping 选项 IP地址
 -c 指定发送次数
功能描述：测试网络连通性
范例： # ping 192.168.1.156 
网络命令：ifconfig
命令名称：ifconfig
命令英文原意：interface configure
命令所在路径：/sbin/ifconfig
执行权限：root
语法：ifconfig 网卡名称 IP地址
功能描述：查看和设置网卡信息
范例：# ifconfig eth0 192.168.8.250
网络命令：mail
命令名称：mail
命令所在路径：/bin/mail
执行权限：所有用户
语法：mail [用户名]
功能描述：查看发送电子邮件
范例：# mail root
网络命令：last
命令名称：last
命令所在路径：/usr/bin/last
执行权限：所有用户
语法：last
功能描述：列出目前与过去登入系统的用户信息
范例：# last
网络命令：lastlog
命令名称：lastlog
命令所在路径：/usr/bin/lastlog
执行权限：所有用户
语法：lastlog
功能描述：检查某特定用户上次登录的时间
范例：# lastlog
 # lastlog -u 502
网络命令：traceroute
命令名称：traceroute
命令所在路径：/bin/traceroute
执行权限：所有用户
语法：traceroute
功能描述：显示数据包到主机间的路径
范例：# traceroute www.lampbrother.net
网络命令：netstat
命令名称：netstat
命令所在路径：/bin/netstat
执行权限：所有用户
语法：netstat [选项]
功能描述：显示网络相关信息
选项：
-t ： TCP协议
-u ： UDP协议
-l ： 监听
-r ： 路由
-n ： 显示IP地址和端口号
范例：
# netstat -tlun 查看本机监听的端口
# netstat -an 查看本机所有的网络连接
# netstat -rn 查看本机路由表
网络命令：setup
命令名称：setup
命令所在路径：/usr/bin/setup
执行权限：root
语法：setup
功能描述：配置网络
范例：# setup
挂载命令
命令名称：mount
命令位置：/bin/mount
执行权限：所有用户
命令语法：mount [-t 文件系统] 设备文件名 挂载点
范例：# mount -t iso9660 /dev/sr0 /mnt/cdrom




第四讲 Linux常用命令
主讲人：李明 （http://weibo.com/limingmessage）
 沈超（http://weibo.com/lampsc)
交流论坛：http://bbs.lampbrother.net
课程大纲
4.1 文件处理命令
4.2 权限管理命令
4.3 文件搜索命令
4.4 帮助命令
4.5 用户管理命令
4.6 压缩解压命令
4.7 网络命令
4.8 关机重启命令
1、shutdown命令
[root@localhost ~]# shutdown [选项] 时间
选项：
-c： 取消前一个关机命令
-h： 关机
-r： 重启
2、其他关机命令
[root@localhost ~]# halt
[root@localhost ~]# poweroff
[root@localhost ~]# init 0
3、其他重启命令
[root@localhost ~]# reboot
[root@localhost ~]# init 6
4、系统运行级别
0 关机
1 单用户
2 不完全多用户，不含NFS服务
3 完全多用户
4 未分配
5 图形界面
6 重启
[root@localhost ~]# cat /etc/inittab
#修改系统默认运行级别
id:3:initdefault:
[root@localhost ~]# runlevel
#查询系统运行级别
5、退出登录命令
[root@localhost ~]# logout








```

