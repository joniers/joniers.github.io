---
layout: post
title: 学习笔记之linux启动过程
---
#linux 启动流程
大致的流程如下：

 1. power on
 2. BIOS
 3. LILO/GRUB
 4. Kernel boot
 5. init进程启动
 6. mingetty
 7. shell (登录完成)

##init进程的初始化过程
init是linux的守护进程，是所有进程的父进程

	1. /sbin/init涉及到对/sbin/telinit,/sbin/getty的调用
	2. /etc/init/rc-sysinit.conf
	3. [initab]
	4. /etc/init.d/rcS
	5. /etc/init.d/rc
	6. /etc/rcN.d(指向init.d下面的软连接)
	7. /etc/init.d/rc.local




