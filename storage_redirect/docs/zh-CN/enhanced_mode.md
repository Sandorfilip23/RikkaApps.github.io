# 增强模式

<!-- TOC depthFrom:2 depthTo:3 -->

- [兼容性](#兼容性)
- [性能影响](#性能影响)
- [下载和安装](#下载和安装)
    - [安装前须知](#安装前须知)
    - [版本对应](#版本对应)
    - [Magisk 模块](#magisk-模块)
    - [重新启动 zygote](#重新启动-zygote)

<!-- /TOC -->

## 兼容性

支持 Android 6.0 - Android Q DP2

#### 其他特殊情况

* “TaiChi·Magisk”

  根据用户回报，目前（2019/3/4）似乎仍有不能同时使用的情况。请**使用下面的检测 app 确认运行情况**，如果出现问题请自行取舍。

## 性能影响

* 应用启动时间增加

  > 在 Google Pixel 2 上增加大约 0.025 秒，其中 0.010 秒来自文件监视，0.015 秒来自修复应用间交互

* 修复应用间交互（只在开启重定向的应用生效）
  
  在应用使用 ActivityManager 及与 Media Store 交互时产生可以忽略不记的开销

* 文件监视（在所有应用生效）

  发送记录会产生开销，但理论上与 Android 的 log 机制消耗一致（可以忽略不记）

## 下载和安装

我们暂时只提供 [Magisk](https://github.com/topjohnwu/Magisk) 模块，因为只有 Magisk 可以提供**可靠的**开机时执行脚本。

### 安装前须知

1. 请务必确认已经了解如何在无法进入系统时删除模块
2. 以防万一，请先备份整个设备的数据
3. 如果有 v12 以前的模块，必须删除

### 版本对应

| 应用版本    | Riru - Storage Redirect 版本 | Riru - Core 版本 |
|-------------|------------------------------|------------------|
| 1.6.3+      | v19.3+                       | v18+             |
| 1.5.2+      | v19.x                        | v16+             |
| 1.5.0-1.5.1 | v18.1                        | v16+             |
| 1.4.0-1.4.9 | v17                          | any              |
| 更早版本    | 不再支持                     |                  |

**注意，版本必须严格对应，否则轻则功能不正常，重则无法开机。**

### Magisk 模块

1. 下载 [Riru - Core v18](https://github.com/RikkaApps/Riru/releases/download/v18/magisk-riru-core-v18.zip) 
2. 下载 [Riru - Storage Redirect v19.4](https://github.com/RikkaApps/StorageRedirect-assets/releases/download/assets/magisk-riru-storage-redirect-v19.4.zip)
3. 在 Magisk 中安装这两个模块
4. 可选，下载 [检测 app](https://github.com/RikkaApps/Riru/releases/download/v17/app-release.apk) 来检查 Riru 是否正常工作
   
### 重新启动 zygote

> Riru v14 起内置此功能