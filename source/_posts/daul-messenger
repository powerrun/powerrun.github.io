---
title: 利用Daul Messenger双开非社交应用
---
默认情况下，三星OneUI的Daul Messenger只支持双开社交应用。本文旨在记录通过ADB命令，在Daul Messenger用户空间下双开非社交应用。

## Quick Start

如果在机主空间（Owner, User 0）已经安装了想要双开的应用，则可以直接使用install-existing将应用安装到Daul Messenger用户
``` bash
adb shell pm install-existing --user [User ID of Daul Messenger] [Package Name]
```

## 后续问题
Dual Messenger默认情况下只为社交应用授权各种权限。因此对于需要相机、蓝牙等权限的应用，我们需要使用命令授权。

授权“相机”权限:
```
adb shell pm grant --user 96 [Package Name] android.permission.CAMERA
```

特别地，当授权“附近的设备”权限时，因为该权限隐含了不止一个具体权限，因此需要多次授权。

连接到已配对的蓝牙设备：
```
adb shell pm grant --user 96 [Package Name] android.permission.BLUETOOTH_CONNECT
```

向附近的蓝牙设备广播：
```
adb shell pm grant --user 96 [Package Name] android.permission.BLUETOOTH_ADVERTISE
```

发现附近的蓝牙设备并与其配对：
```
adb shell pm grant --user 96 [Package Name] android.permission.BLUETOOTH_SCAN
```
