
# Introduce
  * http://www.cnblogs.com/glaivelee/archive/2009/10/07/1578737.html & [__1__](http://blog.csdn.net/it_man/article/details/2048638)&[__2__](http://www.jb51.net/article/5828.htm)
  * [shutdown.bat](http://dramatea.github.io/043%20%E6%89%B9%E5%A4%84%E7%90%86%E6%96%87%E4%BB%B6%EF%BC%9AWin7_%E5%AE%9A%E6%97%B6%E5%85%B3%E6%9C%BA%E5%B7%A5%E5%85%B7.bat.html) & [ds_shutdown](http://dongshao.net/441.html)
  * [wifi.bat](http://blog.csdn.net/powerlly/article/details/9006969) &[ds_wifi](http://dongshao.net/1197.html)

```
1:定点关机
下午2：10准时关机你可以输入如下命令：

at 14:10 shutdonw  -s  回车

直接输入at，查看所有计划任务的id:

取消单个任务:

at id /delete

id为数字，需自己指定

如您使用at查看到当前计划任务关机的id 为1，则输入：

at 1 /delete 就可以取消计划任务1了

取消所有任务:

at /delete /yes 

要1小时之后关闭电脑

2.倒计时关机
shutdown -s -t 3600 （单位是秒，3600等于一小时）

(也可以这样写shutdown -f -s -t 3600 ,-f代表强制运行的应用程序关闭而没有警告)

shutdown -a 可以终止定时关机命令
```
