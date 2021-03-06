### 本地映射/Map Local Settings

功能：把需要请求网络的文件映射为请求本地文件

![](http://i.imgur.com/CXBFieI.png)

**本地映射工具**

本地映射工具使您能够使用本地文件，就像它们是远程网站的一部分一样。您可以在本地开发您的文件，然后刷新浏览器即可看到效果，本地文件的内容将返回给客户端，就像它是正常的远程响应一样。（如果不清楚原理可以看下charles/fiddler这类工具的实现原理）

本地映射可以大大加快开发和测试的效率，否则您将不得不将文件上传到网站来测试结果。使用Map Local，您可以在开发环境中安全地测试。

**动态文件**

动态文件（如包含服务器端脚本的文件）不会由Map Local执行，因此如果文件中有任何脚本将脚本返回到浏览器（可能不是预期的结果）。
如果您希望使用动态文件，就像它们是远程网站的一部分一样，请参阅“远程映射”工具。

**怎么实现的**
当请求与Map Local映射匹配时，它会检查与该路径匹配的本地文件。它不包括查询字符串，如果有一个。如果所请求的文件在本地找到，则作为响应返回，就像从远程站点加载一样，因此对客户端是透明的。如果请求的文件未在本地找到，则请求将像平常一样由网站提供。

**例子**

如果您正在更改测试css，swf或图片 JS，您可以将这些文件类型映射到本地网站的开发副本，以便您可以浏览具有所有开发资产的实时网站。创建从live.com/*.css到本地开发副本的根的映射，以及其他文件类型的类似映射。或者，您可以根据需要映射整个目录或单个文件。

![](http://i.imgur.com/yY4G89R.png)

上面图片，我是把 x.xxx.com 全部映射到某个文件夹下的；

**位置匹配**

每个位置匹配可能包含协议，主机，端口和路径模式，以匹配特定的URL。位置可能包括通配符。


**本地映射**
本地映射包含一个位置匹配和本地目录，从该目录尝试提供匹配。
使用相对路径在本地目录中搜索文件。 相对路径是匹配路径部分之后剩下的请求位置的一部分。 这最好由下面的例子解释。
本地映射可以区分大小写;