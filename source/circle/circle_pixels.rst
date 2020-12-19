彩灯
================

HiiBot Circle具有10颗可控制彩灯，是在pixels列表中，例如第0颗彩灯hbc.pixels[0]。

设置彩灯颜色
-----------------

对每一颗彩灯设置颜色需要给定R（红色）、G（绿色）和B（蓝色）三个通道的值（0-255）。

.. note:: 设置第0颗灯的红色 hbc.pixels[0] = (255,0,0)

示例1：设置第0颗彩灯红色，第1颗彩灯绿色，第2颗彩灯蓝色

.. code-block:: python

   from hiibot_circle import hbc

   while True:
      hbc.pixels[0] = (255, 0, 0)
      hbc.pixels[1] = (0, 255, 0)
      hbc.pixels[2] = (0, 0, 255)


设置彩灯亮度
-----------------

彩灯的亮度调整也是通过hbc.pixels。只需要设置hbc.pixels.brightness的值，范围为[0.0~1.0]。
当亮度设置为0时，则所有灯都灭状态。

示例2：在示例1的基础上，初始彩灯亮度

.. code-block:: python

   from hiibot_circle import hbc

   hbc.pixels.brightness = 0.5

   while True:
      hbc.pixels[0] = (255, 0, 0)
      hbc.pixels[1] = (0, 255, 0)
      hbc.pixels[2] = (0, 0, 255)
   