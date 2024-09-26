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

然后再设置一下 wifi 的密码，在 ``网络→无线`` 中设置。

![](https://github.com/SingleDiego/Raspberry-pi-Router/blob/main/imgs/06.jpeg)


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

##### 修改旁路由 lan 口 IP

（待补充）

##### 修改旁路由网关

（待补充）

##### 修改旁路由 DHCP 和 DNS

（待补充）

##### 防火墙设置

（待补充）

<br>
<hr>
<br>

### 6.终端设置

把要使用旁路由的终端设备（电脑、手机等）连接主路由的 wifi，这时，终端设备的 IP 和网关等还是由主路由器的 DHCP 分配的，我们需要手动指定终端设备的 IP、网关和 DNS。

##### 设定 IP 地址

把终端设备 IP 设为和主路由、旁路由同一网段下又不与其他设备冲突的 IP。本例中主路由网段为 ``192.168.10.x``，所以终端设备可以设为 ``192.168.10.14``。

##### 设定子网掩码

设定为 ``255.255.255.0`` 即可。

以上两项如果不清楚，可以看看终端设备连接主路由时候自动获取的 IP 和子网掩码，手动设定时照抄即可。

##### 设定默认网关

把默认网关设定为旁路由的 IP，本例中旁路由 IP 设定为 ``192.168.10.110``，所以网关也是这个。

DNS 可以设定为和旁路由 IP 一样，也可以选择公共的 DNS。

![](https://github.com/SingleDiego/Raspberry-pi-Router/blob/main/imgs/05.png)

这样设置旁路由对于网络系统是非侵入性的，对主网络的影响最小，只对把网关设定为旁路由 IP 的设备产生影响，即使旁路由崩溃了也不会对主体网络产生影响。


