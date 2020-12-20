====================
传感器输入的API
====================

1) 获取环境温度：temperature；有效值范围为-40～+125摄氏度。用法如下：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc

  while True:
      nowT = hbc.temperature
      print( "temperatue: {} °C".format(nowT) )
      time.sleep(1.0)

----------------------------

2) 获取环境亮度：lightness；有效值范围为0~255。用法如下：

.. code-block::  python
  :linenos:

import time
from  hiibot_circle  import  hbc

while True:
    nowL = hbc.lightness
    print( "lightness: {} ".format(nowL) )
    time.sleep(0.5)

----------------------------

3) 获取环境颜色：ambientColor；属性值采用turple格式，即(R, G, B)三个分量组成的元组。用法如下：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc

  while True:
      colorName = hbc.ambientColor
      print("ambient color value : {} ".format(colorName) )
      time.sleep(0.5)

4) 获取环境颜色编号：ambientColorID；有效值为0~6，分别代表环境颜色White、Red、Yellow、Green、Cyan、Blue、Purple等；
根据该属性值和“ambientColor_name”列表可以获取环境颜色的名称。用法如下：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc

  while True:
      id = hbc.ambientColorID
      print("ambient color: {}/{} ".format(hbc.ambientColor_list[id], hbc.ambientColor_name[id]) )
      time.sleep(0.5)

----------------------------

5) 获取当前加速度值：acceleration；三个方向的加速度分量，即accX, accY, accZ。用法如下：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc

  while True:
      x, y, z = hbc.acceleration
      print("acceleration X:{} Y:{} Z:{} ".format(x, y, z) )
      time.sleep(0.5)

6) 获取当前的倾角：tiltAngle；两个方向的倾角，即Pitch(俯仰角)、Roll(翻滚角。用法如下：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc

  while True:
      pitch, roll = hbc.tiltAngle
      print("tiltAngle  Pitch:{} Roll:{} ".format(pitch, roll) )
      time.sleep(0.5)

7) 检测是否被摇晃：shake；有效值为True或False，如果被摇晃则为True，否则为False。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc
  while True:
      if hbc.shake(shake_threshold=20):
          print('shaked')

8) 敲击侦测的属性：detectTaps；有效值为1或2，如果侦测单击则为1，双击为2。

9) 检测是否被敲击：tapped；有效值为True或False，如果被敲击(单击或双击，依据“敲击侦测的属性”)为True，否则为False。用法如下：

单击侦测的示例：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc
  hbc.detectTaps = 1
  while True:
      if hbc.tapped:
          print('single tapped')

侦测双击的示例：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc
  hbc.detectTaps = 2
  while True:
      if hbc.tapped:
          print('double tapped')

----------------------------

10) 获取环境声音的大小：soundLevel；有效值为0～65535，采样时间约2ms，采样点32个，采样分辨率为16位，然后取采样点的数学期望作为环境声音的大小。
用法如下：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc

  while True:
      sl = hbc.soundLevel
      print(sl)
      time.sleep(0.5)

11) 检测是否听到很大的声音(大于设定的阈值)：loudSound( sound_threshold )；输入参数“sound_threshold”是阈值，当soundLevel大于此阈值时，
返回值为True，否则为False。用法如下：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc

  while True:
      if hbc.loudSound( sound_threshold = 800 ):
          print('loud sound')

12) 按指定的采样点数采样当前环境声音：soundSample( numSamples )；输入参数“numSamples”为指定的采样点数，建议使用16的倍数，
返回值为所有采样数据的列表。用法如下：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc

  while True:
      sl =  [ val for val in hbc.soundSample( numSamples = 32 )] # generate a list from sample data
      print( sl )
      time.sleep(0.5)
