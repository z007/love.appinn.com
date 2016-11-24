## DNS



* [Windows系统 , Windows XP, Linux系统, Mac系统](https://support.dnspod.cn/Kb/showarticle/tsid/240/#link1)
* DNS

* [DNS wikipedia](https://zh.wikipedia.org/wiki/%E5%9F%9F%E5%90%8D%E7%B3%BB%E7%BB%9F)
```
电脑DNS设置
Windows + R
ncpa.cpl 网络连接

路由器设置DNS
网络参数->WAN口设置->高级手动设置DNS服务器

Avast DNS设置
使用Avast杀毒软件进行家庭网络扫描时。
发现路由器DNS设置有问题,建议修改为 8.8.8.8
注意 把首选DNS服务器设置为：8.8.8.8 
       备选DNS服务器设置为：8.8.4.4
全部设为google DNS这样才可以 ，否则Avast 还会提示警告
```


* [DNS 查询](http://ip.cn/dns.html)

```
Google DNS	8.8.8.8	8.8.4.4
OpenDNS	208.67.222.222	208.67.220.220
```


* DNSCrypt

 * http://www.williamlong.info/archives/3890.html
 * https://github.com/opendns/dnscrypt-win-client

* DNSspeeder 2.85

 * http://www.sharewarestudio.com/?page_id=6

* [chrispc-dns-switch](https://free.com.tw/chrispc-dns-switch/)
* [maplatency](https://free.com.tw/maplatency/)




## speedtest
* http://www.speedtest.cn/
* http://ip.cn/

* [IP]( https://www.browserleaks.com)
  * [whois](https://www.browserleaks.com/whois) 
  * [webrtc](https://www.browserleaks.com/webrtc)
  * [ipecho](http://ipecho.net/plain)
  * [ip adress1](http://ip.cn/)
  * [ip adress2](https://www.goldenfrog.com/CN/vyprvpn)
  * [ip adress3](http://www.speedtest.net/)
  


## [DNS leak  test 泄漏](http://www.freebuf.com/articles/network/67591.html)
       * www.dnsleaktest.com
        
       
## [WebRTC Leak Test](https://www.browserleaks.com/webrtc#webrtc-disable)

*  [WebRTC 网页即时通讯](https://zh.wikipedia.org/zh/WebRTC) --wikipedia
```
WebRTC and VPN
WebRTC is a special interface that allows computers on different networks to perform special browser-to-browser applications. An example of these are video chat, voice calling, file sharing and more. There's no flaw in WebRTC but someone can add in some code that will trick your browser into revealing your real IP address. To make sure your real IP address is not revealed check it from this site, http://whatismyipaddress.com/webrtc-test  https://www.browserleaks.com/webrtc#webrtc-disable
```
*  How to Disable WebRTC
```
建议使用 FF
To disable WebRTC in Firefox, go to about:config and toggle media.peerconnection.enabled to false.
使用chrome 比较麻烦
需要使用Extension，前提必须是使用VPN。使用代理软件（如 lantern，tor ,lantern-tor......）无效，产生的效果是局域网(Local IP Address) 看不见了而已
```

****

✔ Disable WebRTC in Firefox
WebRTC in Mozilla Firefox is partially supported since Firefox 22, and it's enabled by default.

To disable WebRTC in Firefox, go to about:config and toggle media.peerconnection.enabled to false.





?Disable WebRTC in Chrome
WebRTC in Google Chorme is supported and enabled by default since Chorme version 23 (and based on it, ex. Opera, Vivaldi).

Bad news:

You CAN'T turn off WebRTC on desktop version of Google Chrome, Disable WebRTC flag is available only on Android.

Good news:

There is a Chrome Extension: WebRTC Block.
* https://github.com/diafygi/webrtc-ips    
* https://github.com/rentamob/WebRTC-Leak-Prevent-Toggle
`

**Extension hides your public IP when you're behind VPN. It will leak only VPN's public IP, but not your real provider IP address! Extension also hides your Local/NAT IP addresses.**

**Unfortunately, if you're behind proxy but not VPN, WebRTC Block will not help you.**

I can't do anything, and no one can. This piece of the periodic table is ****ed by design. So PLEASE stop insulting me on mail and webstore that it's "NOT WORKING !!!" :)

Just use FF. There is no drama
