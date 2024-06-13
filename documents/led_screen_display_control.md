# LED Screen Display Control Instructions

- The configuration files are located in the [/usr/share/openvfd](../armbian-files/platform-files/amlogic/rootfs/usr/share/openvfd) directory of the `Armbian/OpenWrt` system. The command file for the `Armbian` system is at [/usr/sbin/armbian-openvfd](../armbian-files/platform-files/amlogic/rootfs/usr/sbin/armbian-openvfd), and the command file for the `OpenWrt` system is at [/usr/sbin/openwrt-openvfd](https://github.com/ophub/amlogic-s9xxx-openwrt/blob/main/make-openwrt/openwrt-files/common-files/usr/sbin/openwrt-openvfd). If they are not currently in the system, they can be manually uploaded, and file execution permissions can be assigned: `chmod +x /usr/share/openvfd/vfdservice /usr/sbin/*-openvfd`.

- Upgrade the system kernel to the latest version. The `Armbian` system uses the `armbian-update` command for upgrades. The `OpenWrt` system upgrades using `System Menu` → `Amlogic Service` → `Online Download Update`.

- Currently, `x96max.conf`, `x96maxplus.conf`, `h96max-x3.conf`, `hk1-x3.conf`, `hk1box.conf`, `tx3.conf`, `x96air.conf`, `x88pro-x3.conf` and other devices have been tested. Configurations for other devices can be modified by checking: [arthur-liberman/vfd-configurations](https://github.com/arthur-liberman/vfd-configurations) and [LibreELEC/linux_openvfd](https://github.com/LibreELEC/linux_openvfd/tree/master/conf). The second field value in the corresponding content in the configuration files from these two websites needs to be reduced by `1`. For example:

```yaml
vfd_gpio_clk='0,69,0'
vfd_gpio_dat='0,70,0'
```
Modify to:

```yaml
vfd_gpio_clk='0,68,0'
vfd_gpio_dat='0,69,0'
```

- Taking the configuration of [x96maxplus](../armbian-files/platform-files/amlogic/rootfs/usr/share/openvfd/conf/x96maxplus.conf) as an example: If the order of the displayed time text is incorrect, you can adjust the order of numbers in `vfd_chars='4,0,1,2,3'` to `vfd_chars='1,2,3,4,0'` for testing. If the time is displayed upside down, you can adjust the `first value 0x02` in `vfd_display_type='0x02,0x00,0x01,0x00'` to `0x01` for testing. The content displayed can be adjusted according to the specific situation of your device in `functions='usb apps setup sd hdmi cvbs'`.

- Rename the configuration file to `diy.conf` and upload it to the `/usr/share/openvfd/conf` directory, then enter the command `armbian-openvfd 99` for testing.

- The command `armbian-openvfd 0` can disable the LED display and clear the system process. Before each new configuration test, please first execute this disable command, and then execute `armbian-openvfd 99` to test the modified configuration.

- After the screen display is normal, you can add it to the boot autostart task, change the `15` in the following command to your `box number`:

```yaml
# Execute the following command in the terminal to enable the openvfd service
sed -i 's|^#*openvfd_enable=.*|openvfd_enable="yes"|g' /etc/custom_service/start_service.sh
sed -i 's|^#*openvfd_boxid=.*|openvfd_boxid="15"|g' /etc/custom_service/start_service.sh
```

- Everyone is welcome to test and share their device's configuration file (diy.conf) to benefit more people.

|  BoxName   | `BoxID` |  Armbian Command      |   OpenWrt Command       |  Function   |
| ---------- | ------- | --------------------- | ----------------------- | ----------- |
| x96max     |  11     |  armbian-openvfd 11   |   openwrt-openvfd 11    | Enable LED  |
| x96maxplus |  12     |  armbian-openvfd 12   |   openwrt-openvfd 12    | Enable LED  |
| x96air     |  13     |  armbian-openvfd 13   |   openwrt-openvfd 13    | Enable LED  |
| h96max-x3  |  14     |  armbian-openvfd 14   |   openwrt-openvfd 14    | Enable LED  |
| hk1-x3     |  15     |  armbian-openvfd 15   |   openwrt-openvfd 15    | Enable LED  |
| hk1box     |  16     |  armbian-openvfd 16   |   openwrt-openvfd 16    | Enable LED  |
| tx3        |  17     |  armbian-openvfd 17   |   openwrt-openvfd 17    | Enable LED  |
| tx3-mini   |  18     |  armbian-openvfd 18   |   openwrt-openvfd 18    | Enable LED  |
| t95        |  19     |  armbian-openvfd 19   |   openwrt-openvfd 19    | Enable LED  |
| t95z-plus  |  20     |  armbian-openvfd 20   |   openwrt-openvfd 20    | Enable LED  |
| tx9-pro    |  21     |  armbian-openvfd 21   |   openwrt-openvfd 21    | Enable LED  |
| x92        |  22     |  armbian-openvfd 22   |   openwrt-openvfd 22    | Enable LED  |
| whale      |  23     |  armbian-openvfd 23   |   openwrt-openvfd 23    | Enable LED  |
| x88pro-x3  |  24     |  armbian-openvfd 24   |   openwrt-openvfd 24    | Enable LED  |
| diy        |  99     |  armbian-openvfd 99   |   openwrt-openvfd 99    | Enable LED  |
| -          |  0      |  armbian-openvfd 0    |   openwrt-openvfd 0     | Disable LED |
| -          |  -u     |  armbian-openvfd -u   |   openwrt-openvfd -u    | Update Conf |

# LED 屏显示控制说明

- 配置文件放在 `Armbian/OpenWrt` 系统的 [/usr/share/openvfd](../armbian-files/platform-files/amlogic/rootfs/usr/share/openvfd) 目录下，`Armbian` 系统的命令文件位于 [/usr/sbin/armbian-openvfd](../armbian-files/platform-files/amlogic/rootfs/usr/sbin/armbian-openvfd)，`OpenWrt` 系统的命令文件位于 [/usr/sbin/openwrt-openvfd](https://github.com/ophub/amlogic-s9xxx-openwrt/blob/main/make-openwrt/openwrt-files/common-files/usr/sbin/openwrt-openvfd)。如果当前系统中没有的可以手动上传，并赋予文件执行权限：`chmod +x /usr/share/openvfd/vfdservice /usr/sbin/*-openvfd`

- 将系统的内核升级到最新版本。`Armbian` 系统使用 `armbian-update` 命令升级。`OpenWrt` 系统使用 `系统菜单` → `晶晨宝盒` → `在线下载更新` 功能升级。

- 目前有 `x96max.conf`、`x96maxplus.conf`、`h96max-x3.conf`、`hk1-x3.conf`、`hk1box.conf`、`tx3.conf`、`x96air.conf` 和 `x88pro-x3.conf` 等设备经过测试，其他设备的配置可以查看：[arthur-liberman/vfd-configurations](https://github.com/arthur-liberman/vfd-configurations) 和 [LibreELEC/linux_openvfd](https://github.com/LibreELEC/linux_openvfd/tree/master/conf) 进行修改，需要把这两个网站中配置文件里对应内容中进行调整，把第二个字段的值减 `1` 后使用，如：

```yaml
vfd_gpio_clk='0,69,0'
vfd_gpio_dat='0,70,0'
```
修改为：

```yaml
vfd_gpio_clk='0,68,0'
vfd_gpio_dat='0,69,0'
```

- 以 [x96maxplus](../armbian-files/platform-files/amlogic/rootfs/usr/share/openvfd/conf/x96maxplus.conf) 的配置为例：如果显示的时间文字顺序不正确，可以调整 `vfd_chars='4,0,1,2,3'` 的数字顺序为 `vfd_chars='1,2,3,4,0'` 等进行测试。如果时间是翻转显示，可以调整 `vfd_display_type='0x02,0x00,0x01,0x00'` 中的 `第一个值 0x02` 为 `0x01` 等进行测试。显示的内容可根据自己的设备支持的具体情况调整 `functions='usb apps setup sd hdmi cvbs'` 中的值。

- 将配置文件命名为 `diy.conf` 并上传至 `/usr/share/openvfd/conf` 目录下，输入命令 `armbian-openvfd 99` 进行测试。

- 通过命令 `armbian-openvfd 0` 可以禁用 LED 显示并清除系统进程，在每次测试新的配置前，请先执行此禁用命令，再执行 `armbian-openvfd 99` 进行更改后的配置测试。

- 屏幕显示正常后，可以添加至开机自启动任务，下面命令中的 `15` 改为你的 `盒子编号` ：

```yaml
# 在终端执行以下命令启用 openvfd 服务
sed -i 's|^#*openvfd_enable=.*|openvfd_enable="yes"|g' /etc/custom_service/start_service.sh
sed -i 's|^#*openvfd_boxid=.*|openvfd_boxid="15"|g' /etc/custom_service/start_service.sh
```

- 欢迎大家测试后分享自己设备的配置文件（ diy.conf ），让更多人受益。

|  盒子名称   | `盒子编号` |  Armbian 使用命令      |   OpenWrt 使用命令       |   功能   |
| ---------- | -------- | --------------------- | ----------------------- | ------- |
| x96max     |  11      |  armbian-openvfd 11   |   openwrt-openvfd 11    | 启用 LED |
| x96maxplus |  12      |  armbian-openvfd 12   |   openwrt-openvfd 12    | 启用 LED |
| x96air     |  13      |  armbian-openvfd 13   |   openwrt-openvfd 13    | 启用 LED |
| h96max-x3  |  14      |  armbian-openvfd 14   |   openwrt-openvfd 14    | 启用 LED |
| hk1-x3     |  15      |  armbian-openvfd 15   |   openwrt-openvfd 15    | 启用 LED |
| hk1box     |  16      |  armbian-openvfd 16   |   openwrt-openvfd 16    | 启用 LED |
| tx3        |  17      |  armbian-openvfd 17   |   openwrt-openvfd 17    | 启用 LED |
| tx3-mini   |  18      |  armbian-openvfd 18   |   openwrt-openvfd 18    | 启用 LED |
| t95        |  19      |  armbian-openvfd 19   |   openwrt-openvfd 19    | 启用 LED |
| t95z-plus  |  20      |  armbian-openvfd 20   |   openwrt-openvfd 20    | 启用 LED |
| tx9-pro    |  21      |  armbian-openvfd 21   |   openwrt-openvfd 21    | 启用 LED |
| x92        |  22      |  armbian-openvfd 22   |   openwrt-openvfd 22    | 启用 LED |
| whale      |  23      |  armbian-openvfd 23   |   openwrt-openvfd 23    | 启用 LED |
| x88pro-x3  |  24      |  armbian-openvfd 24   |   openwrt-openvfd 24    | 启用 LED |
| diy        |  99      |  armbian-openvfd 99   |   openwrt-openvfd 99    | 启用 LED |
| -          |  0       |  armbian-openvfd 0    |   openwrt-openvfd 0     | 禁用 LED |
| -          |  -u      |  armbian-openvfd -u   |   openwrt-openvfd -u    | 更新配置  |
