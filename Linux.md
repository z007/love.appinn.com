# Literacy Linux: How to Choose Release
https://program-think.blogspot.com/2013/10/linux-distributions-guide.html
# LINUX distributions
* [DistroWatch](https://en.wikipedia.org/wiki/DistroWatch)
  * http://distrowatch.com/
  * http://blog.chinaunix.net/uid-20328094-id-95186.html
  
# Community
* http://www.linuxidc.com/
* https://linux.cn/tech/
* http://blog.jobbole.com/tag/linux/
* http://vbird.dic.ksu.edu.tw/linux_basic/0320bash_1.php
* http://www.linux.com/
* http://www.linuxandubuntu.com/

# Command

* http://man.linuxde.net/
* [sudo passwd](http://jingyan.baidu.com/article/5225f26b0ac250e6fb09084e.html)
 * [Change sudo password timeout in Ubuntu](http://itsfoss.com/change-sudo-password-timeout-ubuntu/)
* https://linux.cn/article-6160-1.html
* [Linux mkdir、tar 和 kill 命令的 4 个有用小技巧](https://linux.cn/article-5863-1.html#3_3387)
* 

# use 
* https://chusiang.gitbooks.io/working-on-gnu-linux//
* https://craftsmanbai.gitbooks.io/linux-learning-wiki/content/index.html
* http://www.codeceo.com/article/linux-productive-tools.html

# 如何用 ISO 镜像制作 U 盘安装盘（通用方法、无需 WinPE）
* https://program-think.blogspot.com/2013/12/create-bootable-usb-stick-from-iso.html
* http://rufus.akeo.ie/
* https://unetbootin.github.io/
* http://www.chrysocome.net/dd
* [ghost](http://www.upanok.com/jiaocheng/15.html)

## DISK
* http://toutiao.com/a4037286912/
* https://support.microsoft.com/zh-cn/kb/300415
* http://www.cnblogs.com/joey0210/archive/2012/08/24/2654289.html
* http://jingyan.baidu.com/article/92255446efce49851748f463.html

# 文件备份技巧：组合“虚拟加密盘”和“网盘”
* https://program-think.blogspot.com/2013/07/online-backup-virtual-encrypted-disk.html
* http://www.hjsplit.org/windows/

# Download
 * [GetUbuntuGNOME/LTS](https://wiki.ubuntu.com/UbuntuGNOME/GetUbuntuGNOME/LTS)
 * [Ubuntu](http://www.ubuntu.org.cn/index_kylin)

# command
 * [Upgrade](https://www.kali.org/news/kali-linux-20-released/)

  ```
  apt-get update
apt-get dist-upgrade # get a coffee, or 10.
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

  
  
# Software 
 [Input](http://www.zhihu.com/question/19839748)


# security
 * http://open.freebuf.com/
 * http://www.freebuf.com/tools/75517.html
 * http://drops.wooyun.org/category/tips
 * http://www.jikexueyuan.com/course/intellegence/
 * http://edu.51cto.com/course/course_id-3195.html
 * http://www.metasploit.cn/forum.php?mod=viewthread&tid=1484

# 坑
 * Inter i5-4590 Windowx64 VM11 安装 linux **amd镜像 极不稳定 kalilinux 安装完成重启无法启动 gnome 使用halt命令 关机无法关机直接死机**(kali-linux-2.0-amd64.iso ubuntu-gnome-14.04.3-desktop-amd64) 
 * 建议Inter cpu 别装 AMD镜像 & 每个环境都不同& 偶然性 **i86镜像较稳定**
