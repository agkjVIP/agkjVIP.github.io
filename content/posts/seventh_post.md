---
title: "Purefast自动签到教程"
date: 2022-11-02T15:18:53+08:00
tags: ["教程"]
categories: [""]
draft: false
dropCap: false

---
## Windows系统&Linux系统

### 使用方法（支持多个机场）
### 在此[仓库](https://github.com/wzdnzd/aggregator)基础上
#### 1. 利用Github Actions签到（推荐）
+ 点击右上角`Fork`
+ **设置密钥：分别添加名（即`Name`）为 `AP_DOMAINS`、`AP_EMAILS`、`AP_PASSWORDS` 的密钥并填写对应的值（即`Value`）。如有多个账号(不论是同一机场与否)，需要在 `Value` 栏里一一填写并用 `||` 隔开**
[![添加密钥](https://s1.ax1x.com/2022/08/14/vNWxoj.png)](https://imgtu.com/i/vNWxoj)
[![密钥](https://s1.ax1x.com/2022/08/14/vU1lng.png)](https://imgtu.com/i/vU1lng)
+ 若要修改签到时间，可修改`.github/workflows/checkin.yml`文件的`cron`配置
[![修改签到时间](https://s1.ax1x.com/2022/08/14/vUSkjS.png)](https://imgtu.com/i/vUSkjS)
+ 在 Actions 页面启用 workflow，可先手动触发运行一次验证配置是否正确
[![手动触发](https://s1.ax1x.com/2022/08/14/vUlBFI.png)](https://imgtu.com/i/vUlBFI)

### 2. 本地运行
+ 克隆代码库
 ```shell
git clone https://github.com/wzdnzd/aggregator.git
```
+ 安装依赖库
```shell
pip install -U requests
```
+ 修改 `config.json` 配置文件
```ini
proxyServer: 代理服务器地址，非必需

waitTime: 0 ~ 24，模拟任意时间签到，非必需

retry: 失败时重试次数，非必需

domains：支持多个机场，必须

domain：机场主域名，必须

proxy：true | false，是否使用代理

email：注册时使用的email

password：密码
```

+ `windows` 操作系统可通过 `任务计划程序` 添加到定时任务，详见[Windows系统中设置Python程序定时运行](https://blog.csdn.net/CaiJin1217/article/details/81453940)
+ `Linux` 或 `MacOS` 可通过 `cron` 添加到定时任务（或登陆启动项），详见[利用Linux的crontab实现定时执行python任务](https://bbs.huaweicloud.com/blogs/333192)


## IOS系统
### 使用方法（不支持多个机场）
### 在此软件[快捷指令](https://apps.apple.com/app/shortcuts/id915249334)基础上
+ 使用[purefast自动签到](https://www.icloud.com/shortcuts/9eb3073898ff4142a4868263b8132b10)指令

+ 在快捷指令特定位置填写账号密码等信息!

+ 设置个人自动化

[![xHrXS1.png](https://s1.ax1x.com/2022/11/02/xHrXS1.png)](https://imgse.com/i/xHrXS1)

+ 编辑自动化-选择启用-当模块中设置自动化运行的时间(个人喜好)-执行模块中选择运行快捷指令即你刚刚导入的快捷指令-选择运行前不询问(若询问，该自动化需要手动运行)-选择运行是通知

[![xHyZC9.png](https://s1.ax1x.com/2022/11/02/xHyZC9.png)](https://imgse.com/i/xHyZC9)

[![xHyPBT.png](https://s1.ax1x.com/2022/11/02/xHyPBT.png)](https://imgse.com/i/xHyPBT)

+ 测试成功后即可



<!--more-->
