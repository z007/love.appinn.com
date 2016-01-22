
# 如何用 ISO 镜像制作 U 盘安装盘（通用方法、无需 WinPE）

* [iso files](http://baike.baidu.com/view/138403.htm)
 * [DAEMON Tools](http://www.disk-tools.com/download/daemon)
 * [ultraiso](https://www.ezbsystems.com/ultraiso/)
* [gho](http://baike.baidu.com/view/704362.htm)
 * [gho files](http://baike.baidu.com/view/3932614.htm)
 
## Windows System setup

### CD/DVD/CCD-RM Drive
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

* CD ghost 即光盘装PE做ghost
 * F12 进入选择CD/DVD/CCD-RM Drive 只按  一     次回车键 切记 回车按一次以上就从硬盘启动
 * 如果无法做ghost 是因为 电脑硬盘太高级了 CD ghost 盘 只可以适合较低级的硬盘
  * [AHCI, ATA, RAID 比较](http://jaseywang.me/2013/04/19/ahci-ata-raid-%E6%AF%94%E8%BE%83/)
  * 解决方式是改变硬盘模式为 ATA F2->System Configuration->STAT Opeation->ATA 
  * 图片参照[F2](https://cloud.githubusercontent.com/assets/8462060/12504289/d2f38fa4-c116-11e5-88fd-8e8df1e9c4c7.jpg)[F12](https://cloud.githubusercontent.com/assets/8462060/12504288/d2f04fba-c116-11e5-89e0-46942bf0de01.jpg)
   * 但是又会出现问题 原先的系统不可以用了 选备份的ghost 不可以用了 ，因为原来你模式是AHCI 模式
   * 不推荐这个么做

#### CD 文件复制出来 激活优盘安装
##### [什么是系统分区和启动分区](http://windows.microsoft.com/zh-cn/windows/what-are-system-boot-partitions#1TC=windows-7)


###### [活动分区](https://zh.wikipedia.org/wiki/%E6%B4%BB%E5%8A%A8%E5%88%86%E5%8C%BA)

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
