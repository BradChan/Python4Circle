====================
控制红色LED的API
====================

1) 红色LED工作模式的属性：redLED_mode；有效值为0或1分别代表开关模式或PWM模式，其中开关模式仅以最大亮度on或off，PWM模式可设置LED亮度；
默认的工作模式是开关模式。用法如下：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc
  hbc.redLED_mode = 0  # 开关模式

  while True:
      hbc.redLED = 1
      time.sleep(0.5)
      hbc.redLED = 0
      time.sleep(0.5)


2) 红色LED的值属性：redLED；开关模式时，有效值为0或1；PWM模式时，有效值为0~65535。用法如下：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc
  hbc.redLED_mode = 1  # PWM模式

  while True:
      hbc.redLED = 5000 # 亮度范围：0~65535, 现在仅10%亮度
      time.sleep(0.5)
      hbc.redLED = 0
      time.sleep(0.5)

3) 切换红色LED的亮灭状态：redLED_toggle()；开关模式时，仅以最大亮度切换亮灭；PWM模式时，以当前亮度切换亮灭。用法如下：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc
  hbc.redLED_mode = 1  # PWM模式
  hbc.redLED = 5000    # 亮度范围：0~65535, 现在仅10%亮度

  while True:
      hbc.redLED_toggle() # 切换亮灭
      time.sleep(0.5)


