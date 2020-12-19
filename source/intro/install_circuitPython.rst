==========================
33
==========================

编程圆模式
++++++++++++++++++++

编程圆支持MakceCode模式和CircuitPython模式，另外还有一个Bootlooder模式。
将编程圆通过USB插上电脑，当磁盘名称为CPXR1BOOT时，即为Bootloader模式。

.. image:: ../_static/intro/mode/cpxr1boot_drive.png

当磁盘名称为CIRCUITPY时，为CircuitPython模式，也就是我们使用Python编程模式。

.. image:: ../_static/intro/mode/circuitpy_drive.png

如果编程圆已经安装有CircuitPython固件，那么可以通过编程圆reset按钮来切换Bootlooder模式和CircuitPython模式，单击切换成CircuitPython模式或者重启运行Python程序，
双击切换成Bootloader模式。


安装或升级CircuitPython固件
++++++++++++++++++++++++++++++
如果编程圆未安装有CircuitPython固件或需要升级CircuitPython固件版本，可以通过Bootloader模式（即磁盘名称为“CPXR1BOOT”时），下载CircuitPython.uf2固件并拖到该磁盘即可。

.. note::  `CircuitPython下载`_ 

.. _CircuitPython下载: http://www.hibottoy.com:8080/static/install/pc/windows/HiiBotCircle/circuitpython.uf2

升级Bootloader固件
++++++++++++++++++++
如果有必要更新Bootloader固件，可以通过Bootloader模式，下载“cpxr1_bootloader.uf2”固件并拖到该磁盘就可完成升级

.. note:: `cpxr1_bootloader下载`_ 

.. _cpxr1_bootloader下载: http://www.hibottoy.com:8080/static/install/pc/windows/HiiBotCircle/cpxr1_bootloader.uf2


