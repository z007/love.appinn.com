# 安装 LAMP HTTP 服务器
```
 On Debian/Ubuntu/Linux Mint

# apt-get install apache2 apache2-doc apache2-utils mysql-server mysql-client php5 php5-mysql php5-curl
On RedHat/CentOS/Fedora

# yum install httpd mysql-server mysql-client php php-mysql php-curl
```


```
如果你想更改 Apache HTTP 服务器的默认端口号(80)为其它端口，你需要编辑配置文件 ‘/etc/httpd/conf/httpd.conf’ 并查找以下面开始的行：

LISTEN 80 

把端口号 ‘80’ 改为其它任何端口(例如 3221)，保存并退出。
```
# 我试了不可以

Centos只有 80这个端口默认可以LISTEN 80 

使用其他端口 需要特殊指定给http 才可以使用
比如 要用 3221 88 8445端口

[To fix my problem, I had to add ports 88 and 8445 and3221 to my system's centos7 configuration:](http://stackoverflow.com/questions/17079670/httpd-server-not-started-13permission-denied-make-sock-could-not-bind-to-ad)
```
注意 --  连字符 是英文状态下的切记
Install semanage tools: sudo yum -y install policycoreutils-python
Allow port 3221 for httpd: sudo semanage port -a -t http_port_t -p tcp 3221
Allow port 88 for httpd: sudo semanage port -a -t http_port_t -p tcp 88
Allow port 8445 for httpd: sudo semanage port -a -t http_port_t -p tcp 8445
```
扩展
[Listen](https://httpd.apache.org/docs/trunk/bind.html) [nmap-command](http://www.tecmint.com/nmap-command-examples/)

 

```
增加刚才分配给 Apache 的端口通过防火墙，然后重新加载防火墙。

允许 http 服务通过防火墙(永久)。
	firewall-cmd  --zone=public --add-service=http  --permanent

允许 3221 8445号端口通过防火墙(永久)。80 8080 防火墙默认通过
	firewall-cmd --zone=public --add-port=3221/tcp --permanent
	firewall-cmd --zone=public --add-port=8445/tcp --permanent

now
/etc/httpd/conf/httpd.conf
Listen 80
Listen 3221
Listen 8445
重新加载防火墙。（LCTT 译注：关于 firewall 的进一步使用，请参照：http://www.linux.cn/article-4425-1.html ）

firewall-cmd --reload
完成上面的所有事情之后，是时候重启 Apache HTTP 服务器了，然后新的端口号才能生效。

	systemctl restart httpd.service
	echo -e "<?php\nphpinfo();\n?>"  > /var/www/html/phpinfo.php
	php /var/www/html/phpinfo.php 
	
	http://127.0.0.1:80/8080/3221/8445
	http://localhost:80/8080/3221/8445
	http://127.0.0.1:80/8080/3221/8445
	http://0.0.0.0:80/8080/3221/8445
	http://ip: 80/8080/3221/8445
	
	OR 
	如下图所示，用 links 命令行工具 验证 Apache HTTP 服务器。
        yum install links
	links 127.0.0.1
	links http://127.0.0.1/phpinfo.php
	
现在添加 Apache 服务到系统层使其随系统自动启动。
	systemctl start httpd.service
	systemctl enable httpd.service
	systemctl status httpd.service

```

```
 Installing Webmin
 wget http://prdownloads.sourceforge.net/webadmin/webmin-1.740-1.noarch.rpm
 rpm -ivh webmin-*.rpm
```

```
http://www.tecmint.com/things-to-do-after-minimal-rhel-centos-7-installation/2/
http://www.tecmint.com/install-lamp-in-centos-7/

Install MariaDB Database

MariaDB is a fork of MySQL. RedHat Enterprise Linux and its derivatives have shifted to MariaDB from MySQL. It is the Primary Database management System. It is again one of those tools which is necessary to have and you will need it sooner or later no matter what kind of server you are setting. Install MariaDB on CentOS Minimal Install server as below.

yum install mariadb-server mariadb
systemctl start mariadb.service
systemctl enable mariadb.service
firewall-cmd --add-service=mysql

Now it’s time to secure MariaDB server.
# /usr/bin/mysql_secure_installation
enter input passwd  
root and  passwd(Don't delect root user login)
now login
mysql -u root -p 
```

# [FirewallD Configuration](http://www.tecmint.com/things-to-do-after-minimal-rhel-centos-7-installation/3/)

```
To disable firewalld.
# systemctl stop firewalld
# systemctl disable firewalld
# firewall-cmd --state

To enable firewalld.
# systemctl enable firewalld
# systemctl start firewalld
# firewall-cmd --state

# systemctl status firewalld
OR
# firewall-cmd --state


Get a list of all the zones.
# firewall-cmd --get-zones



To get details on a zone before switching.
# firewall-cmd --zone=work --list-all

To get default zone.
# firewall-cmd --get-default-zone

To switch to a different zone say ‘work‘.
# firewall-cmd --set-default-zone=work
Swich Firewalld Zones

To list all the services in the zone.
# firewall-cmd --list-services

To add a service say http, temporarily and reload firewalld.
# firewall-cmd  --add-service=http
# firewall-cmd --reload

To add a service say http, permanently and reload firewalld.
# firewall-cmd --add-service=http --permanent
# firewall-cmd --reload

To remove a service say http, temporarily.
# firewall-cmd  --remove-service=http
# firewall-cmd --reload

To remove a service say http, permanently.
# firewall-cmd --zone=work --remove-service=http --permanent
# firewall-cmd --reload

To allow a port (say 331), temporarily.
# firewall-cmd --add-port=331/tcp
# firewall-cmd --reload

To allow a port (say 331), permanently.
# firewall-cmd --add-port=331/tcp --permanent
# firewall-cmd --reload

To block/remove a port (say 331), temporarily.
# firewall-cmd --remove-port=331/tcp
# firewall-cmd --reload

To block/remove a port (say 331), permanently.
# firewall-cmd --remove-port=331/tcp --permanent
# firewall-cmd --reload

```




`
