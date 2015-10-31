
# [github](https://github.com/tiimgreen/github-cheat-sheet/blob/master/README.zh-cn.md)
 
  
# git
http://blog.csdn.net/shulianghan/article/details/18812279

https://github.com/z007/github/blob/master/github.md
# [GitHub vs. Bitbucket ](http://www.oschina.net/translate/bitbucket-vs-github-its-more-than-just-features)

# [tip](http://dengshuan.me/misc/github-tips.html) 
*  [cache](http://webcache.googleusercontent.com/search?q=cache:bOWkIdr68ewJ:dengshuan.me/misc/github-tips.html+&cd=1&hl=zh-CN&ct=clnk)
 ```
   GitHub 使用小技巧

GitHub 现在成了程序员最流行的社交网站，可能也是最大的代码托管仓库。然而除了代码托管外，GitHub 还提供其它服务：代码仓库(https://github.com), 代码片段(https://gist.github.com), 短网址(https://git.io)，主页 (http://username.github.io)，工作(https://jobs.github.com)。这里记录一下 GitHub 一些使用小技巧。

文件夹
文件A/文件名
URL 小技巧

代码链接高亮特定行，在URL末尾添加 #Lm-Ln ，其中 m 和 n 是行数

PR 的 URL 后面添加 .diff 或 .patch 可以显示纯文本的 diff 或 patch

在 diff 时的 URL 后面加上 ?w=1 可以忽略空格

在 URL 后面添加 ?author=username 可以直接查看某个作者提交历史

直接在 gist 的 URL 后面添加 .pibb 可以得到纯 HTML 的版本，从而不借助 js 将 gist 内嵌到网页

更多 URL 小技巧可以参考 GitHub 提供的 API

参考

高级搜索

GitHub 的代码搜索只搜索主分支，而且文件小于384k，不支持通配符搜索

高级搜索入口在这里， 也可以直接在搜索框中输入键值对实现高级搜索。

高级搜索方式是提供键值对，可选键有 user, repo, created, language, stars, forks, size, pushed, extension, path, fullname, location, followers, repos, state, comments, label, author, mentions, assignee, updated, fork

键值对之间用空格隔开，值如果有多个，分开写，例如 repo:repo1 repo:repo2 ，值本身有空格，需要用双引号包起来，例如 language:"Emacs Lisp"，搜索不区分大小写，所以 language:objective-c 同样可以搜索出结果

快捷键

GitHub 上几乎每个页面都有快捷键 ，想要查看所浏览页面支持的快捷键，输入问号。

全站快捷键

s 定位到搜索框
g+n 查看通知
代码库快捷键

g+c 到代码库首页
g+i 查看 issue
g+p 查看 PR
g+w 查看 Wiki
浏览代码

t 激活查找文件模式
l 定位到行
w 切换分支或tag
y 将 URL 展开成正则形式
i 显示或隐藏 diff 中的评论
issues

c 创建一个 issue
/ 定位到 issue 搜索框
l 过滤或编辑标签
m 过滤或编辑 milestone
a 过滤或编辑 assignee
r 在回复中引用鼠标选中的文本
通知

e l y 标记为已读
shift m 将帖子静音
PR

r 在回复中引用鼠标选中的文本
o+enter 打开 issue
Network Graph

方向键和 hjkl 与 Vim 中一样
shift + 方向键或 hjkl 行动到头
发布

现在也可以托管编译的二进制文件以及压缩文件了，不过是将软件打包放到 release 下

Pages

Pages 都是 http 访问的，有个人/组织主页和项目主页两种

个人/组织主页必须在 username.github.io 仓库里，而项目主页是在项目的 gh-pages 分支，没有自定义域名时，个人/组织主页为 http://username.github.io 下，而项目主页在 http://username.github.io/projectname ，没有自定义域名不能自定义404页面

gist

gist 分为公开和私密的，不像私有仓库不能被非授权用户访问，私密仅仅表示不能被搜索(gist 搜索与仓库搜索方法一样)，仍然可以直接被别人看到（只要知道地址）。没登录也可以创建 gist（匿名 gist）。
   ```
   
