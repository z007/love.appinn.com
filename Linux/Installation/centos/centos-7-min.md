* Centos7安装完毕后无法联网的解决方法
  * ONBOOT=no改为ONBOOT=ye
```
cd etc/sysconfig/network-scripts/
 用ls命令查看网卡配置文件名（在CENTOS7中网卡名貌似变成了随机数字，所以每台机器的网卡名并不相同）
ifcfg-e* 这类 应该是你机器网卡名
vi  ifcfg-e* 你的网卡
将最后一行的ONBOOT=no改为ONBOOT=ye
service network restart
```
![](http://www.centoscn.com/uploads/allimg/140831/0036034325-0.jpg)
![](http://www.centoscn.com/uploads/allimg/140831/0036031L3-1.jpg)

* [CentOS7，我想将分配的网络接口名更改为别的名字。有什么合适的方法来来重命名CentOS或RHEL7的网络接口？](http://www.linux.cn/article-4045-1.html)

# 安装完最小化 RHEL/CentOS 7
* https://linux.cn/article-5341-1.html --安装完最小化 RHEL/CentOS 7 后需要做的 30 件事情（一）
* https://linux.cn/article-5342-1.html --安装完最小化 RHEL/CentOS 7 后需要做的 30 件事情（一）
  * http://www.tecmint.com/centos-7-installation/  --图像界面安装
  

1. 注册并启用红帽订阅
*	使用静态 IP 地址配置网络
 * yum install net-tools  --  [它提供 ifconfig 工具，如果你不习惯 ip 命令，还可以使用它]
 *  ip addr show          --使用 ip 命令来配置静态 IP 地址。所以，确认你首先检查了当前的 IP 地址
 *  vi /etc/sysconfig/network-scripts/ifcfg-enp0s3
*	设置服务器的主机名称
*	更新或升级最小化安装的 CentOS
*	安装命令行 Web 浏览器
*	安装 Apache HTTP 服务器
*	安装 PHP
*	安装 MariaDB 数据库
*	安装并配置 SSH 服务器
*	安装 GCC (GNU 编译器集)
*	安装 Java
*	安装 Apache Tomcat
*	安装 Nmap 检查开放端口
*	配置防火墙
*	安装 Wget
*	安装 Telnet
*	安装 Webmin
*	启用第三方库
*	安装 7-zip 工具
*	安装 NTFS-3G 驱动
*	安装 Vsftpd FTP 服务器
*	安装和配置 sudo
*	安装并启用 SELinux
*	安装 Rootkit Hunter
*	安装 Linux Malware Detect (LMD)
*	用 Speedtest-cli 测试服务器带宽
*	配置 Cron 作业
*	安装 Owncloud
*	启用 VirtualBox 虚拟化
*	用密码保护 GRUB
