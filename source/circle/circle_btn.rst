===========================
按钮
===========================

HiiBot Circle具有2个按钮：按钮A和按钮B，分别对应button_a和button_b。

当按钮A被按下时，则hbc.button_a为True，否则为False。按钮B同理。


.. code-block:: python
   :linenos:

   from hiibot_circle import hbc

   while True:
      if hbc.button_a:
         print("Button A pressed!")
         hbc.red_led = True
      if hbc.button_b:
         print("Button B pressed!")
         hbc.red_led = False

示例在while循环中，检测按钮A是否按下，如果按下了打印输出并控制红灯(red_led)亮；
检测按钮B是否按下，如果按下了打印输出并控制红灯灭。