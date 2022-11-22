---
title: "QuantumultX 小白教程"
date: 2022-10-25T10:07:26+08:00
tags: ["QuantumultX"]
categories: [""]
draft: false
dropCap: false

---



## 转载自[耳东陈](https://raw.githubusercontent.com/erdongchanyo/Rules/main/Quantumult%20X/README.md)

### 注：该教程实例均仅用作举例，由于例子较为古老实用性未知，不确定是否可用，见谅。

感谢教程提供(不分先后)：

[Shawn](https://www.notion.so/Quantumult-X-1d32ddc6e61c4892ad2ec5ea47f00917)、[Sabrina](https://merlinblog.xyz/)、[毒奶](https://limbopro.xyz/)

感谢规则、脚本等提供(不分先后)：

[DivineEngine](https://github.com/DivineEngine)、 [GeQ1an](https://github.com/GeQ1an)、[NobyDa](https://github.com/NobyDa)、[lhie1](https://github.com/lhie1)、[chavyleung](https://github.com/chavyleung)、[lxk0301](https://github.com/lxk0301)、[yichahucha](https://github.com/yichahucha)、[Sunert(Flydreams)](https://github.com/Sunert/Scripts)

感谢icon资源提供(不分先后)：

[Koolson](https://github.com/Koolson)、[Orz-3](https://github.com/Orz-3)

### [@阿甘科技的个人导航](https://xydh.fun/gzy20080302)

### [@阿甘科技的油管](https://www.youtube.com/channel/UCj4DaQ3kboTY6tun1eCaT9g/featured)

### [@阿甘科技的博客](https://agkjvip.github.io)






---

## 一、Quantumult X小白系列教程｜导入订阅链接、添加自己搭建的节点，开始使用

❗️**`视频教程地址：`**https://youtu.be/Ub9RN-7Q94s

### 1. 关于节点

- 导入 `自己搭建的节点` 或者 `节点(机场)订阅链接` 
- 支持协议：ss / ssr / trojan / vmess / http(s)
- 配置文件中对应的模块：**`[server local]` / `[server remote]`**

### 2. 首先，给你的Quantumult X增加一个小工具：资源解析器

`适用于 Quantumult X (v1.0.8-build253) 版本后`

> - ????**有啥用？**
>
>   > 使用 `资源解析器` 后，可以将 Quantumult X 原本不识别的 节点或订阅链接 轻松的导入
>
> - ????**有啥优点？**
>
>   > 可以通过修改`本地节点配置片段` 来管理服务器
>   >
>   > 本地解析，服务器无暴露风险
>   >
>   > 支持中文参数(空格除外)
>
> - ????**如何添加`资源解析器`**
>
>   在Quantumult X 配置文件中 `[general]` 部分，加入
>
>   ```
>   resource_parser_url=https://raw.githubusercontent.com/KOP-XIAO/QuantumultX/master/Scripts/resource-parser.js
>   ```

### 3. 添加节点和订阅链接

#### a. 通过Quantumult X UI界面 (用户界面) 进行添加节点

> `设置` > `节点`

##### a.1 通过 `添加` / `SS URI` / `扫码` 添加节点

> ⚠️ 一次只能添加一个节点
>
> 添加后，节点信息将出现在配置文件的 `[server_local]` 部分
>
> - `添加`：只支持 ss协议
>
> - `SS URI`：支持 ss / ssr 以及 `Quantumult X 格式`的 trojan / vmess / http(s) 节点信息
>
>   以添加 trojan 节点为例：
>
>   ```
>   trojan=example.com:443, password=pwd, over-tls=true, tls-verification=false, fast-open=false, udp-relay=false, tag=节点名称
>   ```
>
> - `扫码`：支持 ss / ssr 以及 `Quantumult X 格式的` trojan / vmess /http(s) 节点二维码

##### a.2 通过 `引用(订阅)` 添加节点

> ⚠️ 默认支持 ss / ssr 订阅链接，后续不对 ss / ssr 订阅链接做演示
>
> 订阅后，订阅信息会出现在配置文件的 `[server_remote]` 部分
>
> - 通过 `iCloud` / `本地(我的iPhone)` 下的 `节点配置片段` 导入个人节点
>
>   > - 新建节点配置片段：
>   >
>   >   `设置` > `配置文件` > `新建配置片段` > 选择 `节点`
>   >
>   > - 编辑节点配置片段：
>   >
>   >   文本框中填写节点信息
>   >
>   >   > - 以 `trojan` 节点为例
>   >   >
>   >   >   Quantumult X 可识别格式
>   >   >
>   >   >   ```
>   >   >   trojan=example.com:443, password=pwd, over-tls=true, tls-verification=false, fast-open=false, udp-relay=false, tag=节点名称
>   >   >   ```
>   >   >
>   >   >   Quantumult X 不识别的格式
>   >   >
>   >   >   ```
>   >   >   trojan://password@example1.com:443?allowInsecure=1#节点名称
>   >   >   ```
>   >
>   > - 保存节点配置片段：
>   >
>   >   右上角 `保存` > `输入文件名`文件名可以包含中文(空格除外) > `好`
>   >
>   >   > 关闭` iCloud资源文件夹`
>   >   >
>   >   > 节点配置片段保存至 `本地` 路径下的 `我的iPhone/Quantumult X/Profiles/`
>   >
>   >   > 打开` iCloud资源文件夹`
>   >   >
>   >   > 节点配置片段保存至 `iCloud` 路径下的 `iCloud/Quantumult X/Profiles/`
>   >
>   > - 导入节点配置片段：
>   >
>   >   如果配置文件中节点信息不是 Quantumult X 格式，需要打开资源解析器
>   >
>   >   `设置` > `节点` > `引用(订阅)` > 右上角`添加` > 地址栏中输入保存的`文件名` > `确定`
>   >
>   >   ⚠️ 开启iCloud资源文件夹后，默认使用`iCloud`路径下的文件，`我的iPhone`路径不被读取
>
> - 通过 `订阅链接` 导入节点
>
>   > - Quantumult X 格式的订阅链接
>   >
>   >   链接示例：
>   >
>   >   ```
>   >   https://hxlm.cc/api/v1/client/subscribe?token=example
>   >   ```
>   >
>   > - Quantumult X 无法识别的订阅链接
>   >
>   >   可打开 `资源解析器` 进行导入；
>   >
>   >   也可使用 `在线API订阅转换器` 转换后导入
>   >
>   >   > 在线 API 订阅转换器：https://dove.589669.xyz/web
>   >   >
>   >   > 输出类型请选择  `节点订阅` 

#### b. 通过手动修改配置文件进行添加节点

> `设置` > `配置文件` > `编辑`
>
> 编辑配置文件 `[server_local]` 部分
>
> - **SS/SSR 节点写法**
>
>   略
>
> - **trojan 节点写法**
>
>   ```
>   trojan=example.com:443, password=pwd, over-tls=true, tls-verification=false, fast-open=false, udp-relay=false, tag=节点名称
>   ```
>
> - **v2ray(vmess) 节点写法**
>
>   ```
>   vmess=example.com:443, method=chacha20-ietf-poly1305, password=pwd, obfs-host=example.com, obfs=wss, obfs-uri=/ws, tls-verification=true, fast-open=false, udp-relay=false, tag=节点名称
>   ```
>
> - **http(s)节点写法**
>
>   ```
>   http(s)=example.com:443(端口号根据实际端口填写), username=可选, password=可选, fast-open=false, udp-relay=false, tag=节点名称
>   ```

### 4. 开始使用

**我们可以根据使用需求，手动将 Quantumult X 的代理模式切换为 `全部代理`、`全部直连`、`规则分流` 三种模式** ;

> - `全部代理`
>
>   所有的网络请求都将通过 proxy 下选中的节点进行。
>
> - `全部直连`
>
>   顾名思义，就是所有网络请求将不使用任何代理进行。
>
> - `规则分流`
>
>   根据 **分流规则** 将网络请求进行分流，网络请求的走向(是否能成功访问)由匹配到的 **策略组** 决定；
>
>   **策略组** 将 **分流规则** 传递过来的网络请求进行分发。

在没有配置`策略组`和`分流规则`之前，建议使用 `全部代理` 模式进行网络访问，下期教程开始介绍策略组和分流规则。



## 二、Quantumult X小白系列教程｜基础使用：认识策略组和分流规则，利用大佬们的策略组和分流规则，实现自动分流，让 Quantumult X 更加智能

❗️**`视频教程地址：`**https://youtu.be/wNwpnxmTAJ8

### 1. 策略组

- 策略组 包含 若干节点，也可包含 子策略(组)
- 策略组 服务于 分流规则
- 不同策略组可根据用户个人习惯进行先后排序
- 配置文件中对应的模块：**`[proxy]`**

#### a. Quantumult X 内置的 4 种策略组

> **static** / 静态策略组 (常用)
>
> Available / 健康检查策略组 (略)
>
> Robin / 轮询策略 (略)
>
> SSID / 服务集策略 (略)

#### b. Quantumult X 内置的 3 种策略

> **Proxy** / 代理
>
> **Direct** / 直连
>
> **Reject** / 拒绝

#### c. 添加策略组(举例说明)

> - ```
>   static=GMedia, Outside, proxy, direct, img-url=https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/IconSet/GMedia.png
>   ```
>
>   >static：这是一条 静态策略组
>   >
>   >=GMedia,：策略组命名为 GMedia
>   >
>   >Outside, proxy, direct：表示在 GMedia 这条策略组下可以选择用哪些策略(组)或节点
>   >
>   >img-url=：策略组在Quantumult X首页采用的图标(icon)
>
>   这是一条名称为 GMedia 的、可以选择使用Outside策略(组)、proxy策略、direct策略的策略组
>
>   选中 Outside：将使用 Outside 的策略组中选中的节点进行网络访问
>
>   选中 proxy：将使用 proxy 下选中的节点进行网络访问
>
>   选中 direct：将不使用代理，通过直连的方式进行网络访问
>
> - ```
>   static= US Server, server-tag-regex= 美国|????????|US, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/US.png
>   ```
>
>   > static：这是一条 静态策略组
>   >
>   > = US Server：策略组命名为 US Server
>   >
>   > server-tag-regex=：根据节点名来筛选节点
>   >
>   > img-url=：策略组在Quantumult X首页采用的图标(icon)
>
>   这是一条筛选节点的策略组，如果导入的节点名称中有[美国]、[????????]、[US]其中任意一个，该节点将会出现在该策略组下。
>
>   这个策略组对于有多个机场订阅的用户来说，可以更方便的整理节点。



### 2. 分流规则

- 分流规则 是一个list文件

- 分流规则A 可以被 分流规则B 包含

- 分流规则 存在先后顺序，靠前规则优先生效，打乱顺序可能导致规则失效

  > 例如：GeQ1an 的 GMedia.list 规则中 已经包含了 Netflix.list / Spotify.list / YouTube.list
  >
  > 如果你要对 Netflix.list / Spotify.list / YouTube.list 进行重新排序，请确保它们位于 GMedia.list 前面

- 配置文件中对应的模块：**`[filter_remote]`/`[filter_local]`**

#### a. 分流规则工作原理

> list 文件内包含若干如下的域名列表：
>
> ```
> # > ABC
> HOST-SUFFIX,edgedatg.com,GMedia
> HOST-SUFFIX,go.com,GMedia
> 
> # > Abema TV
> USER-AGENT,AbemaTV*,GMedia
> HOST-SUFFIX,abema.io,GMedia
> HOST-SUFFIX,abema.tv,GMedia
> HOST-SUFFIX,akamaized.net,GMedia
> HOST-SUFFIX,ameba.jp,GMedia
> HOST-SUFFIX,hayabusa.io,GMedia
> ```
>
> 如果发起的**网络访问 命中**了**分流规则**列表中包含的域名，那么**访问请求**将会被**分发至**这条规则指定的**策略组**。访问成功与否取决于策略组

#### b. 添加分流规则

##### b.1 **添加** `[filter_remote]` 远程分流规则订阅

###### a. 在软件界面(UI)中直接添加分流规则

> 一次添加一条
>
> `Quantumult X 设置` > `分流` > `引用` > 右上角 `添加` - 输入资源链接
>
> ```
> https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/GMedia.list
> ```

###### b. 通过修改配置文件添加分流规则

> 一次可添加多条
>
> `Quantumult X 设置` > `配置文件` > `编辑` > `[filter_romote]` 模块
>
> 格式
>
> ```
> https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/GMedia.list, tag=GMedia 规则, enabled=true
> ```
>
> tag=：给分流规则命名，建议对应策略命名
>
> enabled=：是否启用该分流规则，true/启用、false/停用

##### b.2 **添加** `[filter_local]` 本地分流配置片段

###### a. 通过 `iCloud` / `本地(我的iPhone)` 下的 `分流配置片段` 导入分流规则

> 参考第一期教程：
>
> 1 - 新建 分流配置片段
>
> 2 - 导入 分流配置片段
>
> 反正我是小白，不会自己写分流规则，所以这里，略过

###### b. 通过修改配置文件添加

> `Quantumult X 设置` > `配置文件` > `编辑` > `[filter_local]` 模块
>
> 格式参考（鬼知道是什么意思）
>
> ```
> # 绕过企业证书过期
> host, ocsp.apple.com, reject
> 
> # 其它
> host-suffix, local, direct
> ip-cidr, 10.0.0.0/8, direct
> ip-cidr, 17.0.0.0/8, direct
> ip-cidr, 100.64.0.0/10, direct
> ip-cidr, 127.0.0.0/8, direct
> ip-cidr, 172.16.0.0/12, direct
> ip-cidr, 192.168.0.0/16, direct
> geoip, cn, Mainland
> final, Final
> ```

**如果 远程分流 和 本地分流 遇到相同规则，本地规则优先生效**

### 3. 为分流规则指定策略组

#### a. 手动为分流规则指定策略组(推荐)

> `Quantumult X 设置` > `分流` > `引用` - 选中规则左滑 - `编辑` - 打开 `策略偏好`
>
> 在弹出的选项中，选择对应的策略组

#### b. 使用`force-policy`强制指定策略组

> 举例：使用 force-policy 强制让 [GMedia 规则] 分流规则使用 [GMedia] 策略偏好
>
> ```
> https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/GMedia.list, tag=GMedia 规则, force-policy=GMedia, enabled=true
> ```
>
> - 如果已经存在 [GMedia] 策略组，则 [GMedia 规则] 分流规则与 [GMedia] 策略组绑定；
> - 如果不存在 [GMedia] 策略组，则 `force-policy` 将强制自动生成一个只包含`direct`/直连 和 `reject`/拒绝 两个内置策略的 [GMedia] 策略组。
> - 在App首页长按该策略组图标，可以将已经导入的节点和二级策略组添加到该策略组下

### 4. 开始使用分流规则和策略组

- 在了解了策略组和分流规则后，我们就可以自己写策略组了，不过光有策略组没有分流规则等于啥都没有；

  分流规则要我们小白自己去写的话，估计能弄到崩溃，所以这里建议大家使用网上各位大佬们提供的分流规则；

  结合他们的分流规则来写符合你自己使用习惯的策略组。

- 这里给大家准备了一份配置文件，配置中包含`基础的策略组`和`分流规则`，以及上一期教程中提到的 `资源解析器`；通过 `下载` 导入新的配置文件会覆盖之前包括节点在内的所有配置。

- ❗️**`配置文件下载地址：`**

  ```
  hhttps://raw.githubusercontent.com/erdongchanyo/Rules/main/Quantumult%20X/quantumult_EDC-Lazy.conf
  ```

  配置文件中包含的策略组和规则有：

  - 国外连接策略` (添加了对应规则)`

  - 国外媒体策略 `(添加了对应规则)`

    > 国外媒体策略 / Netflix策略 / Youtube策略 / Spotify策略 / TikTok策略

  - 国内连接策略 `(添加了对应规则)`

  - 软件&服务策略 `(添加了对应规则)`

    > Telegram策略 / Twitter策略 / Apple策略 / TestFlight策略 / Microsoft策略 / Paypal策略 / LOL策略
    
  - 国内媒体策略 `(添加了对应规则)`
  - 网易云策略

  - 最终策略 `(添加了对应规则)`

  - 正则筛选服务器策略组

    > 美国节点策略组 / 香港节点策略组 / 台湾节点策略组 / 新加坡节点策略组 / 日本节点策略组
    >
    > 网易云音乐解锁服务器策略组

- 下载了配置文件后，只需要重新添加节点就可以开心的使用 Quantumult X 了



## 三、Quantumult X小白系列教程｜基础实战：创建网易云音乐解锁服务器节点策略组，利用分流规则，轻松解锁网易云音乐Netecase Music灰色(无版权)音乐

❗️**`视频教程地址：`**https://youtu.be/_XmUmRrizwg

### 1. 解锁网易云灰色音乐大致原理

- 利用QQ、酷我音乐等音乐平台的资源链接替换网易云灰色歌曲链接
- 有条件的盆友可以自己搭建解锁服务器
- 教程中用到的免费服务器均为网络收集，限制仅允许网易云音乐相关域名与 IP 通过代理，其余代理请求一律丢弃。

### 2. 下载、安装、信任证书

#### a. 下载证书

> Safari浏览器点击链接：https://raw.githubusercontent.com/nondanee/UnblockNeteaseMusic/master/ca.crt
>
> “此网站正尝试下载一个配置描述文件。您要允许吗？”
>
> 点击`允许`进行下载

#### b. 安装证书

> 进入`设置` > `通用` > `描述文件` > `已下载的描述文件`
>
> 选择 `UnblockNeteaseMusic Root CA` ，右上角点击 `安装`

#### c. 信任证书

> 进入`设置` > `通用` > `关于本机` > `证书信任设置` 下
>
> 开启 `UnblockNeteaseMusic Root CA` 

### 3. 添加网易云音乐`策略组`

> - Quantumult X `设置` > `配置文件` > `编辑`
>
> - 找到 `[policy]` 模块
>
> - 增加以下策略组
>
>   - 网易云音乐策略组
>
>     ```
>     static=Netease Music, direct, Netease Unblock Server, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Netease_Music_Unlock.png
>     ```
>
>     释义：这是一条叫做 `Netease Music` 的静态策略，可以选择 `直连` 、 `Netease Unblock Server策略组` 两种策略的策略组
>
>   - 网易云音乐解锁服务器筛选策略组（教程二中的 `正则筛选策略`）
>
>     ```
>     static= Netease Unblock Server, server-tag-regex= 解锁网易云, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Netease_Music.png
>     ```
>
>     释义：这是一条静态策略，通过 `server-tag-regex` 正则筛选，将导入的节点中包含 `解锁网易云` 的节点全部归纳到 `Netease Unblock Server` 策略组下

### 4. 添加网易云音乐`分流规则`

> - Quantumult X `设置` > `配置文件` > `编辑`
>
> - 找到 `[filter_remote]` 模块
>
> - 增加以下分流规则
>
>   ```
>   https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Optional/Netease%20Music.list, tag=Netease Music 规则, force-policy=Netease Music, update-interval=86400, opt-parser=false, enabled=true
>   ```
>
>   释义：这是一条分流规则，使用 `GeQ1an大佬` 的 `Netease Music.list` 分流规则，规则名称为 `Netease Music 规则`，每24小时(24x60分x60秒=86400秒)更新一次。

### 5. 导入网易云音乐解锁服务器节点

> - 将节点信息手动写入配置文件 `[server_local]` 模块下
>
>   - 不推荐，不方便管理
>
> - 通过 `远程订阅链接` 或远程 `包含解锁网易云节点信息的txt文件` 进行导入
>
>   - 不推荐，如果是别人上传的文件，文件内包含的节点信息如果失效，你无法维护
>
> - **通过 `配置文件` > `新建配置片段` 进行导入**
>
>   - `新建配置片段` > `节点`
>
>   - 弹出的文本框中增加以下节点信息(以下节点信息为Quantumult X可识别格式)，右上角 `保存`
>
>     文件名可以包含中文(空格除外)
>
>     ```
>     http=music.lolico.me:39000, fast-open=false, udp-relay=false, tag=解锁网易云节点1
>     http=block4music.poetyin.me:39000, fast-open=false, udp-relay=false, tag=解锁网易云节点2
>     shadowsocks=blockmusic.poetyin.me:30003, method=aes-128-gcm, password=desperadoj.com_free_proxy_emx2, fast-open=false, udp-relay=false, tag=解锁网易云节点3
>     shadowsocks=music.desperadoj.com:30001, method=aes-128-gcm, password=desperadoj.com_free_proxy_emx2, fast-open=false, udp-relay=false, tag=解锁网易云节点4
>     shadowsocks=music.desperadoj.com:30003, method=aes-128-gcm, password=desperadoj.com_free_proxy_emx2, fast-open=false, udp-relay=false, tag=解锁网易云节点5
>     ```
>
>     > - 打开` iCloud资源文件夹`
>     >
>     >   节点配置片段保存至 `iCloud` 路径下的 `iCloud/Quantumult X/Profiles/`
>     >
>     > - 关闭` iCloud资源文件夹`
>     >
>     >   节点配置片段保存至 `本地` 路径下的 `我的iPhone/Quantumult X/Profiles/`
>
> - `节点` > `引用(订阅)` > 右上角 `添加` > 输入 `文件名`
>
>   ⚠️ 开启iCloud资源文件夹后，默认使用`iCloud`路径下的文件，`我的iPhone`路径不被读取
>
>   如果文件内的节点信息不是Quantumult X可识别格式，请打开 `资源解析器`
>
>     > 资源解析器 安装请参考 [教程一：安装资源解析器](#1.1 首先，给你的Quantumult X增加一个小工具：资源解析器)

### 6. 搞定，解锁网易云灰色音乐

> `Netease Music` 策略下可选 `直连` 、 `Netease Server策略组`
>
> > - `直连`：
> >
> >   使用你当前手机正常网络访问网易云音乐
> >
> >   / 搜索“周杰伦 晴天”，搜索结果呈灰色，不可播放
> >
> > - `Netease Server策略组`：
> >
> >   使用 `Netease Unblock Server` 策略组下选中的 `解锁网易云音乐服务器` 访问网易云音乐
> >
> >   需要切换节点时，直接在 `Netease Unblock Server` 策略组下进行
> >
> >   / 搜索“周杰伦 晴天”，搜索结果正常可播放



## 四、Quantumult X小白系列教程｜进阶使用：了解重写和MITM解密，实现广告屏蔽、TikTok不拔卡区域解锁、Youtube广告屏蔽

❗️**`视频教程地址：`**https://youtu.be/QaMxTYuYU6U

### 1. 了解重写 / MITM解密

- 简单来说，重写 和 mitm解密 主要用来去广告以及某些重定向，去广告就不用说了，至于什么叫重定向咱也不太懂，反正我在网上看的就是：比如将 `google.cn` 重定向 `google.hk`
- 配置文件中对应的模块：**`[rewrite]` / `[mitm]`  ** 

### 2. MITM解密

- 官方解释：mitm 根证书用于 https 解析，只有配置了主机名的请求才会被 mitm 模块进行解析。

  > - 主机名：对应配置文件中 `[mitm]` 模块下的 `hostname=` 后面的内容
  > - 我的理解，它就是一个本地证书，反正开启就行：先生成证书、再配置证书(安装证书、信任证书)、然后打开开关。
  > - 想要使用 Quantumult X `解锁TikTok` 等高级玩法，就必须开启 `mitm`。

- 开启步骤：

  > Quantumult X `设置` > `MitM` > `生成证书` > `配置证书`(安装并信任、参考 `安装网易云音乐证书`)
  >
  > 证书安装完成、打开 `MitM` 开关

### 3. 重写脚本(网上其它教程习惯叫做 `复写脚本`)

- 官方解释(我也不懂)：用于修改 HTTP 或 HTTPS 请求和响应

  > 不需要也没必要搞懂，对于我们这样的小白用户，直接引用各位大佬的重写规则就好了，要啥自行车？

- 添加 `[rewrite_remote]` 远程重写脚本订阅

  > - 小白应该也不会自己写脚本，建议直接引用`远程重写订阅`
  >
  >   `设置` > `重写` > `引用` > 右上角 `添加` > 输入远程重写订阅地址
  >
  >   > 举例 `神机通用重写订阅`
  >   >
  >   > ```
  >   > https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Rewrite/General.conf
  >   > ```
  >   >
  >   > 规则内包含主机名 `hostname` 以及重写 `rewrite` 规则
  >
  > - 当然也可以引用下载到 iCloud / 本机路径下的 `.conf` 配置文件
  >
  >   > `iCloud` 文件路径：`iCloud/Quantumult X/Profiles/`
  >   >
  >   > `本地` 文件路径：`我的iPhone/Quantumult X/Profiles/`
  >   >
  >   > 导入方法：直接输入  `文件名.conf`
  >
  >   ⚠️ 开启iCloud资源文件夹后，默认使用`iCloud`路径下的文件，`我的iPhone`路径不被读取
  >
  >   ⚠️ 下载回来的脚本需要定期手动下载新版本进行替换

- 添加 `[rewrite_local]` 本地重写脚本

  > - `设置` > `配置文件` > `编辑` >  `[rewrite_local]` 模块
  >
  > - 支持引用 iCloud / 本地 / 远程路径，文件格式为 .js
  >
  >   - iCloud / 本地  `.js `文件 (开启iCloud资源文件夹后默认使用iCloud路径下的配置文件)
  >
  >     > - 脚本文件在哪里弄？
  >     >
  >     >   > 自己写 > 会么？不会！
  >     >   >
  >     >   > 各位大佬无私奉献，可以下载保存至 iCloud 或者 本地
  >     >
  >     > - 脚本文件储存路径
  >     >
  >     >   > iCloud 文件路径：`iCloud/Quantumult X/Scripts/`
  >     >   >
  >     >   > 本地 文件路径：`我的iPhone/Quantumult X/Scripts/`
  >
  >   >   >脚本引用方法：直接输入 `脚本文件名.js`
  >   >
  >   >   ⚠️ 开启iCloud资源文件夹后，默认使用`iCloud`路径下的文件，`我的iPhone`路径不被读取
  >
  >   - 远程路径 `.js` 文件 `Store版本 1.0.5+版本可用`
  >
  >     > 举例 `获取Netflix剧集评分(by yichahucha)`
  >     >
  >     > ```
  >     > ^https?://ios\.prod\.ftl\.netflix\.com/iosui/user/.+path=%5B%22videos%22%2C%\d+%22%2C%22summary%22%5D url script-request-header https://raw.githubusercontent.com/yichahucha/surge/master/nf_rating.js
  >     > ^https?://ios\.prod\.ftl\.netflix\.com/iosui/user/.+path=%5B%22videos%22%2C%\d+%22%2C%22summary%22%5D url script-response-body https://raw.githubusercontent.com/yichahucha/surge/master/nf_rating.js
  >     > ```
  >     >
  >     > MitM模块下，hostname后添加`ios.prod.ftl.netflix.com`
  >
  >   - 修改路径+正则表达式
  >
  >     > 举例 `AK视频重写规则`
  >     >
  >     > ```
  >     > ^http:\/\/tingyun\.info\/api\/community\/edit url response-body "code":\d+, response-body "code":200
  >     > ^http:\/\/tingyun\.info\/api\/user\/personal url response-body .+ response-body {   "code": 200,   "msg": "个人信息",   "time": "1666534199",   "data": {     "id": 108267,     "group_id": 0,     "parentid": 0,     "area": "",     "imei": "",     "xqx": "",     "is_change": 0,     "hl": "",     "jyyx": "",     "guanzhu": 0,     "fensi": 0,     "number": "JSJYJE",     "photo": "http:\/\/yfui.club0",     "num_t": 0,     "num": "-1",     "t_number": "208",     "vip_time": "2099-09-08",     "integral": 0,     "power": 0,     "agent": 0,     "username": "Mango_444603",     "nickname": "Mango_444603",     "password": "6ec639b8718fdc65201c1ec0a6bc9308",     "salt": "l05aGW",     "email": "",     "mobile": "14725836920",     "avatar": "http:\/\/tupian.ds9rsqa.cn\/mrtx\/48_1588741687.jpg",     "level": 1,     "gender": 0,     "birthday": null,     "bio": "",     "money": "0.00",     "fencheng": 0,     "weichat": "客服QQ\/微信：928355547",     "yitian": "",     "yitianyuan": "",     "qitian": "",     "qitianyuan": "",     "shiwu": "",     "shiwuyuan": "",     "yiyue": "",     "yiyueyuan": "",     "sanyue": "",     "sanyueyuan": "",     "liuyue": "",     "liuyueyuan": "",     "yinian": "",     "yinianyuan": "",     "yongjiu": "",     "yongjiuyuan": "",     "yitianurl": "",     "qitianurl": "",     "shiwuurl": "",     "yiyueurl": "",     "sanyueurl": "",     "liuyueurl": "",     "yinianurl": "",     "yongjiuurl": "",     "url8": "",     "url9": "",     "score": 0,     "successions": 1,     "maxsuccessions": 1,     "prevtime": 1663603948,     "logintime": 1663603948,     "loginip": "120.235.69.55",     "loginfailure": 0,     "joinip": "120.235.69.55",     "jointime": 1663603948,     "createtime": 1663603948,     "updatetime": 1663603948,     "token": "",     "status": "normal",     "verification": "",     "age": 0,     "is_okami": 0,     "view_num": 0,     "is_verifyed": 0,     "v_num": 0,     "device_code": "acb1616e2f8e3130b32ff868773eb8a2",     "tj_user_count": 0,     "video": 0,     "fabu": 0,     "today_invite_number": 0,     "invite_number": 0,     "vip": 1,     "read": 0,     "prevtime_text": null,     "logintime_text": null,     "jointime_text": null,     "avatar_text": "http:\/\/tupian.ds9rsqa.cn\/mrtx\/48_1588741687.jpg"   } }
  >     > ```
  >     >
  >     > MitM模块下，hostname后添加`tingyun.info`
  

### 4. 重写实战应用

#### a. 添加 `神机去广告重写订阅`(共2条)

> ```
> https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Rewrite/Block/Advertising.conf
>
> https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Rewrite/Block/AdvertisingPlus.conf
> ```
>
> 我们在浏览器打开规则网址，看一下内容，以 `zhihu` 一段为例
>
> 禁用重写，进入知乎app，可以看到有推送的广告内容
>
> 启用重写，重新进入知乎app，广告内容全部消失。

#### b. 添加 `TikTok区域解锁重写订阅`（

> - 17.9.0以上版本
>     > ```
>     > https://raw.githubusercontent.com/Tartarus2014/Surge-Script/master/Unlock/TikTokUS.sgmodule
>     > ```
>     >
>     > `烧烤哥` 大佬目前提供的远程TikTok区域解锁重写一共可以解锁5个区域，圈x使用时请打开 资源解析器
>     >
>     > 分别为：日本`JP`、韩国`KR`、台湾`TW`、英国`UK`、美国`US`
>     >
>     > 如果要修改解锁区域，只需将订阅地址中最后 `TikTokUS.sgmodule` 中的区域代码 `US` 进行替换即可
>     >
>     > ⚠️ TikTok 区域解锁重写一次只可启用一个，不可多个地区同时使用；
>
#### c. 添加 `神机去Youtube广告重写订阅`

> ```
> https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Rewrite/Block/YouTubeAds.conf
> ```
>
> ⚠️ 用于跳过视频开头的广告（需要5秒后手动跳过的广告）



- 到这一步，是不是发现 `Quantumult X` 在某些方面比传统的 `Shadowrocket` 好玩多了
- 当然，还有其它更多好玩的重写订阅，自己去发现吧～



## 五、Quantumult X小白系列教程｜进阶使用：了解task_local，配合重写功能、利用crontab命令，玩转圈X定时脚本任务，各种签到薅羊毛整起来

❗️**`视频教程地址：`**https://youtu.be/HrrOXEvrXBA

### 1. 了解任务脚本

- 通过 `crontab命令`，在固定时间 或 间隔时间 执行指定的 JS 脚本。
- 配置文件中对应的模块 **`[task_local]`**
- 大部分任务脚本需要对应的 `本地重写` **`[rewrite_local]`** 脚本文件支持， [参考“添加本地重写脚本”部分](#3. 重写脚本(网上其它教程习惯叫做 `复写脚本`))
- Quantumult X UI界面中对应的入口：`设置` > `调试` > `构造请求`

### 2. crontab 命令简单说明

- 格式

  > `* * * * * example.js`

- 解释

  >|      |  *   |  *   |  *   |  *   |         *          | /path/example.js |
  >| :--: | :--: | :--: | :--: | :--: | :----------------: | :--------------: |
  >| 意义 | 分钟 | 小时 |  日  |  月  |       星期几       | 被执行的脚本路径 |
  >| 格式 | 0-59 | 0-23 | 1-31 | 1-12 | 0-7 (0和7为星期天) |                  |

### 3. 如何添加任务

#### a. 通过`引用本地任务脚本`添加任务

- 任务脚本自己会写么？不会！所以想在本地引用的话就只能把大佬们的脚本下载回来，慢慢用

  > iCloud文件路径：`iCloud/Quantumult X/Scripts` 
  >
  > 我的iPhone文件路径：`我的iPhone/Quantumult X/Scripts` 
  >
  > 引用方法：`[task_local]` 模块下直接使用 `crontab命令` 调用
  >
  > 引用格式：`0 9 * * * example.js`

  ⚠️ 开启iCloud资源文件夹后，默认使用`iCloud`路径下的文件，`我的iPhone`路径不被读取

#### b. 通过`引用远程路径任务脚本`添加任务

- 大佬们一般都会在说明文档或者js文档的开头注释清楚脚本使用方法

  其中一般都会有针对 Quantumult X 的说明，按照说明来复制粘贴就行

- 举例：`京东多合一签到脚本` (by NobyDA)

  > [task_local]
  >
  > ```
  > https://raw.githubusercontent.com/NobyDa/Script/master/JD-DailyBonus/JD_DailyBonus.js, tag=京东多合一签到, img-url=https://raw.githubusercontent.com/Orz-3/task/master/jd.png, enabled=true
  > ```
  >
  > `tag=` 任务脚本名称
  >
  > `img-url=` 任务脚本在 `设置` > `调试` > `构造请求` 中的图标
  >
  > [rewrite_local]
  >
  > ```
  > https:\/\/api\.m\.jd\.com\/client\.action.*functionId=signBean url script-request-header https://raw.githubusercontent.com/NobyDa/Script/master/JD-DailyBonus/JD_DailyBonus.js
  > ```
  >
  > [mitm]
  >
  > ```
  > hostname = api.m.jd.com
  > ```
  >
  > 

### 4. 任务脚本实战举例 - 腾讯视频签到 (by [chavyleung](https://github.com/chavyleung/scripts/tree/master/videoqq))

#### a. 脚本本地引用 (引用本地重写脚本和本地任务脚本)

- 作者提供配置方法
  需将 `本地重写[rewrite_local]脚本`和`任务[task_local]脚本`下载至 `iCloud` 或 `我的iPhone` 的 `/Quantumult/Scripts `路径下

  > ```
  > [MITM]
  > *.video.qq.com
  > 
  > [rewrite_local]
  > ^https:\/\/access.video.qq.com\/user\/auth_refresh url script-request-header videoqq.cookie.js
  > 
  > [task_local]
  > 1 0 * * * videoqq.js
  > ```

#### b. 脚本远程引用 (引用远程重写脚本和本地任务脚本)

- 用Chrome扩展[Enhanced GitHub](https://chrome.google.com/webstore/detail/enhanced-github/anlikcnbgdeidpacdbdljnabclhahhmd) 获取Github文件真实链接

  再加上[Orz-3](https://github.com/Orz-3/task)大佬收集的task任务图标

  > ```
  > [MITM]
  > *.video.qq.com
  > 
  > [rewrite_local]
  > ^https:\/\/access.video.qq.com\/user\/auth_refresh url script-request-header https://raw.githubusercontent.com/chavyleung/scripts/master/qqmusic/qqmusic.cookie.js
  > 
  > [task_local]
  > 1 0 * * * https://raw.githubusercontent.com/chavyleung/scripts/master/videoqq/videoqq.js, tag=腾讯视频签到, img-url=https://raw.githubusercontent.com/Orz-3/task/master/videoqq.png, enabled=true
  > ```

  完美

<!--more-->
