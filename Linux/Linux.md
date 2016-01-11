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
* http://vbird.dic.ksu.edu.tw/linux_basic/0320bash_1.php --鸟哥
* http://www.linux.com/
* http://www.linuxandubuntu.com/
* http://www.tecmint.com/
* http://www.centoscn.com/
* http://linux.vbird.org/
 * http://book.51cto.com/art/201007/211888.htm
 * http://study-area.org/menu2.htm
 * http://study-area.org/menu1.htm
 * http://phorum.study-area.org/index.php



# use 
* https://chusiang.gitbooks.io/working-on-gnu-linux//
* https://craftsmanbai.gitbooks.io/linux-learning-wiki/content/index.html
* http://www.codeceo.com/article/linux-productive-tools.html

# 如何用 ISO 镜像制作 U 盘安装盘（通用方法、无需 WinPE）

```
1.
一台新电脑有200G硬盘空间  
装系统分区时给系统盘（默认C盘）100G   
会出现 100M 和 102300M 两个分区（100M分区在前）  
删除102300M分区将100M分区扩展添加102300M就到了一个100G系统分区  
为什么不能删除100M分区在102300M分区在扩展100M因为系统分区只可向   后*  扩展100M分区在前  
2.
 剩余100G分个D盘  
3. ghost 备份直接备份系统盘这时不存在单独的100M问题
4.重装系统时直接格式化系统盘就可以，如果删除系统盘重新建记得100M盘扩展删除102300M盘  

```
* https://program-think.blogspot.com/2013/12/create-bootable-usb-stick-from-iso.html
* http://rufus.akeo.ie/
* https://unetbootin.github.io/
* http://www.chrysocome.net/dd
* [ghost 备份](http://www.upanok.com/jiaocheng/15.html)
* [ghost 还原](http://jingyan.baidu.com/article/4ae03de34c73bb3efe9e6b57.html)

~~未 合并100M盘时系统盘C 102400M 备份时C盘时 备份时 选择  boot 100M 和余下102300M 
还原时 只需还原102300M 那个分区即可~~
````
最后一步
conture 继续 回到启动盘环境
reset computer 重启计算机 
```




#[什么是系统分区和启动分区](http://windows.microsoft.com/zh-cn/windows/what-are-system-boot-partitions#1TC=windows-7)


## [活动分区](https://zh.wikipedia.org/wiki/%E6%B4%BB%E5%8A%A8%E5%88%86%E5%8C%BA)

 * Diskpart 
  * http://toutiao.com/a4037286912/
  * https://support.microsoft.com/zh-cn/kb/300415
  * http://www.cnblogs.com/joey0210/archive/2012/08/24/2654289.html
  * http://jingyan.baidu.com/article/92255446efce49851748f463.html
  ```
 激活分区
    活动分区是指用以启动操作系统的一个主分区。一块硬盘上只能有一个活动分区。
    要将当前分区设置为活动分区，点击工具栏按钮“激活”，或点击菜单“分区 -   激活当前分区”项，
    也可以在要激活的分区上点击鼠标右键并在弹出菜单中选择“激活当前分区”项。
    如果其它分区处于活动状态，将显示下面的警告信息：
   
    0. 前提格式化 在做激活 而且是Window 系统文件  
    1.系统分区激活
     把系统文件复制到已经激活的分区的 根 目录（如C盘必须放在C盘根目录）（激活复制文件通过 U盘进入执行）
    2.U盘激活复制系统文件安装（同理可激活U盘）系统文件U盘根目录
    3. 系统文件DVD/IOS文件提取工具daemon-tools (support\文件夹   upgrade\文件    autorun.inf    setup.exe  可以不复制)
    
    
  总结：
  1.只要推荐 激活U盘
  系统文件已经提取 激活U盘直接安装 复制系统文件到U盘根目录 直接安装   
 ```
 * [daemon-tools](http://www.daemon-tools.cc/chn/products/compare)
 
 ![window system setup files](https://cloud.githubusercontent.com/assets/8462060/12226395/4de0ed3e-b856-11e5-9282-6763c25c3d62.png "window system setup files")

 
* [认识主分区,活动分区,扩展分区和逻辑分区](http://www.disktool.cn/jiaocheng/basic-partition.html)

# 文件备份技巧：组合“虚拟加密盘”和“网盘”
* https://program-think.blogspot.com/2013/07/online-backup-virtual-encrypted-disk.html
* http://www.hjsplit.org/windows/

# Download
 * [GetUbuntuGNOME/LTS](https://wiki.ubuntu.com/UbuntuGNOME/GetUbuntuGNOME/LTS)
 * [Ubuntu](http://www.ubuntu.org.cn/index_kylin)


# Software 
* [Input](http://www.zhihu.com/question/19839748)
* [Squirrel](http://forrestchang.github.io/2015/10/31/squirrel-recommended/?hmsr=toutiao.io&utm_medium=toutiao.io&utm_source=toutiao.io)




# 坑
 * Inter i5-4590 Windowx64 VM11 安装 linux **amd镜像 极不稳定 kalilinux 安装完成重启无法启动 gnome 使用halt命令 关机无法关机直接死机**(kali-linux-2.0-amd64.iso ubuntu-gnome-14.04.3-desktop-amd64) 
 * 建议Inter cpu 别装 AMD镜像 & 每个环境都不同& 偶然性重装系统之前还挺好的 **i86镜像较稳定**
 * Kalilinux 虚拟机 [VMware Images](https://www.offensive-security.com/kali-linux-vmware-arm-image-download/)推荐
  *  Default root Password toor
