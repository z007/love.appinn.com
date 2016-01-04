* [hashlib](http://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000/0014319556588648dd1fb0047a34d0c945ee33e8f4c90cc000)
* [python的md5和sha1加密](http://www.cnblogs.com/the4king/archive/2012/02/06/2340660.html)

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
import hashlib

x = hashlib.md5()
x.update('hello, '.encode('utf-8'))
x.update('python'.encode('utf-8'))
print(x.hexdigest())

print(hashlib.md5('hello, python'.encode('utf-8')).hexdigest())
```
