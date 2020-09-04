# `OSI`七层模型、`TCP/IP`模型、`Http`协议模式

[TOC]

## 一、`OSI`七层模型

`OSI（Open System Interconnect）`，即开放式系统互联。 一般都叫`OSI`参考模型，是`ISO`（国际标准化组织）组织在1985年研究的网络互连模型，分为以下七层：

> 1. 应用层：可见的终端应用，如浏览器、`FTP`等； --> 发送或接受数据
> 2. 表示层：计算机识别的信息转变成人可以识别的信息，如图片、声音、视频等； --> 数据压缩或解压缩
> 3. 会话层：传输端口和接收端口建立会话； -->
> 4. 传输层：传输数据的协议与端口，如`TCP/UDP`等； --> 包装`TCP/UDP`等协议
> 5. 网络层：路由器传输，涉及`IP`地址，数据报包等； --> 包装`IP`地址打包成数据报包
> 6. 数据链路层：网桥、网卡，以太网交换机传输； --> 将数据报包转换成帧
> 7. 物理层：具体可以进行数据传输的物理设备，如光纤、双绞线等。--> 比特流数据

![image](https://github.com/tianyalu/NetworkTheory/raw/master/show/network_seven_level_model.png)

## 二、`TCP/IP`参考模型

> 1. 应用层：对应`HTTP/HTTPS`、`DNS`、`FTP`、`TFTP`、`SMTP`、`Telnet`等；
> 2. 传输层：对应`TCP`、`UDP`等协议；
> 3. 网络层：对应`IP`、`ICMP`、`RIP`、`IGMP`等协议；
> 4. 主机至网络层：对应`ARP`、`RARP`、`IEEE802.3`、`PPP`、`CSMA/CD`等协议

![image](https://github.com/tianyalu/NetworkTheory/raw/master/show/network_four_level_model.png)

## 三、`HTTP`协议模式

### 3.1 实用工具`Restlet Client`

可以通过`Chrome`的插件 [`Restlet Client`](https://chrome.zzzmh.cn/info?token=aejoelaoggembcahagimdiliamlcdmfm) 来分析网络请求。

### 3.2 `HTTP`协议

#### 3.2.1 `HTTP1.0`

`HTTP1.0`每次连接都会断开：

![image](https://github.com/tianyalu/NetworkTheory/raw/master/show/http1.0.png)

#### 3.2.2 `HTTP1.1`

`HTTP1.1`可以通过`keep-alive`来保持长连接，不会每次都断开，但会增加服务器压力。

![image](https://github.com/tianyalu/NetworkTheory/raw/master/show/http1.1.png)

#### 3.2.3 `HTTP Get Request`

> 1. 请求行：`GET / HTTP1.1`；
> 2. 请求属性集：`Connection:keep-alive`、`Host:www.baidu.com`...

![image](https://github.com/tianyalu/NetworkTheory/raw/master/show/http_get_request.png)

#### 3.2.4 `HTTP Post Request`

> 1. 请求行：`GET / HTTP1.1`；
> 2. 请求属性集：`Connection:keep-alive`、`Host:www.baidu.com`...；
> 3. 请求体长度：`Content-Length:16`；
> 4. 请求的类型：`Content-Type:application/json` 或者 `Content-Type:applicaton/x-www-form-urlencoded`。

> * 请求体：`a=11188888&b=222` 。

![image](https://github.com/tianyalu/NetworkTheory/raw/master/show/http_post_request.png)

