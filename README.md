
####第一步：在浏览器中输入url
**url**：统一资源定位符，是对可以从互联网上得到的资源的位置和访问方法的一种简洁的表示，是互联网上标准资源的地址。互联网上的每个文件都有一个唯一的URL，它包含的信息指出文件的位置以及浏览器应该怎么处理它。

**url的构成**
举例http://www.aspxfans.com:8080/news/index.asp?boardID=5&ID=24618&page=1#name

从上面的URL可以看出，一个完整的URL包括以下几部分：
1.协议部分：该URL的协议部分为“http：”，这代表网页使用的是HTTP协议。在Internet中可以使用多种协议，如HTTP，FTP等等本例中使用的是HTTP协议。在"HTTP"后面的“//”为分隔符
2.域名部分：该URL的域名部分为“www.aspxfans.com”。一个URL中，也可以使用IP地址作为域名使用
3.端口部分：跟在域名后面的是端口，域名和端口之间使用“:”作为分隔符。端口不是一个URL必须的部分，如果省略端口部分，将采用默认端口
4.虚拟目录部分：从域名后的第一个“/”开始到最后一个“/”为止，是虚拟目录部分。虚拟目录也不是一个URL必须的部分。本例中的虚拟目录是“/news/”
5.文件名部分：从域名后的最后一个“/”开始到“？”为止，是文件名部分，如果没有“?”,则是从域名后的最后一个“/”开始到“#”为止，是文件部分，如果没有“？”和“#”，那么从域名后的最后一个“/”开始到结束，都是文件名部分。本例中的文件名是“index.asp”。文件名部分也不是一个URL必须的部分，如果省略该部分，则使用默认的文件名
6.锚部分：从“#”开始到最后，都是锚部分。本例中的锚部分是“name”。锚部分也不是一个URL必须的部分
7.参数部分：从“？”开始到“#”为止之间的部分为参数部分，又称搜索部分、查询部分。本例中的参数部分为“boardID=5&ID=24618&page=1”。参数可以允许有多个参数，参数与参数之间用“&”作为分隔符。


#####url中的协议
**http协议**：超文本传输协议（HTTP，HyperText Transfer Protocol)是互联网上应用最为广泛的一种网络协议。所有的WWW
文件都必须遵守这个标准。设计HTTP最初的目的是为了提供一种发布和接收HTML页面的方法。

**file协议**：File协议主要用于访问本地计算机中的文件，就如同在Windows资源管理器中打开文件一样。

**https协议**：是以安全为目标的HTTP通道，简单讲是HTTP的安全版

**//**：当前文件的url与页面保持一致

####第二步：域名解析
将好记的域名解析成IP，服务由DNS服务器完成。人们习惯记忆域名，但机器间互相只认IP地址，域名与IP地址之间是对应的，它们之间的转换工作称为域名解析，域名解析需要由专门的域名解析服务器来完成，整个过程是自动进行的。

**IP地址**：它为互联网上的每一个网络和每一台主机分配一个逻辑地址

**域名解析流程**（按下列顺序查找IP）
1.浏览器缓存 – 浏览器会缓存DNS记录一段时间

2.系统缓存 - 从 本地Hosts 文件查找是否有该域名和对应 IP。

3.路由器缓存 – 一般路由器也会缓存域名信息。

4.ISP DNS 缓存 – 比如到电信的 DNS 上查找缓存。

5.如果都没有找到，则向根域名服务器查找域名对应 IP，根域名服务器把请求转发到下一级，知道找到 IP

- 电脑上不了网，修改dns为8.8.8.8或114.114.114.114就可以上网，这两个地址是大型的dns服务器，储藏了许多ip
- dns劫持，给错误的ip，假网址域名可一样


####第三步：服务器处理
- 常见的Web服务器有Apache、Nginx、lls、Lighttpd

- web服务器接收用户的Request交给网站代码，或者接受请求反向代理其他web服务器

举例：
![image.png](http://upload-images.jianshu.io/upload_images/8610970-27adf2e08bb33eac.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

图中的白色区域为服务器，收到用户请求后，三个网站返回的都是202.112.230.14这个ip，不过nginx服务器中有配置文件，当接受到不同的域名时，将请求交给不同的文件夹管控

####第四步：网站处理流程
MVC模型(model)-视图(view)-控制器(controller)
![image.png](http://upload-images.jianshu.io/upload_images/8610970-2304bbd968bf440b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

####第五步：浏览器处理
1.HTML字符串被浏览器接受后被一句句读取解析

2.解析到link 标签后重新发送请求获取css

3.解析到 script标签后发送请求获取 js，并执行代码

4.解析到img 标签后发送请求获取图片资源

浏览器根据 HTML 和 CSS 计算得到渲染树，绘制到屏幕上js 会被执行

