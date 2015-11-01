# Windows、Ubuntu双系统重装windows系统后grub引导的修复及默认启动项的修改

```
装了个windows，之后重新引导了Ubuntu，下面记录下：
gurb引导的修复：
     1、拿一个Ubuntu系统U盘或者光盘，没有的话去烧一个，如何烧点此文。
     2、重启进入U盘或光盘启动，选择实用Ubuntu（try ubuntu）。
     3、查看信息。打开终端（ctrl+alt+t），在终端下输入
[plain] view plaincopy 
sudo -i（获得管理员权限）  
fdisk -l（查看分区及类型）  
     然后会出现你的磁盘的信息。
[plain] view plaincopy 
Device    Boot    Start   End Blocks    Id   System   
     在Id列找出83的那行对应的Device列的内容，看看是sda多少的，下面假设为sda*。（假如有多个Id为的83分区，可以从后面一个一个尝试4-6步）。
     4、挂载分区。在终端输入（注意*的替换和空格）：
[plain] view plaincopy 
mount /dev/sda* /mnt  
     5、在终端输入：
[plain] view plaincopy 
grub-install --root-directory=/mnt /dev/sda  
稍等片刻便能看到：Installationfinished,No Error Reported的字样，说明设置成功了。
     6、重启电脑就能看到Ubuntu的grub引导界面了，如果没有请返回第3步看看是否有多个Id为83的分区。
     7、此时先别进入windows，进入Ubuntu在终端中输入：
[plain] view plaincopy 
sudo update-grub  
     执行完重启电脑就可以正常进入windows和Ubuntu了，这时grub引导算修复完毕。

grub默认启动项的修改
     那位同学还要求把默认启动项给改回windows。。。（这样一学期能进几次Ubuntu。。。）
     在启动时记住windows是在启动项的第几行。
     进入Ubuntu，在终端上输入：
[plain] view plaincopy 
sudo gedit /boot/grub/grub.cfg  
     将set default="0"上面的0改为刚才看到的windows在第几行减一。
     保存退出，重启即可。
```
