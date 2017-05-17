# charles-initial
Fiddler在MAC下到替代品,没啥好介绍的；

Charles 主要的功能包括：
- 截取 Http 和 Https 网络封包。
- 支持重发网络请求，方便后端调试。
- 支持修改网络请求参数。
- 支持网络请求的截获并动态修改。
- 支持模拟慢速网络。

### 安装方法：略

注意：Charles 是收费软件，可以免费试用 30 天；推荐用正版，如果为了研究学习，可以看下[charles破解版和破解方法](http://www.baidu.com/)

### 将Charles 设置成系统代理

首先charles设置为系统代理；可以用fidder的官网的图片表示charles的原理

![](https://imgsa.baidu.com/exp/pic/item/73ca5910b912c8fcaa028211fd039245d788213d.jpg)


Charles 是通过将自己设置成代理服务器来完成封包截取的，通过charles链接客户端和真正的服务器;

所以使用 Charles 的第一步是将其设置成系统的代理服务器。

启动 Charles 后，第一次 Charles 会请求你给它设置系统代理的权限。你可以输入登录密码授予 Charles 该权限。你也可以忽略该请求，然后在需要将 Charles 设置成系统代理时，选择菜单中的 “Proxy” -> “Mac OS X Proxy” 来将 Charles 设置成系统代理。

参考如下，如果Mac下有管理密码，输入即可；http://blog.csdn.net/liu251/article/details/52096142

将charles设置为chrome的代理

需要注意的是，Chrome 和 Firefox 浏览器默认并不使用系统的代理服务器设置，而 Charles 是通过将自己设置成代理服务器来完成封包截取的，所以在默认情况下无法截取 Chrome 和 Firefox 浏览器的网络通讯内容。如果你需要截取的话，在 Chrome 中设置成使用系统的代理服务器设置即可，或者直接将代理服务器设置成 127.0.0.1:8888 也可达到相同效果。

备注：如果您的chrome有用过改HOST的扩展工具，请暂时关闭；否则chrome会通过你的扩展控制，不能使用charles；

可能会看到的提示是：**您的网络代理设置是由扩展程序管理的。** 这种的；

http://blog.csdn.net/liu251/article/details/52096142

### charles 主界面介绍

Charles 主要提供两种查看封包的视图，分别名为 “Structure” 和 “Sequence”。
- Structure/结构：视图将网络请求按访问的域名分类。
- Sequence/序列：视图将网络请求按访问的时间排序。

可以根据具体的需要在这两种视图之前来回切换。请求多了有些时候会看不过来，Charles 提供了一个简单的 Filter 功能，可以输入关键字来快速筛选出 URL 中带指定关键字的网络请求。

对于某一个具体的网络请求，你可以查看其详细的请求内容和响应内容。如果请求内容是 POST 的表单，Charles 会自动帮你将表单进行分项显示。如果响应内容是 JSON 格式的，那么 Charles 可以自动帮你将 JSON 内容格式化，方便你查看。如果响应内容是图片，那么 Charles 可以显示出图片的预览。

### 过滤网络请求

通常情况下，我们需要对网络请求进行过滤，只监控向指定目录服务器上发送的请求。对于这种需求，以下几种办法：

##### 方法一：直接过滤域名；

在主界面的中部的 Filter 栏中填入需要过滤出来的关键字。例如我查看的域名地址是：http://www.baidu.com , 那么只需要在 Filter 栏中填入 baidu.com 即可。

##### 方法二：修改Include的域名和端口

在 Charles 的菜单栏选择 “Proxy”->”Recording Settings”，然后选择 Include 栏，选择添加一个项目，然后填入需要监控的协议，主机地址，端口号。这样就可以只截取目标网站的封包了。

通常情况下，我们使用方法一做一些临时性的封包过滤，使用方法二做一些经常性的封包过滤。

##### 方法三：在目标的网络请求上右键，选中focus（此时，该域名已经被设置为一个标记了；）；然后点击fillter后面的focused来筛选你的做的focus标记文件；



参考和更多：

https://www.charlesproxy.com/documentation/

http://blog.devtang.com/2015/11/14/charles-introduction/

http://www.heyuan110.com/2015/08/15/Charles%E8%BE%85%E5%8A%A9%E8%B0%83%E8%AF%95%E6%8E%A5%E5%8F%A3/

http://www.cnblogs.com/wonyun/p/5586746.html

http://www.w2bc.com/article/224808

http://www.jianshu.com/p/fdd7c681929c

http://www.tuicool.com/articles/qYbqquB

http://m.blog.csdn.net/article/details?id=52585077

http://www.cnblogs.com/yuanjunliang/articles/5167927.html

https://coolnull.com/3978.html

http://yangfch3.com/2016/08/25/Charles%E4%BD%BF%E7%94%A8%E7%AC%94%E8%AE%B0/