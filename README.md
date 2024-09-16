# 仓库说明 
仓库代码来源于[ophub](https://github.com/ophub/amlogic-s9xxx-armbian)仓库，主要构建rk3399相关设备的固件

# Armbian

Armbian（中文名：岸边）系统是基于 Debian/Ubuntu 而构建的专门用于 ARM 芯片的轻量级 Linux 系统。Armbian 系统精益、干净，并且 100% 兼容并继承了 Debian/Ubuntu 系统的功能和丰富的软件生态，可以安全稳定地运行在 TF/SD/USB 及设备的 eMMC 里。这个项目保留了 Armbian 官方系统的完整性，并进一步拓展了在电视盒子等一些非官方支持设备上的使用，增加了一些便捷操作指令。现在你可以将电视盒子的安卓 TV 系统更换为 Armbian 系统，让他成为一台功能强大的服务器。

## 其他发行版

- [amlogic-s9xxx-openwrt](https://github.com/ophub/amlogic-s9xxx-openwrt) 项目提供了在盒子中使用的 `OpenWrt` 系统，在支持 Armbian 的相关设备中同样适用。
- [unifreq](https://github.com/unifreq/openwrt_packit) 为晶晨、瑞芯微和全志等更多盒子制作了 `OpenWrt` 系统，属于盒子圈的标杆，推荐使用。
- [Scirese](https://github.com/Scirese/alarm) 在安卓电视盒子里测试了 `Arch Linux ARM` / `Manjaro` 系统的制作、安装和使用，具体详见他仓库中的相关说明。
- [7Ji](https://7ji.github.io/) 在他的博客中发表了一些在 Amlogic 平台上的逆向工程和开发的文章，比如以 ArchLinux 的方式安装 ArchLinux ARM 系统，对 Amlogic 平台的启动机制的介绍等。在他的 [ampart](https://github.com/7Ji/ampart) 项目中，提供了一款分区工具，能够读取并编辑 Amlogic 的 eMMC 分区表和 DTB 内分区，可以 100% 利用 eMMC 空间。在 [amlogic-s9xxx-archlinuxarm](https://github.com/7Ji/amlogic-s9xxx-archlinuxarm) 项目中提供了 `Arch Linux ARM` 系统的制作和使用方法。在 [YAopenvfD](https://github.com/7Ji/YAopenvfD) 项目中提供了另一个 openvfd 守护进程。
- [13584452567](https://github.com/13584452567) 是本仓库 `Rockchip` 系列设备的开拓者，因为他的分享而拓展了对 [EAIDK-610](https://github.com/ophub/amlogic-s9xxx-armbian/pull/991), [King3399](https://github.com/ophub/amlogic-s9xxx-armbian/pull/1080), [TN3399](https://github.com/ophub/amlogic-s9xxx-armbian/pull/1094), [Kylin3399](https://github.com/ophub/amlogic-s9xxx-armbian/pull/1132), [ZCube1-Max](https://github.com/ophub/amlogic-s9xxx-armbian/pull/1247), [tvi3315a](https://github.com/ophub/amlogic-s9xxx-armbian/pull/1687), [xiaobao](https://github.com/ophub/amlogic-s9xxx-armbian/pull/1698) 等众多 `Rockchip` 设备的支持，他也是 [TQC-A01](https://github.com/ophub/amlogic-s9xxx-armbian/pull/1638) 等 `Allwinner` 设备 [专用内核](https://github.com/13584452567/linux-6.6.y) 的维护者。他在 [论坛](https://github.com/ophub/amlogic-s9xxx-armbian/discussions/1634) 和 [问答区](https://github.com/ophub/amlogic-s9xxx-armbian/issues) 里提供了大量的技术支持和解决方案，为盒子圈的发展做出了巨大的贡献。
- [cooip-jm](https://github.com/cooip-jm) 在他的 [wiki](https://github.com/cooip-jm/About-openwrt/wiki) 里分享了很多 Armbian，lxc，docker，AdGuard 等应用的使用方法，推荐学习。


## 链接

- [cm9vdA](https://github.com/cm9vdA?tab=repositories)
- [ophub](https://github.com/ophub/amlogic-s9xxx-armbian)
- [armbian](https://github.com/armbian/build)
- [unifreq](https://github.com/unifreq)
- [kernel.org](https://kernel.org)

## License

The amlogic-s9xxx-armbian © OPHUB is licensed under [GPL-2.0](LICENSE)

