### 禁用cookies/Block Cookies Settings

功能：阻止发送和接收Cookie

![](http://i.imgur.com/iLcvYBl.png)

##### 禁用Cookie工具

禁用Cookie工具阻止发送和接收Cookie。 它可以用来测试网站，就像您的浏览器中禁用Cookie一样。 

请注意，网络蜘蛛（如Google）通常不支持Cookie，因此该工具也可用于模拟蜘蛛网站的视图。

**适用范围**

该工具可以针对每个请求启用，也可以仅对选定的位置启用。选中 enable block cookies 即可 

当用于某个域名时，可以将禁用Cookies的效果限制在你所配置的主机上；同时选中 only for selected locations 即可；

**原理**

Cookie头部从请求中删除，防止将cookie值从客户端应用程序（例如Web浏览器）发送到远程服务器。 

Set-Cookie头将从响应中移除，从而防止客户端应用程序从远程服务器接收cookie的请求。

**注意**

很多网站的登录是通过写入Cookies然后通过读取Cookies的值来进行网站用户身份和权限管理的；如果你禁用了Cookies，这将会到导致你登录某个网站的一直，一直停留到登录页，这是因为写入您Cookies的方法没有值导致的；表现就是你一直登录，虽然账号密码正确但一直还是停留在登录页；

**选中 only for selected locations 的设置**

设置单个匹配可以查看 [charles location的匹配方式.md]，设置的方式都是一样的；