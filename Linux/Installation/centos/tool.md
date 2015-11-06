
# [Enable Third Party Repositories](http://www.tecmint.com/things-to-do-after-minimal-rhel-centos-7-installation/4/) --启用第三方软件库

[EPEL--Extra Packages for Enterprise Linux](http://freeloda.blog.51cto.com/2033581/1260824)

```
 yum install epel-release
 rpm -Uvh http://www.elrepo.org/elrepo-release-7.0-2.el7.elrepo.noarch.rpm
``` 
  下列软件都属于第三方软件
* yum install p7zip
* yum install vsftpd
* yum install ntfs-3g 
 * [维基介绍](https://zh.wikipedia.org/wiki/NTFS-3G)
 [1](http://www.ha97.com/2832.html)     [2](http://linux.ximizi.com/linux/linux2708.htm)
 [NTFS](https://zh.wikipedia.org/wiki/NTFS)     [FAT32](https://zh.wikipedia.org/wiki/FAT#FAT32)    [NetBIOS](https://zh.wikipedia.org/wiki/NetBIOS)
```
我没怎么搞明白centos7怎么在虚拟机挂在 本地磁盘 
于是在 本地计算机->管理>磁盘管理->压缩卷->新建 （I盘NTFS） （H盘FAT32 ）设成分享磁盘 权限 完全控制
或设置新建文件夹设成共享
ifconfig 虚拟机 
ipconfig 本地计算机

查看IP
ping Ip 测试

在Connect to serve smb://192.168.179.1/
输入本地计算 用户名密码 即可实现怎删改查
```
在命令行实现访问共享磁盘文件 并未实现 （建议可跳过）
[smbclient -L 192.168.100.111 -U 本地计算机名](http://www.dabu.info/linux_virtual_machine_vm_on_shared_windows_folder.html)

[2](http://sonice.blog.51cto.com/994545/217451)

[3](https://www.samba.org/samba/docs/man/manpages/smbclient.1.html)



  

