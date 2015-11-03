# [Centos7安装完毕后无法联网的解决方法](http://www.centoscn.com/CentosBug/osbug/2014/0831/3621.html)
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


[CentOS6.3 最小化安装后配置](http://blog.csdn.net/knight1394/article/details/8560325)
```

```
# [解决克隆CentOS后 eth0无法初始化/找不到eth0的问题](http://www.centoscn.com/CentosBug/osbug/2015/0813/5998.html)
```

#ifconfig
只能看到本地环回口，
然后用
#ifconfig -a
查看所有可用网卡，发现显示的是eth1而不是eth0。
 
猜想
Clone的时候，将原虚拟机的网卡配置等全部Clone的，
但在VMware中Clone实际上也是重新创建一台服务器，
MAC地址等自然也会被重新创建，
但因为复制了原服务器的配置，所以新创建的网卡就不再是eth0，而是保存为eth1。
解决方法：
修改/etc/udev/rules.d/70-persistent-net.rules //保存网卡MAC地址等信息的配置文件
先查看里面有：
# PCI device 0x8086:0x100f (e1000)
SUBSYSTEM=="net", ACTION=="add", DRIVERS=="?*", ATTR{address}=="eth0-MAC", ATTR{type}=="1", KERNEL=="eth*", NAME="eth0"
# PCI device 0x8086:0x100f (e1000)
SUBSYSTEM=="net", ACTION=="add", DRIVERS=="?*", ATTR{address}=="eth1-MAC", ATTR{type}=="1", KERNEL=="eth*", NAME="eth1"
删除以上eth0的信息，将eth1的信息中的eth1-〉eth0
# PCI device 0x8086:0x100f (e1000)
SUBSYSTEM=="net", ACTION=="add", DRIVERS=="?*", ATTR{address}=="eth1-MAC", ATTR{type}=="1", KERNEL=="eth*", NAME="eth0"
再将vi /etc/sysconfig/network-scripts/ifcfg-eth0 中的MAC地址改成上面eth1-MAC地址，然后配置IP等信息，
重启服务器，就可以了。
然后再次用ifconfig 来查看时，出现的就是eth0的配置信息了。
```

# 安装完最小化 RHEL/CentOS 7
* http://www.tecmint.com/things-to-do-after-minimal-rhel-centos-7-installation/
* https://linux.cn/article-5341-1.html --安装完最小化 RHEL/CentOS 7 后需要做的 30 件事情（一）
* https://linux.cn/article-5342-1.html --安装完最小化 RHEL/CentOS 7 后需要做的 30 件事情（一）
  * http://www.tecmint.com/centos-7-installation/  --图像界面安装

# tool  
* [Speedtest-CLI](http://www.tecmint.com/check-internet-speed-from-command-line-in-linux/)
* [在 Linux 中以交互方式实时查看Apache web访问统计](https://linux.cn/article-5352-1.html)
* [centos 安装setup小工具](http://skyuck.iteye.com/blog/1724496)

1. 注册并启用红帽订阅
*	使用静态 IP 地址配置网络
 * yum install net-tools  --  [它提供 ifconfig 工具，如果你不习惯 ip 命令，还可以使用它]
 *  ip addr show          --使用 ip 命令来配置静态 IP 地址。所以，确认你首先检查了当前的 IP 地址
 *  vi /etc/sysconfig/network-scripts/ifcfg-enp0s3 --你的网卡名称可能不同 但应该是 ifcfg-e 开头的
 *  [CentOS7，我想将分配的网络接口名更改为别的名字。有什么合适的方法来来重命名CentOS或RHEL7的网络接口？](http://www.linux.cn/article-4045-1.html)
  ```
  IPADDR = "[在这里输入你的静态 IP]"
GATEWAY = "[输入你的默认网关]"
DNS1 = "[你的DNS 1]"
DNS2 = "[你的DNS 2]"
启网络服务并检查 IP 是否和分配的一样。如果一切都顺利，用 Ping 查看网络状态。
 service network restart
 ip addr show
 ping -c4 baidu.com
  ```
*	设置服务器的主机名称
 ```
echo $HOSTNAME 
vi /etc/hostname
echo $HOSTNAME 你也可以用 ‘hostname’ 命令查看你当前的主机名
```
*	更新或升级最小化安装的 CentOS
```
yum update && yum upgrade
```
*	[安装命令行 Web 浏览器](http://www.tecmint.com/command-line-web-browsers/)
```
yum install links
```
*	安装 Apache HTTP 服务器
```
 yum install httpd
```

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

#	安装 Owncloud

http://www.tecmint.com/install-owncloud-to-create-personal-storage-in-linux/

wget https://download.owncloud.org/community/owncloud-8.0.0.tar.bz2

```
tar -jxvf owncloud-8.0.0.tar.bz2
rm -rf owncloud-8.0.0.tar.bz2
chmod -R 777 owncloud

vi /etc/httpd/conf/httpd.conf	
AllowOverride None
Change this to:

AllowOverride All

service httpd restart

http://10.12.205.59/phpinfo.php  

http://localhost/owncloud   
OR
http://your-ip-address/owncloud   
```
### owncloud  status
``` 
ownCloud

Can't write into config directory!
This can usually be fixed by giving the webserver write access to the config directory.

ownCloud – 您控制的网络服务
```

# wwordpress
https://www.digitalocean.com/community/tutorials/how-to-install-wordpress-on-centos-6--2

wget http://wordpress.org/latest.tar.gz

tar -xzvf latest.tar.gz

http://localhost/wwordpress

### wordpress  status
```
OK  
```

