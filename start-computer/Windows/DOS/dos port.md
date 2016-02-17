windows 端口被占用解决办法
from
>进入cmd命令，输入netstat -ano 即可看到所有连接的PID， 之后在任务管理器中找到这个PID所对应的程序。


假如我们需要确定谁占用了我们的8008端口，在windows命令行窗口下执行： 

 >> netstat -ano|findstr 8008 
       输出结果为：TCP    127.0.0.1:8083         0.0.0.0:0              LISTENING       5888

这表明端口被进程号为5896的进程占用，继续执行下面命令： 

>>tasklist|findstr "5888"
notepadr.exe           5896 Console                 0     18,152 K
说明SogouExplorer.exe占用了你的端口。 
