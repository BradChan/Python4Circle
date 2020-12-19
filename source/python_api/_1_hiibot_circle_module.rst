=======================
hiibot_circle模块
=======================

编程圆的Python解释器带有多种内置的Python模块，包括数字I/O(digitalio)、模拟I/O(analogio)、脉宽调制I/O(pwmio)、
I/O总线(busio)等计算机系统的基本输入和输出，同时还包括编程圆板载硬件资源控制模块(hiibot_circle)。

hiibot_circle模块通过“HBCircle”类实现编程圆的全部硬件资源，并使用“hbc”实例化所有接口。因此，
使用下面的语句即可导入编程圆的全部板载资源：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc

用法示例如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc
  import time
  hbc.fillPixels( (0,255,255) )
  while True:
      time.sleep(1)

此示例中，首先从hiibot_circle导入“hbc”实例对象，并导入“time”模块；然后调用“hbc”的填充彩色灯珠接口“fillPixels()”
使得所有灯珠显示青色(RGB值为(0,255,255))。

