---
title: 'Wyse 3040 使用 Arch Linux 黑屏'
author: 'qa'
timestamp: 1729432488941
---

现象: 启动过程中黑屏，继续等待仍然保持黑屏。但添加 nomodeset 参数启动能进入 tty。

解决方法: [https://wiki.archlinux.org/title/Intel_graphics#With_the_Intel_driver](https://wiki.archlinux.org/title/Intel_graphics#With_the_Intel_driver)

具体操作:

```shell
pacman -S xf86-video-intel
```

```shell
# /etc/X11/xorg.conf.d/20-intel.conf

Section "Device"
  Identifier "Intel Graphics"
  Driver "intel"
EndSection
```