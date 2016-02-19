1. color ?
```
设置默认的控制台前景和背景颜色。
颜色属性由两个十六进制数字指定 -- 第一个为背景，第二个则为
前景。每个数字可以为以下任何值之一:

    0 = 黑色       8 = 灰色
    1 = 蓝色       9 = 淡蓝色
    2 = 绿色       A = 淡绿色
    3 = 浅绿色     B = 淡浅绿色
    4 = 红色       C = 淡红色
    5 = 紫色       D = 淡紫色
    6 = 黄色       E = 淡黄色
    7 = 白色       F = 亮白色
    
    例如: "COLOR fc" 在亮白色上产生亮红色
```
2. [fsutil](https://technet.microsoft.com/en-us/library/cc788058.aspx)
```
fsutil file createnew 创建一个指定大小的新文件
用法 : fsutil file createnew <文件名> <长度>
例如 : fsutil file createnew C:\testfile.txt 1000
```
3. 网络命令
* [nslookup 和dos 常用网络命令](https://github.com/z007/love.appinn.com/blob/d6b7b18c17c04713f8c45289af7b665d926edfc2/Linux/Installation/Windows-Server/Windows%20Server%202012%20R2.md)
* [DOS下常用网络命令技巧](http://blog.csdn.net/xumin07061133/article/details/7506045)
```
nslookup baidu.com 8.8.8.8
nslookup baidu.com
ARP –a
Tracert baidu.com
```
