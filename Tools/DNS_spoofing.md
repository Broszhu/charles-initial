### DNS欺骗/DNS Spoofing

功能：通过将您自己的主机名指定给远程地址映射来欺骗DNS查找

一般的开发流程中，在上线之前都需要在测试环境中先行进行验证，而此时手机客户端请求的域名是不太容易改变的，可以通过设置dns方式把域名转发到测试机上，具体设置Tools->DNS Spoofing Settings

比如要把所有包含xxxxxx.com的域名转到10.0.0.71的服务器上，其实用修改HOST的方式是可以解决的；


**下面是官方文档上的介绍**：

DNS Spoofing工具使您能够通过将您自己的主机名指定给远程地址映射来欺骗DNS查找。 当请求通过Charles时，您的DNS映射将优先。

在DNS更改之前，DNS Spoofing可用于测试虚拟托管网站，因为您的浏览器将会像DNS更改一样运行。

DNS更改通常需要长达24小时才能生效，并且没有DNS欺骗，DNS变更生效后，网站将会变得非常困难。

您可以将主机名映射到IP地址或另一个主机名，这些名称将由Charles在DNS中查找以查找其IP地址。

主机名可能包含通配符。