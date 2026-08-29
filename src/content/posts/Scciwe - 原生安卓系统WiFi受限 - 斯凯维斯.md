---
title: 原生安卓系统WiFi受限
published: 2025-03-25
description: 原生的安卓系统的设置在中国部分不使用，所以需要更改一下
image: ./cover.jpg
tags: [安卓，原生系统，WiFi]
category: 手机
draft: false
---

## 原生安卓系统WiFi受限

1、首先打开手机的开发这模式，并且打开USB调试以及OEM引导解锁

2、下载ADB工具，并且解压到单独的文件夹里

3、在该文件夹里，按住Shift+鼠标右键，点击在此处打开Powershell窗口

4、使用数据线连接手机和电脑

5、在打开的cmd页面，输入

```
nginx
复制代码
adb devices
```

并在手机上点击允许该电脑调试 如果显示（其他机型会显示其他代码）

```
nginx
复制代码
1
2

List of devices attached PM1LHMA781401142     
unauthorized
```

则说明连接成功，可以执行ADB命令

6、依次输入以下代码

```javascript
javascript
复制代码
adb shell settings delete global captive_portal_http_url
```

```javascript
javascript
复制代码
adb shell settings delete global captive_portal_https_url
```

```csharp
csharp
复制代码
adb shell settings put global captive_portal_http_url http://connect.rom.miui.com/generate_204

```

# 原生安卓系统WiFi受限

```csharp
csharp
复制代码
adb shell settings put global captive_portal_https_url https://connect.rom.miui.com/generate_204每次输入完代码都点击下回车，执行完成后，打开飞行模式，并且关闭，或者直接重启手机再次连接WiFi即可。 如果无法连接，需要修改NTP时间服务器（非必须）

```

```
csharp
复制代码
adb shell settings put global ntp_server ntp.aliyun.com
```

之后重启手机即可  

### 评论

![](http://100.66.169.6:2502/static-file/fcd668e3-647e-48d1-93e7-cf0009f967f2/3a46fada-a9a2-4a2c-9f5a-7d3b7a5df27b.svg)

### 全部评论
