### 远程映射/Map Remote Settings

功能：X

![](http://i.imgur.com/P1ZbC6y.png)

##### 远程映射工具

远程映射工具根据配置的映射更改请求位置，以便从新位置“可见的”地提供响应，就像原始请求一样。

此映射使您能够从B站点提供A站点的全部或部分(A是原始的目标，B是你远程映射的地方)。

例如，
- 您可以把 xk72.com/charles/ 映射到 localhost/charlesdev/ 来为xk72.com提供一个子目录，
- 或者把xk72.com/*.php 这种指定后缀的所有文件映射到localhost/charlesdev/。

**使用建议**

如果您想开发某个网站，并且已经有了开发环境的网站，并希望把刚更新的某些文件应用到线上网站，测试下效果如何，则“远程映射”将非常有用。

例如，您可能把测试环境的css和images目录下的文件更新了。可以把live.com/css/映射到 dev.com/css/或把live.com/*.css这样的映射到dev.com。

**映射类型**

- 您可以将目录映射到目录，如xk72.com/charles/ 映射到 localhost/charlesdev/
- 您可以将文件映射到文件，如xk72.com/charles/download.php 映射到 abc.com/testing/test.html
- 您可以将目录与文件模式映射到目录，如xk72.com/charles/*.php 到localhost/charlesdev/
- 如果在目标映射中未指定路径，则URL的路径部分将不会更改。如果要映射到根目录，请在目标路径字段中已/结尾。

**个人觉得，其实没有必要这么做，如果想达到同样的效果也可以通过修改本地HOST的方式来实现**；

虽然不推荐远程映射，但是非常推荐用"本地映射"

**本地映射**

另请参阅本地映射工具，可以把网络上的某些请求文件映射到本地文件，这样你就不用把文件丢到测试环境上去，直接刷新浏览器就可以查看最新效果。

**locations匹配**
每个位置匹配可能包含协议，主机，端口和路径模式，以匹配特定的URL。位置可能包括通配符。