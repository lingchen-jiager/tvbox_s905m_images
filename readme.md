存储联通iptv，utstarcom，s905m芯片的armbian镜像文件。

此镜像文件刷入u盘后，需要将extlinux.conf文件中的fdt /dtb/amlogic/**meson-gxl-s905x-p212**.dtb改为fdt /dtb/amlogic/**meson-gxbb-p201**.dtb
再将u-boot-s905改名为u-boot.ext,方可进入系统，否则会导致无法进入系统。

usb网口插到远离hdmi接口的那一个，然后在系统中恢复出厂设置，机顶盒会自动重启从u盘中运行，暂未尝试写入emmc。


来源：https://www.armbian.com/amlogic-s9xx-tv-box/
