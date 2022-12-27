---
title: "史上最快免费搭建节点方法"
date: 2022-12-01T15:54:42+08:00
tags: ["教程","阿甘科技的博客"]
categories: [""]
draft: false
dropCap: false
---

[Replit](https://repl.it)是一个基于浏览器的云端协同开发平台，可用于构建开发环境、实时协作、托管网络应用等。Replit提供可创建动态或者静态网站的容器，并会自动生成免费https域名（格式为：项目名.用户名.repl.co）。这代表着任何人都可以试用Replit的云服务器创建自己的网站，或者是其他的服务，例如v2ray，而且这一切，都是免费的。

[点此进入Replit官方文档](https://docs.replit.com/)

### 注册
注册地址 https://repl.it
可选谷歌账号、shoppingmode 苹果账号、fb或者GitHub账号一键登录，或者自己用邮箱注册也行，邮箱注册的需要收信验证一下。

其他的没什么说的，就是跳过，或者随便选择吧；

### Replit测试
注册后，我随便弄了个Repl，经测试Repl项目是在谷歌云中运行的，主服务器8核64G，当然了这不可能都给你用，所有Repl项目会共用这台服务器，直到它到了负荷，会自动切换到下一台。

随便开一个Repl，然后shell进入，查看当前主机状态，负载蛮高的。
![1](https://iweec.com/usr/uploads/2022/12/1695379248.png)

每个免费的项目会得到0.2-0.5个CPU512M内存1GB的硬盘空间，想提高性能就要充值！

另外就是replit.nix，需要自己集成；最后，Replit的项目就叫：repl；

### 创建repl
### 静态或动态网站
在home中，点击Create，然后选择HTML, CSS, JS（静态），PHP Web Server(动态)，然后Create Repl即可。

倘若网站的文件比较少，可以直接写代码，如果文件比较多用git之前先要把Replit连接到你的github。


Replit虽然也提供了数据库，我看仅仅适合学习用途，动态网站所需的数据库还是自己找个免费的，例如：[freedb](https://freedb.tech/)

简单说，就是我们的内容托管在Replit，数据库还是需要用别人的，想尝试Replit自己的SQLite服务，也可以试试。

可能是我测试的时间比较短，并没有发现问题。Replit官方说：永远在线服务是要购买的，这说明，这个空间并不能永久在线！做站就要认真考虑一下了。

### 为自己的网站绑定域名
在网站页面，点击Domain Linking，输入自己的域名，按照提示修改A记录或者使用CNAME，再添加TXT记录，然后检查通过即可绑定域名访问。

### 创建其他repl
这里没什么可说的，Python、C#、node.js、Java都可以随便尝试。

### 共享自己的项目
在自己repl的右上角，点击Invite即可给项目生成一个URL，发给你的伙伴即可实现共享。

### 其他功能
Replit的其他功能都可以在文档中找到，够玩好几天了。

## 搭建shadowsocks
感谢热心网友提供的搭建方法。

1、浏览器登录自己的Replit账号，新窗口打开[Replit-ss1](https://replit.com/@wanghanzhe/V2RAY?v=1)
备用地址： [Replit-ss2](https://replit.com/@oracleservice/V2RAY)

2、fork这个项目，仅需点击Use Template，然后给项目取个名字，然后Use Template就行了。

3、点击run，Console会输出password和url，直接添加到app中即可使用；

![2](https://iweec.com/usr/uploads/2022/12/1673290034.png)

4、速度如何呀？ 谷歌的服务器不用问，电脑上我都没测试，直接告诉你能跑满，而且现在用的人也不太多，白嫖党作为自己的主力线路好像也没压力。

5、个别伙伴扫描二维码不能直接导入v2客户端，请参考如下配置：
![4](https://iweec.com/usr/uploads/2022/12/2274539777.jpg)

## 搭建trojan
非常简单，Fork [Replit-Trojan1](https://replit.com/@sos801107/trojan?v=1)
备用地址： [Relit-Trojan2](https://replit.com/@oracleservice/trojan)
然后运行 bash main.sh
即可看到 trojan链接和二维码，实测路由器可用。

![3](https://iweec.com/usr/uploads/2022/12/3103210989.png)

配置参考：

![3](https://iweec.com/usr/uploads/2022/12/2336471006.jpg)

## 搭建Vmess
**Fork** 此项目: [V2ray](https://replit.com/@hifeng/v2rayN?v=1)

完成后点击 **Run**

然后左侧Files菜单中,程序自动创建 url.txt 文件，该文件包含 VMess 和 VLess 协议的链接地址，在客户端软件中导入即可。

同时，程序自动创建了 VLess.png 和 VMess.png 文件,分别是 VLess 和 VMess 协议的二维码，使用手机扫描即可添加节点。

服务启动,复制节点信息后,请手动删除 url.txt uuid.txt VLess.png 及 VMess.png 文件

否则,任何知道你的 repo 地址的人都可以使用你的节点

## 保持开启

### 为何要保持开启？
由于 Replit 为了节省资源在项目没有流量访问时会自动关闭项目

### 部署网站监控
在UptimeBot中新建一个监控:

### 配置:

Monitor Type 选择 https

Friendly Name 名称随意

Url 填写Replit的域名或绑定的域名

[可选]邮箱提醒(当监控不成功时发送邮件,由于显示的是 Bad Request 所以会一直发邮件,不推荐选)

完成后点击 Creat Monitor 即可
