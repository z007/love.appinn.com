1. [路由器](https://zh.wikipedia.org/wiki/%E8%B7%AF%E7%94%B1%E5%99%A8)
  1.  [无线路由器怎么设置](http://www.192ly.com/router-settings/fast/fw300r-router-settings.html)
  2.  [SSID](https://zh.wikipedia.org/wiki/%E6%9C%8D%E5%8A%A1%E9%9B%86_(%E6%97%A0%E7%BA%BF%E5%B1%80%E5%9F%9F%E7%BD%91)#.E6.9C.8D.E5.8A.A1.E9.9B.86.E6.A0.87.E8.AF.86.E7.AC.A6)
    2.1  [开启/关闭SSID广播](http://www.jb51.net/network/62893.html) --无线设备能自动搜索到SSID,禁止广播SSID，可以阻止有人来蹭网。但是直接输入SSID名称，添加密码依然可以连上。
  3.  [WDS 桥接](http://www.192ly.com/router-settings/tp-link/tl-wdr5600-v2-wds.html)
  4.  一台路由器拥有双网段，私有模式，会客模式? P3
    4.1 局域网不同网段通信? P3
  5.  [无线路由器的WAN DNS 和里面的DHCP DNS有何区?](http://bbs.csdn.net/topics/390954530)P3
    5.1 无线路由器DHCP DNS 作用是为连上此路由的局域网设备提供默认DNS服务，在他们默认使用自动获取动态DNS服务器。
    5.2 无线路由器的WAN DNS 默认不设置为ISP服务商提供，在路由器->网络参数->WAN设置->高级手动添加DNS
    
    ```
    个人理解 并亲自测试
    测试网址  www.dnsleaktest.com
   
    测试条件  gogle DNS 主选 8.8.8.8  备用 8.8.4.4  笔记本电脑 无代理
    
     结论：局域网设备比如笔记本上网，域名解析依次host ->本机DNS->无线路由器的DHCP DNS->无线路由器的WAN DNS
    1.
    本机DNS  8.8.8.8 8.8.4.4
    无线路由器的DHCP DNS 默认（不设置）
    无线路由器的WAN DNS  默认（ISP）
    
    Windows +R  ncpa.cpl  Enter
    右键禁用，然后启用
     ipconfig/all
     8.8.8.8 8.8.4.4
     www.dnsleaktest.com
     
    ===========》》》》》》》》》 ISP Google
    2.
    本机DNS  默认动态自动获取
    无线路由器的DHCP DNS  8.8.8.8 8.8.4.4
    无线路由器的WAN DNS  默认（ISP）
    
     Windows +R  ncpa.cpl  Enter
    右键禁用，然后启用
    ipconfig/all
     8.8.8.8 8.8.4.4
     www.dnsleaktest.com
    ===========》》》》》》》》》 ISP Google
    3.
    本机DNS  默认动态自动获取
    无线路由器的DHCP DNS 默认（不设置）
    无线路由器的WAN DNS   8.8.8.8 8.8.4.4
    
     Windows +R  ncpa.cpl  Enter
    右键禁用，然后启用
    ipconfig/all
     8.8.8.8 8.8.4.4
     www.dnsleaktest.com
    ===========》》》》》》》》》 ISP Google
    
    4.
    本机DNS  默认动态自动获取
    无线路由器的DHCP DNS 默认（不设置）
    无线路由器的WAN DNS  默认（ISP）
    
     Windows +R  ncpa.cpl  Enter
    右键禁用，然后启用
    ipconfig/all
     本地网关地址
     192.168.1.1
     0.0.0.0
     （这是通过路由器无线局域内网连接，稍后进行直接拔路由直接插家庭入网线，宽带连接（拨号连接）再试）P1
     
     www.dnsleaktest.com
    ===========》》》》》》》》》 使用网络的 ISP 
    
    注意：DNS测试条件变为 主选 google 8.8.8.8  备用阿里云 223.5.5.5
    DNS IPS 出现4种情况
    
    全部为使用网络的ISP
    全部为google
    大部分为你使用网络的ISP
    大部分为google 
    
    但是 
    大部分情况下就变了使用网络的ISP了 
    也可知道阿里云DNS !!!!!!!!!!!!!!!!!!!!!
    
   https://github.com/z007/love.appinn.com/blob/96cabf44d495dda1460e4802ee923cb511d7eb98/start-computer/network/DNS.md
    ```
  6.[LAN DNS](http://www.draytek.com.cn/support/FaqcontentShow.php?article_id=268)--局域网DNS服务
2. [网关](https://zh.wikipedia.org/wiki/%E7%BD%91%E5%85%B3)
3. [路由器和网关](https://www.freebsd.org/doc/zh_CN.UTF-8/books/handbook/network-routing.html)
4. [网络地址转换 NAT](https://zh.wikipedia.org/wiki/%E7%BD%91%E7%BB%9C%E5%9C%B0%E5%9D%80%E8%BD%AC%E6%8D%A2)
5. [VMWARE虚拟机三种网络模式（BRIDGED，NAT，HOST-ONLY)区别详解](http://hao.jser.com/archive/7954/)
6. [为什么常见路由器的网关默认 IP 都是 192.168.1.1？](https://www.zhihu.com/question/20185640/answer/23193352)
7. [Internet 因特网](https://zh.wikipedia.org/wiki/%E4%BA%92%E8%81%94%E7%BD%91)
8. [WAN 广域网](https://zh.wikipedia.org/wiki/%E5%B9%BF%E5%9F%9F%E7%BD%91)
9. [LAN 局域网](https://zh.wikipedia.org/wiki/%E5%B1%80%E5%9F%9F%E7%BD%91)
10. [LAN_vs_WAN](http://www.diffen.com/difference/LAN_vs_WAN)
11. [Wi-Fi](https://zh.wikipedia.org/wiki/Wi-Fi)
12. 
