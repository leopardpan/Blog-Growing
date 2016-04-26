---
layout: post
title: "iBeacon 能为开发者做什么？"
date: 2016-04-06 11:25:06 -0700
description: ""
category: 技术分享
---

![ibeacon](/img/iBeacon.png)
<!--more-->

## 简介：  

* iOS7后苹果出的一项新技术，支持蓝牙4.0(或以上)的iOS设备，工作方式是低功耗蓝牙（BLE），一个 `iBeacon` 硬件设备在不做任何处理的情况下一般可使用两三年左右。
* 可实现地理围栏、室内定位等功能，测量距离：[iBeacon](https://developer.apple.com/ibeacon/) 通过设备的 `UUID` 可以检测到具体的 `iBeacon` 信息，如：`Major` ，`Minor` ，用来进行多个 `iBeacon` 区分，`RSSI` ，用来计算信号接受者到 `iBeacon` 信号发射硬件之间的距离。`identifier` : 用来区分某一块的 `iBeacon` 信号，`iBeacon` 信号接受者自定义。iBeacon信号会因为人或物而遮挡信息强度，影响iBeacon信号接收。
   
#### **iBeacon功能 对开发者使用的额外成本:**
* `iBeacon` 也属于一种定位功能，所以需要添加 `CoreLocation.framework` 。
* `App` 开发者需要开启定位功能需要配置：在 `Xcode` 的 `info.plist` 里面添加 `NSLocationAlwaysUsageDescription` 或 `NSLocationWhenInUseUsageDescription` 字段。（iOS7后该添加了该字段应用才会弹出 `是否允许应用访问用户的位置信息）。


#### **检测iBeacon信号对用户设备的必要条件：**
* 用户设备iOS7或更新操作系统。
* 用户蓝牙设备4.0或更新。
* 用户蓝牙设备必须开启。
* 用户设备定位服务必须开启，允许应用访问位置信息。

#### iBeacon 可以激活 App ：
* 条件：这个 `App` 能后台访问位置信息，并且具备上述功能(能正常检查iBeacon)。
* 现象：这个 `App` 即使没有启动(无进程), 当有被监测iBeacon信号出现时, 这个 `App` 能被唤醒, 没任何操作的情况下, 进程存活时间可长达几个小时。
* 影响：开发者对用户使用App的使用时长统计可能会出现失误, 这时开发者就需要借助第三方统计SDK了,例如： `TalkingData` SDK 等。


#### iBeacon功能对用户造成的影响:
* iBeacon如果在后台监测到信号时, 当屏幕处于锁频状态, 设备左下角会有这个 App 的icon, 对于这一现象具体怎么使用就要看开发者了。
 
