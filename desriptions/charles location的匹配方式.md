
### charles location的匹配方式/edit location

location匹配包含:
- protocol 	请求的URL的协议，包含HTTP和HTTPS,
- Host		主机
- Port		端口
- Path		路径
- Query		查询字符

如果您所有字段都留空，在这种情况下，它们将匹配任何值；

**通配符**

使用*，？或字符范围[...]。

- 使用"*"匹配零个或多个字符。
- 使用"？"匹配一个字符
- 使用"字符范围"来匹配范围中的一个字符，例如。 [a-z]或[aeiou]。

**path**

要匹配子路径，您必须使用/*结束路径。

注意：在以前的Charles版本中，这是隐含的，但现在是必需的。

**query**

查询字段与查询字符串的内容匹配(key和value)。不包括？,因为它是启动查询的字符。

请注意在 query里 ？字符是通配符。

查询字段可以包括通配符，如其他字段，因此您可以在查询字符串中的任何位置执行诸如“* page = 1 *”的查询以匹配“page = 1”。

**常见用途**

- 要将每个请求匹配给“指定主机”，请输入主机名，并将其他字段留空。
- 要将每个请求与"主机上的给定路径"相匹配，请输入主机名和以/结尾的path，将其他字段留空。
- 要使主机上的"给定后缀"匹配每个文件，请输入主机名和/*.suffix，将其他字段留空。

**例子**

<table style="border:1px solid #f2f2f2;">  
    <tr>  
        <td>Host</td>  
    	<td>Path</td>
    	<td>结果</td>  
    </tr>  
    <tr>  
        <td>charlesproxy.com</td>  
    	<td> </td>
    	<td>匹配到charlesproxy.com的所有请求</td>  
    </tr> 
    <tr>  
        <td>*.charlesproxy.com</td>  
    	<td> </td>
    	<td>匹配所有以.charlesproxy.com结尾的请求</td>  
    </tr>
    <tr>  
        <td>charlesproxy.com</td>  
    	<td>/charles/</td>
    	<td>仅仅匹配 charlesproxy.com/charles/ 的所有请求</td>  
    </tr>  
    <tr>  
        <td>charlesproxy.com</td>  
    	<td>/charles/*</td>
    	<td>匹配 charlesproxy.com/charles/下的所有请求，包括文件和子路径</td>  
    </tr>  
    <tr>  
        <td>charlesproxy.com</td>  
    	<td>/charles</td>
    	<td>仅匹配 charlesproxy.com/charles</td>  
    </tr>  
    <tr>  
        <td>charlesproxy.com</td>  
    	<td>/index.html</td>
    	<td>仅匹配charlesproxy.com/charles.html</td>  
    </tr>  
    <tr>  
        <td>charlesproxy.com</td>  
    	<td>/*.html</td>
    	<td>仅匹配charlesproxy.com后以.html的文件</td>  
    </tr>
    <tr>  
        <td> </td>  
    	<td>/charles/*.html</td>
    	<td>匹配任何host中所有/charles/路径下(包括子路径)已.html结尾的文件</td>  
    </tr>   
</table> 

如果在上面再加"协议"和"端口"可以将上面的匹配进一步缩小。