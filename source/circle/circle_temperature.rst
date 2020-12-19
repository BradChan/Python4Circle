===========================
温度传感器
===========================

HiiBot Circle集成温度传感器，具备温度检测功能。当需要获取当前温度时，使用hbc.temperature的值即可。获取的温度单位是摄氏温标（°C）。


.. code-block:: python

   import time
   from hiibot_circle import hbc

   while True:
      print("Temperature C:", hbc.temperature)
      print("Temperature F:", hbc.temperature * 1.8 + 32)
      time.sleep(1)


.. note:: 摄氏温度和华氏温度的关系：T℉=1.8t℃+32（t为摄氏温度数，T为华氏温度数）