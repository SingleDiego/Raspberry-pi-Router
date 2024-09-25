# Raspberry-pi-Router

本文记录一下使用 Raspberry Pi 4b 刷入 OpenWrt 系统，并作为旁路由使用的过程。

<br>
<hr>
<br>

### 1.固件选择

树莓派使用的 OpenWrt 固件我选择了恩山论坛 bleach1991 编译的版本。

详见：https://www.right.com.cn/forum/forum.php?mod=viewthread&tid=8379758

下载地址：https://openwrt.mpdn.fun:8443/?dir=lede/bcm/

我使用的是树莓派4b的 mini 版固件。

<br>
<hr>
<br>

### 2.烧录固件到SD卡

我使用 rufus 软件把固件烧录到 SD 卡中：

![](https://github.com/SingleDiego/Raspberry-pi-Router/blob/main/imgs/01.png)

烧录完毕后把 SD 卡插入树莓派。

<br>
<hr>
<br>

### 3.登录 OpenWrt 管理后台

此时把树莓派接通电源开机，无需插入网线，可在电脑或手机等设备的无线连接界面看到一个名为 BleachWrt 的 wifi，（该 wifi 名称会根据固件版本不同而有所不同）。

连接该 wifi，在浏览器访问 192.168.1.1，即可打开路由器的管理后台，用户名为：root，默认密码为：password（这些信息也会根据固件版本不同而有所区别）。


