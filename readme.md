

设备：
联通utstarcom iptv机顶盒
型号：mc8638s
芯片：s905m
P/N号2706结尾。
内存1G+4G
过程
先将原版系统刷机成第三方系统，步骤参考如下链接：

https://blog.csdn.net/fatiaozhang9527/article/details/133285366
刷好后，找一个8g的u盘，使用rufus将armbian的镜像img文件刷写到u盘里，img文件我在这个仓库找到的s905的倒也能用，但是太大，所以使用的是armbian社区镜像：https://www.armbian.com/amlogic-s9xx-tv-box/
使用这个镜像需要将boot里的extlinux.conf文件中的fdt /dtb/amlogic/meson-gxl-s905x-p212.dtb更改为fdt /dtb/amlogic/meson-gxbb-p201.dtb。将u-boot-s905文件重命名为u-boot.ext（不重命名的话进不了系统）。

然后拔出u盘，插到机顶盒的usb口，注意需要插入远离hdmi接口的usb。然后在机顶盒系统中，恢复出厂设置，机顶盒就会重启，从u盘启动了。我并未尝试将系统写入emmc，只是尝试了在u盘运行。

这个版本的社区镜像还不错，装上之后wifi网卡自动识别出来了，不像有的镜像缺少网卡驱动。我之前也尝试过没有网卡驱动的镜像，有些使用modprobe 8189es加载驱动后就正常了，但有些没有8189es驱动，就很麻烦。

相同设备可以尝试此镜像，也欢迎相同设备的朋友推荐其它镜像。

来源：https://www.armbian.com/amlogic-s9xx-tv-box/
