# 2015-12-25python3常用内置模块datetime

```
ST3 = sublime3
ND = 难点
P1>P2>P3>P4>P5 未解决问题优先级
```
* Issue
	* [Decode error - output not utf-8](http://blog.csdn.net/lhshu2008/article/details/18735827)

``` python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
# "%Y-%m-%d %H:%M:%S.%f
# 1秒=1000毫秒=1000 000微秒

# 精简 python 日期计算2 句 
# 缺点手动该脚本日期
# http://day.9om.com/ --javascript  计算
# 想找到方法 python x.py 输入日期 得出结果 但是datetime()参数是 需要时常量指定整数 交互式输入 使用input()不行 --P5
# from  datetime import datetime , timedelta 
# print(datetime.now() - datetime(2012, 12, 21) + timedelta(days=1))


# 详细  讲datetime.timedelta(1100, 61, 650691) # ND 倒数第二个参数为秒(天,秒，微秒) 
# now = datetime.now() now是一个定值,以后的now都是以上一个now = datetime.now()

from  datetime import datetime , timedelta 
now = datetime.now()
print(now)
print('--------------------')
# love = datetime(2011, 12, 21, 1 , 8 , 12, 123456)
love = datetime(2012, 12, 21)
print(now -love +  timedelta(days=1))
print(datetime.now() - datetime(2012, 12, 21) + timedelta(days=1))

# print('---------for 隔开两次输出时间差()无用 还是用sleep --汉字ST 输出[Decode error - output not utf-8]---P3------')

# for letter in 'Python':     # 第一个实例
#    print('shun:', letter)
print('---------sleep 5s-----------')
import time
# print("Start : %s" % time.ctime())
time.sleep( 5 )
# print("End : %s" % time.ctime())
print('--------------------')
print(now)
now = datetime.now()
print(now)
print('--------------------')
print(datetime.now())
print('--------------------')
print(datetime.now() - datetime(2012, 12, 21) + timedelta(days=1))


[do_input.py](https://github.com/michaelliao/learn-python3/blob/master/samples/basic/do_input.py)

# >>> print(datetime.now() - datetime(2012, 12, 21))
# 1100 days, 00:01:01.415621
# >>> datetime.now() - datetime(2012, 12, 21)
# datetime.timedelta(1100, 61, 650691) # ND 倒数第二个参数为秒(天,秒，微秒)
```

1.datetime

```
python 3.5.1 (v3.5.1:37a07cee5969, Dec  6 2015, 01:38:48) [MSC v.1900 32 bit (Intel)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> from datetime import datetime
>>> dt = datetime(2015, 4, 19, 12, 20) # 用指定日期时间创建datetime
>>> dt.timestamp() 
1429417200.0
>>> now = datetime.now()
>>> now.timestamp()
1451055348.246042
>>> 

# dt.timestamp()

# ND 产生 AttributeError: type object 'datetime.datetime' has no attribute 'datetime' 2点原因·

------1多版本共存 使用dt.timestamp()------timestamp() 是python3(这里简称3.x)常用内置模块的函数-----------------------
使用2.7版本出现错误（AttributeError: type object 'datetime.datetime' has no attribute 'datetime'）
安装3.x 环境变量为3.x 也不行 （多版本共存可能导致此问题）
（https://www.python.org/shell/ 是可以环境3.x））
2.7完全卸载重启安装3.x OK


timestamp() 3.x内置模块函数

timestamp
>>> import time
>>> time.time()  #2.7 time() 可以
1421075455.568243

PYTHON-基础-时间日期处理小结
http://www.wklken.me/posts/2015/03/03/python-base-datetime.html#
------------------------2书写错误多余语句----------------
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

from datetime import datetime
now = datetime.now()
print(now)
datetime.datetime(2015, 5, 18, 17, 2, 10, 871012) # 此句多余

AttributeError: type object 'datetime.datetime' has no attribute 'datetime'
http://stackoverflow.com/questions/12906402/type-object-datetime-datetime-has-no-attribute-datetime
```
