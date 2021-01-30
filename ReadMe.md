# ASUS X411UA 安装macOS Bigsur 



## 电脑配置

| 规格     | 详细信息                                            |
| -------- | --------------------------------------------------- |
| 电脑型号 | 华硕ASUS X411UA 笔记本电脑 ASUS VivoBook14          |
| 操作系统 | macOS BigSur 11.1                                   |
| 处理器   | 英特尔 酷睿 i5-8250U                                |
| 内存     | 8GB 2667MHz                                         |
| 硬盘     | 镁光1100 MTFDDAV256TBN 256G                         |
| 显卡     | Intel UHD Graphics 620                              |
| 显示器   | 14英寸 京东方BOE06F3                                |
| 声卡     | Conexant CX8050                                     |
| 网卡     | QCA9377 可更换为Dell DW1820A（我用的是Intel AX200） |

## 哪些可以工作得更好

- 使用[HIDPI](https://github.com/Ziloong/Lenovo-Air13-IWL-Hackintosh/blob/master/HIDPI)来提升系统UI质量

## BIOS推荐设置

- DVMT设置64M`
- 关闭CSM

## 处理器 : Intel Core i5-8250U

- 驱动 : [CPUFriend.kext](https://github.com/acidanthera/CPUFriend/releases) 
- 变频正常 

## 显卡 : Intel UHD Graphics 620

驱动 : [WhateverGreen.kext](https://github.com/acidanthera/WhateverGreen/releases)

使用 `DeviceProperties` 方法仿冒 `device-id` : `3EA6` , 注入 `ig-platform-id` , 默认使用 `59160000 ` 其他ID注入后闪屏或者有别的奇怪的问题。
HDMI 使用 `DeviceProperties` 方法 `framebuffer-con1-alldata` 注入 `framebuffer-con1-alldata` , 默认使用 `01050900 00080000 C7010000 02040A00 00080000 C7010000  ` 注入HDMI接口

Properties-显卡补丁方法说明（黑苹果小兵） : [Properties-显卡补丁一览表.pdf](https://github.com/Ziloong/ASUS-X411UA-Hackintosh-BigSur-Opencore0.6.5/blob/main/Properties%E6%96%B9%E6%B3%95/Properties-%E6%98%BE%E5%8D%A1%E8%A1%A5%E4%B8%81%E4%B8%80%E8%A7%88%E8%A1%A8.pdf)

## 声卡 : Conexant CX8050

- 驱动 : [AppleALC.kext](https://github.com/acidanthera/AppleALC/releases)
- 采用 `DeviceProperties` 方法注入 , 注入ID为13
- 内置音频输入输出正常

## 网卡 : 更换Intel AX200 （有条件可更换DW1820A 可完美隔空投送以及接力）

- 驱动 : [itlwm](https://github.com/OpenIntelWireless/itlwm)
- 无法隔空投送、接力

## 键盘

- 驱动 : [VoodooPS2Controller.kext](https://github.com/acidanthera/VoodooPS2/releases)

## 触控板 

- 驱动 : [VoodooI2C.kext 、VoodooI2CHID.kext](https://github.com/VoodooI2C/VoodooI2C/releases)

## USB : 端口定制 8086:9DED

- 驱动 : [SSDT-EC-USBX.aml]()
- 使用 [Hackintool](https://github.com/headkaze/Hackintool/releases) 定制USB
- 

## 电池

驱动 : [DSDT.aml]()

修改DSDT驱动,不会制作SSDT补丁

## 杂项

Kexts

- 添加驱动 [NoTouchID.kext](https://github.com/al3xtjames/NoTouchID/releases) 解决输入密码卡顿问题
- 添加必备驱动 [Lilu.kext](https://github.com/acidanthera/Lilu/releases)
- 添加SMC、电池、传感器驱动 [AsusSMC.kext 、VirtualSMC.kext 、SMCBatteryManager.kext 、SMCProcessor.kext](https://github.com/acidanthera/VirtualSMC/releases)

所使用到的软件

- [Hackintool](https://github.com/headkaze/Hackintool/releases)
- PlistEdit Pro

