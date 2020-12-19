============================
红灯
============================

HiiBot Circle具有一颗可控制的红灯：red_led。当对red_led赋值True时，红灯变常亮状态，否则为常灭状态。

示例1：亮灯

.. code-block:: python

   from hiibot_circle import hbc

   while True:
      hbc.red_led = True


示例2：闪灯，可通过修改间隔时间0.5来控制闪灯间隔。

.. code-block:: python

   import time
   from hiibot_circle import hbc

   while True:
      hbc.red_led = True
      time.sleep(0.5)
      hbc.red_led = False
      time.sleep(0.5)

.. note:: 示例2使用了time.sleep(0.5)延时，需要引入time模块。