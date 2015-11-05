[From CSND](http://blog.csdn.net/back_to_dream/article/details/6707049)

```
一、常用DOS命令
FDISK（硬盘分区） 外部命令
FORMAT（磁盘格式化） 外部命令
CHKDSK（磁盘检查） 外部命令
磁盘操作类 DISKCOPY（全盘拷贝） 外部命令
DISKCOMP（全盘比较） 外部命令
VOL（显示磁盘卷标） 内部命令
LABEL（建立卷标） 外部命令
F: 改变盘符
目录操作类 MD（建立目录） 内部命令RD（删除目录） 内部命令CD（显示/更改目录） 内部命令DIR（显示目录）内部命令PATH（路径设置） 外部命令TREE（显示目录结构） 外部命令

COPY（拷贝文件） 内部命令
COMP（文件比较） 外部命令
DEL（删除文件） 内部命令
文件操作类 RENAME（文件改名） 内部命令
TYPE（文件内容显示） 内部命令
BACKUP（磁盘备份） 外部命令
RESTORE（备份文件恢复） 外部命令
EDIT（编辑器） 外部命令

CLS（清屏幕） 内部命令
DATE（系统日期设置） 内部命令
其 它 TIME（系统时间设置） 内部命令
VER（显示版本号） 内部命令
PROMPT（设置系统提示符） 内部命令

二、DOS命令分类

（一）DOS中的命令分三种：内部命令、外部命令和批处理命令。
1.内部命令：内部命令包含在C:\Windows\COMMAND.COM文件中。
2.外部命令：以文件形式存在于硬盘C:\Windows\COMMAND文件夹中，需读入才能操作。常用.COM，.EXE，.BAT扩展名。该文件夹包括DOS7.1的所有外部命令。
（二）DOS按执行方式可分为配置命令与非配置命令。
配置命令一般不能在DOS命令行中直接执行，而只能放在CONFIG.SYS文件中在DOS启动时执行，配置命令主要用于装入设备驱动程序，更改操作系统参数的默认值等。
非配置命令可在DOS命令行直接执行，也可以放在批处理文件（.BAT文件）中执行。
三、如何进入和退出DOS
DOS主要由IO.SYS、MSDOS.SYS、COMMAND.COM三个模块组成。
1.在Windows下进入DOS
打开开始/程序/MS-DOS方式，可进入窗口DOS方式。或打开C:\Windows\COMMAND.COM或其快捷方式。完成操作后，用EXIT命令，或用x退出。
在开始/运行中键入COMMAND，可进入全屏DOS实模式，用EXIT退出。
2.进入纯DOS
可在Windows下重启进入MS-DOS方式，或在开机时按F8（不断点击），选择启动菜单的Command prompt only。进入纯DOS状态加载全部支持WIN启动的DOS驱动程序。退出时用WIN命令进入桌面或RESET键重启。
第二章 DOS常用命令
一、磁盘操作类命令
1.硬盘分区 FDISK：可将新硬盘分为主分区（C区）、扩展分区（在里面可建立D、E、F等逻辑磁盘）。由于MSDOS6.22所带的FDISK不支持2GB以上FAT32格式的分区，所以一般用Windows9x下的FDISK。FDISK不支持NTFS等非DOS分区的创建，且只能创建唯一的主分区，这是它在当前多种操作系统共存的情况下，逐渐被大家遗忘的主要原因。
2.磁盘格式化 FORMAT [盘符] [/S] [/V] [/N] [/T]
/S装入DOS系统文件，/V输入卷标。FORMAT A: /S可制作较简单的启动盘来刷新BIOS。
3.磁盘检查 CHKDSK [盘符] [路径] [文件名] [/F] [/V]
/F纠正逻辑错误，/V显示所有目录和文件。
4.全盘复制命令 DISKCOPY [盘符1] [盘符2] 1→2
5.全盘比较 DISKCOMP [盘符1] [盘符2]
6.显示磁盘卷标 VOL [A:]
二、目录类命令
1.改变盘符 F：
2.显示或改变当前目录 CD [C:] [path] CD\ CD..
3.建立子目录 MD [C:] path
4.删除子目录 RD [C:] path RD\RS\CB
先需删除文件 DEL A:\RS\CB\*.*
5.查看目录 DIR [C:] [path] [filename] [/P] [/W] [/B] [/S] [/A] [/O]
/P逐屏 /W每行五个 /B每行一个 /L 小写英文 /S所有子目录内容
/A文件属性（H显示隐含文件 －H不显示 S显示系统文件 D显示目录 A存档文件 R只读文件 如 /A：H）
/O排序方式（N按字典次序 －N反英文次序 E扩展名字序 D建立日期先后 S文件大小 G目标在文件名前如/O－N，/O：GE）
6.路径设置命令 PATH [C:] path {;[D:] path ……}
只能寻找扩展名为 .EXE ,.COM,.BAT 可执行文件。
7.显示磁盘目录结构命令 TREE 凵[C:] [/F] /F显示所有文件
三、文件操作类命令
1.文件拷贝 COPY [C:] [path] filename[+……]凵[D:] [path] [文件名2] [/V]
/V 在复制的同时校验文件。
COPY CON C.BAT 键盘输入内容，Ctrl+Z或F6回车后存盘。
COPY C.BAT PRN 输出到打印机。
2.文件比较 COMP [C:] [PATH] file1凵[D:] [path] file2
3.删除文件 DEL|ERASE [C:] [path] filename [/P]
/PDOS询问是否删除。
4.文件改名 REN|RENAME [盘符] [路径] 文件名1凵文件名2
5.显示文件内容 TYPE [盘符] [路径] 文件名[＞PRN]
＞PRN 打印，文件必须是ASCⅡ码。
6.磁盘文件备份命令 BACKUP 盘符1 [路径] [文件名] 凵盘符2[/S][/M][/A][/F]
/S所有文件，/M修改过才备份，/A不删除目标盘文件，/F复制前格式化。
7.备份文件恢复命令 RESTORE C: [D:][PATH][ FILE][ /S][/P][/M][/N]
/S所有文件，/P修改文件，/M备份后改变的文件，/N恢复不存在的文件。
8.编辑文件 EDIT 可实现改写内容和改名。
四、其它命令
1.清屏命令 CLS
2.系统日期显示与设置命令 DATE [mm-dd-yy]
3.系统时间显示与设置命令 TIME [hh:mm:ss]
4.改变系统提示符命令 PROMPT
5.显示操作系统版本号命令 VER
6.显示系统环境变量命令SET
7.输出重定向符> 作用是改变计算机的输出方向，格式：
DOS命令 > 输出对象名（显示器、磁盘文件、打印机PRN等）如
dir c:\/a/s > c:\list.txt DOS命令/? > help.txt （输出到文件）
五、高级DOS命令
1.指定数据文件查找路径命令 APPEND [盘符][路径][；盘符 路径……]
APPEND； 清除数据文件的路径。
2.驱动器转移命令 ASSIGN A=B A→B
3.设置或修改文件属性命令 ATTRIB[±R][±A][±H] [±S]文件名[/S]
+R只读属性 －R去除只读 +A档案+H隐含+S系统－S去除/S所有文件
（可用TYPE查看）
4.扩展复制命令 XCOPY [C:][PATH][源file] 凵[D:][PATH][GOALFILE]
[/A][/D][/E][/M][/P][/S][/V] /A对档案文件，/D指定日期以后，/E与/S配合拷贝空子目录，/M同A但会去除档案属性，/P询问（Y|N），/S拷贝所有文件与子目录，/V所有扇区校验。
5.驱动器移植命令 JOIN [盘符] 凵[盘符 路径][/D]
/D解除驱动器与子目录的挂接。
6.环境变量设置命令 SET [变量=字符串]
7.后台打印命令 PRINT[/D:device][盘符][路径]文件名[/T][/C][文件/P]
/T将打印列表删除，/C删除某个文件至/P为止，/P加入文件（默认）。
8.系统传输命令 SYS [盘符]
将系统文件IO.SYS 、MSDOS.SYS和COMMAND.COM拷贝到*盘根目录。
9.联机帮助命令 HELP [命令名] 或 命令名/？
获得DOS命令的功能说明。
10.调试程序DEBUG 汇编爱好者可用之修复硬盘主引导记录MBR和DOS引导记录DBR。
11.新增命令
⑴. START [选项] 程序 [参数] 选项如下：
/m[inimized] 在（后台方式下）运行程序，且窗口为最小化状态
/max[imized] 在（前台方式下）运行程序，且窗口为最大化状态
/r[estored] 在（前台方式下）运行程序，且窗口设为复原状态
/w[ait] 等到有了别的程序存在，才返回该程序
如果没有指定选项，那么默认为/r
⑵.内部命令LOCK和UNLOCK
这两个命令的作用在于对磁盘驱动器进行锁定和解锁。使之允许或禁止应用程序直接访问磁盘。在Windows98中，一般不允许应用程序进行直接磁盘访问。如，在使用UNDELETE命令之前，务必先使用LOCK命令进行磁盘锁定。
12.显示系统保留内存的容量MEM
13.EXIT：退出正在运行的程序。
六、批处理子命令（建立COPY CON C:\*.BAT 或EDIT 存盘）
1.开放/禁止屏幕显示子命令 ECHO [ON/OFF/message]
/ON:显示之后所有命令，/OFF不显示，message显示指定字符串。
2.注释子命令 REM [message]
3.暂停子命令 PAUSE [message]
 
 
 
 

 





UID 355436
七、DOS的系统配置由CONFIG.SYS文件来描述。
第三章 Windows命令
一般在开始/运行处执行。
一、系统命令
Windows的各种命令一般在C：和C：\Windows中。在GUI下进入DOS实模式，可打开C:\Windows\COMMAND.COM或其快捷方式，但许多命令不支持。通过重启进入DOS较好。
1.scanreg 注册表检查程序（在C:\Windows\command中）
在DOS 下键入scanreg，进入程序操作界面。scanreg.exe可修复注册表的错误，从备份文件C:\Windows\Sysbckup\rb001-005.cab中选择恢复注册表。命令参数如下：
/backup 立即备份注册表
/restore 按照备份的时间和日期显示所有备份文件进行恢复
/comment 在/restore中显示同备份文件有关的部分
/fix 修复注册表文件的错误
例：scanreg/restore 恢复注册表
scanreg.ini文件是注册表检查程序的配备文件，可设置相关参数。在Windows视窗中实用scanregw.exe，会自动在每天首次开机时扫描注册表并备份，位于msconfig启动项中。如果你忘了备份，那么赶快键入scanreg/Opt，它也能保证你重新恢复系统，但必须进入存放scanreg的目录。？
在Windows“运行”中键入scanregw.exe,会启动注册表检查器。在Windows启动时自动执行scanregw.exe/autorun。
2.注册表编辑器regedit（在C:\Windows中）（用处少）
在DOS下可以引入和导出注册表文件。命令如下：
⑴.Regedit [/L:system][/R:user]/E file.reg [regpath] 导出注册表文件
/L:指定system.dat文件所在的路径，/R:指定user.dat文件所在的路径。如果没有/L/R参数，就会在默认的路径（C:\Windows）下寻找。/E表示导出。可选项regpath是指定要导出哪个分支。例，我们要将保存在C:\Windows\system.dat和保存在C:\Windows\Profiles\User.dat中关于控制Windows98启动项目的分支导出到test.reg里，命令如下：
Regedit/L:C:\Windows\/R:C:\Windows\Profiles\/e test.reg HKEY LOCAL MACHINE\Software\Microsoft\Windows\CurrentVersion\Run
⑵.Regedit [/L:system][/R:user]file.reg 引入注册表文件
⑶.Regedit [/L:system][/R:user]/C file.reg 重建注册表。所指定的.reg文件应包含注册表的全部内容。
⑷.Regedit [/L:system][/R:user]/D regpath 删除注册表分支
在Windows下，双击一个注册表文件会弹出确认对话框，将之导入注册表。运行C:\Windows\regedit.exe/s c:\ file.reg则不会出现对话框。（勿用）
3.图形界面（GUI）启动命令WIN（用得少）
WIN.COM是DOS和GUI的接口命令。各参数主要用于确定系统故障，会使系统性能降低：WIN[/D:[F][M][S][V][X]]
/D 当Windows不能正常启动时用于查找故障原因
/F 关闭32位磁盘访问方式
/M 以安全模式启动到WINDOWS 。WIN/W和WIN/M这两个参数的作用基本一样，可以实现在DOS模式下让计算机重新启动（软重启）唯一不同的是，使用/W会提示按任意键后重启，使用/W则直接重启
/N 以网络安全模式启动到WINDOWS，比WIN/M参数多了网络功能
最有意思的是WIN/Z这个命令（使用/Z参数），使用它可以实现DOS模式下的软关机，当输入WIN/Z后，按任意键，WINDOWS会立即关闭计算机，这样就不必用手去按电源开关了。/z参数是用 win /?查不到的。
4.将路径虚拟为盘符subst 如subst a: d:bios 表示将D盘的BIOS文件夹虚拟为A盘。
5.系统文件检查器SFC
在Windows下运行SFC（位于C:\Windows\system\sfc.exe），可对系统文件检查和安装，显示添加、更改和删除的文件日志。由于安装应用程序时常会自动更改，没有必要对系统文件还原。
6.HD-Copy 整盘复制？用于修复数据。
7.在DOS下制作启动盘：只要使用保存在C:\Windows\Command目录下的bootdisk.bat文件就可以解决。
8.恢复在DOS模式下删除的文件：在开始/程序/MS-DOS方式的DOS命令符下运行“Lock”命令，在出现“Are you sure(Y/N)?”提示信息时按“Y”键后，按回车键，就解除了Windows对磁盘访问的限制，执行命令“Undelete”。
9.整合升级文件命令msiexec：例 msiexec /p 升级文件.msp /a 原文件.msi SHORTFILENAMES=TRUE /qb 可将升级程序SP1等整合到OFFICE XP安装程序中。
10.系统配置实用程序msconfig：可以选择启动时运行的程序，需要的就打勾。但有些后台程序不会显示出来。可打开注册表HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run将不需要的程序删除。
二、应用程序DOS命令
1.FBDISK：32KB。一款优秀的处理有坏扇区硬盘的分区软件。对购买二手硬盘的朋友是不错的磁盘扫描程序。即使是用Pqmagic隐藏的分区也无法逃脱检查。
2.Windows NT中的Net命令是一个功能强大的工具。在命令行方式执行，它的功能覆盖了NT中大部分重要的管理功能。它可以管理网络环境、各种服务程序的运行和配置、进行用户和登录管理等。Windows98中虽然也有NET命令，但功能却少得多。下面简单的介绍一下NET命令的部分用法：
⑴.用户账号管理 NET USER / NET ACCOUNTS / NET GROUP /
NET LOALGROUP
⑵.有关机器和会话的信息管理 NET COMPUTER / NET CONFIG /
NET SESSION
⑶.建立与网络设备的连接 NET VIEW /NET USE / NET SHARE
⑷.发送信息 NET NAME / NET SEND /
⑸.帮助 NET HELP / NET HELPMSG
3.关机命令：在运行中键入“C:\Windows\rundll32.exe user.exe,exitWindows”。或者在桌面建立快捷方式，运行上述文件内容，或使用计划任务进行定时关机。
第四章 网络命令
一、ipconfig
用来查询本机的IP地址、子网掩码、默认网关等信息。还可用来诊断一些Win2000的网络故障。如 ipconfig/all>c:\*.txt，可将显示信息保存到C区的文件中。
二、tracert：能够追踪访问网络中某个节点时所走的路径。据说在查询Internet上某个节点访问路径的速度较慢，尤其是查询国外的网址。可采用软件VisualRoute以加快速度。
三、netstat：netstat –a可显示一些端口，如8225被打开，就中了灰鸽子病毒，要删除Kernel32.exe文件。
四、net
五、Telnet
六、显示IP地址 ping
拨号上网采用动态IP分配。直接访问网站的IP地址，可加快连接速度。可用本命令测试网络通信是否正常。
ping XXX（XXX为主机名或IP地址） 如：
pingwww.microsoft.com ， ping ftp.microsoft.com
另外，也可用winipcfg.exe来查看。
附录：常用DOS命令
1.改变盘符 X：
2.显示或改变当前目录 CD [盘符] [路径]
回到上级目录 CD\ 回到根目录 CD..
3.查看目录 DIR [C:] [path] [filename] [/P] [/W]
4.文件拷贝 COPY [C:] [path] filename[+……]凵[D:] [path] [文件名2]
5.修改文件属性命令 ATTRIB[±R][±A][±H] [±S]文件名
6.删除文件 DEL|ERASE [C:] [path] filename
7.显示文件内容 TYPE [盘符] [路径] 文件名
8.注册表导入 scanreg/restore
9.编辑文件 EDIT
10.退出 EXIT
11.进入WIN98 WIN（有时不好用）
12.显示IP地址 ping（winipcfg.exe）
```
