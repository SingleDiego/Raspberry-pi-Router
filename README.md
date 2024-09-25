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

![](https://github.com/SingleDiego/Raspberry-pi-Router/blob/main/imgs/01.png =509.5*528.5)

烧录完毕后把 SD 卡插入树莓派。

<br>
<hr>
<br>

### 3.登录 OpenWrt 管理后台

此时把树莓派接通电源开机，无需插入网线，可在电脑或手机等设备的无线连接界面看到一个名为 ``BleachWrt`` 的 wifi，（该 wifi 名称会根据固件版本不同而有所不同）。

连接该 wifi，在浏览器访问 [192.168.1.1](192.168.1.1)，即可打开路由器的管理后台，用户名为：``root``，默认密码为：``password``（这些信息也会根据固件版本不同而有所区别）。

![](https://github.com/SingleDiego/Raspberry-pi-Router/blob/main/imgs/02.png)

<br>
<hr>
<br>

### 4.密码设置

首先修改路由器管理后台的登录密码，在 ``系统→管理权`` 处修改登录密码。

![](https://github.com/SingleDiego/Raspberry-pi-Router/blob/main/imgs/03.png)

然后再设置一下 wifi 的密码

（待补充）

<br>
<hr>
<br>

### 5.树莓派作为旁路由的接线方法

先来看一下一张网络拓朴图：

![](https://github.com/SingleDiego/Raspberry-pi-Router/blob/main/imgs/04.png)

图中可见旁路由在整个网络中的位置，只需要把树莓派的 ``LAN`` 口（也就是树莓派唯一的网口）和主路由的 ``LAN`` 口用网线连接起来即可。

<br>
<hr>
<br>

### 5.旁路由设置

###### 修改旁路由 lan 口 IP

（待补充）

###### 修改旁路由网关

（待补充）

###### 修改旁路由 DHCP 和 DNS

（待补充）

###### 防火墙设置

（待补充）

<br>
<hr>
<br>

### 6.终端设置

