=====================
控制彩色灯珠的API
=====================

1) 编程圆彩色灯珠的亮度属性: hbc.pixels.brightness；有效值范围：0.0~1.0。用法示例如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc
  hbc.pixels.brightness = 0.1  # 将所有灯珠的亮度设置为10%

.. Attention:: 

  A. 设置彩色灯珠的新属性之后，只能在调用hbc.pixels.show()接口之后才会生效
  B. 亮度属性是所有灯珠的亮度，编程圆不支持单颗或部分灯珠亮度的调节
  C. 当灯珠亮度较高时，切勿裸眼直视灯珠！



2) 某颗彩色灯珠的颜色属性：hbc.pixels[index]；有效值为turple型，即(R, G, B)型，其中每个颜色分量的范围是0~255。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc
  hbc.pixels.brightness = 0.1  # 将所有灯珠的亮度设置为10%

  hbc.pixels[0] = (255, 0, 0)  # 设置第0颗灯珠的颜色为红色
  hbc.pixels.show()            # 刷新灯珠的颜色

显示环形彩色图案，示例程序如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc
  import time
  hbc.pixels.brightness = 0.1  # 将所有灯珠的亮度设置为10%

  colors = [(255,0,0), (128,128,0), (128,255,0), (0,255,0), (0,128,128), 
            (0,128,255), (0,0,255), (128,0,128), (255,0,128),(255,0,64)]

  i=0
  for c in colors:
      hbc.pixels[i] = c   # 
      i += 1
  hbc.pixels.show()       # 刷新灯珠的颜色

  while True:
      time.sleep(1)

3) 让所有彩色灯珠显示(即填充)指定的颜色：hbc.fillPixels( (R,G,B) )。用法示例：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc
  import time
  hbc.pixels.brightness = 0.1  # 将所有灯珠的亮度设置为10%

  while True:
      hbc.fillPixels( (255,0,0) )
      time.sleep(0.5)
      hbc.fillPixels( (0,255,0) )
      time.sleep(0.5)
      hbc.fillPixels( (0,0,255) )
      time.sleep(0.5)

4) 绘制彩虹图案：drawRainbow(c)；输入参数“c”是起始的色调值，有效值为0～255。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc
  import time
  hbc.pixels.brightness = 0.1  # 将所有灯珠的亮度设置为20%
  hbc.drawRainbow( 100 )

  while True:
      time.sleep(2)

5) 显示指定的彩色图案：drawPattern( listColor )；输入参数“listColor”是一个颜色列表，该列表顺序地指定每一颗灯珠的颜色。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc
  import time
  hbc.pixels.brightness = 0.1  # 将所有灯珠的亮度设置为10%

  colors = [(255,0,0), (128,128,0), (128,255,0), (0,255,0), (0,128,128), 
            (0,128,255), (0,0,255), (128,0,128), (255,0,128),(255,0,64)]

  hbc.drawPattern( colors )

  while True:
      time.sleep(1)

6) 将当前显示的彩色图案向左/逆时针旋转一步：shiftLeft()。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc
  import time
  hbc.pixels.brightness = 0.1  # 将所有灯珠的亮度设置为10%
  hbc.drawRainbow( 0 )  # 绘制彩虹图案

  while True:
      hbc.shiftLeft()
      time.sleep(0.2)

7) 将当前显示的彩色图案向右/顺时针旋转一步：shiftRight()。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc
  import time
  hbc.pixels.brightness = 0.1  # 将所有灯珠的亮度设置为10%

  colors = [(255,0,0), (128,128,0), (128,255,0), (0,255,0), (0,128,128), 
          (0,128,255), (0,0,255), (128,0,128), (255,0,128),(255,0,64)]

  hbc.drawPattern( colors )

  while True:
      hbc.shiftRight()
      time.sleep(0.2)

8) 使用指定的变量绘制单色柱状图：drawMonoPillar( var, minV, maxV, onColor )；输入参数包括变量“var”，变量最小值“minV”，
变量最大值“maxV”和柱状图颜色“onColor”，其中柱状图颜色是turple型，即(R, G, B)。用法如下：

使用编程圆的光传感器感知到的环境亮度“lightness”绘制单色柱状图：

.. code-block::  python
  :linenos:

  from hiibot_circle import hbc
  import time

  hbc.pixels.brightness = 0.1

  minLevel = hbc.lightness  # the ambient lightness
  maxLevel = 255  # peak of lightness level

  while True:
      time.sleep(0.05)
      lightness = hbc.lightness  # get
      hbc.drawMonoPillar(lightness, minLevel, maxLevel, (0, 255, 255))

9) 使用指定的变量绘制彩色柱状图：drawColorPillar( var, minV, maxV, peakColor )；输入参数包括变量“var”，变量最小值“minV”，
变量最大值“maxV”和柱状图峰值颜色“peakColor”，其中柱状图峰值颜色是turple型，即(R, G, B)。用法如下：

使用编程圆的数字麦克风感知到的声音信号高低“soundLevel”绘制彩色柱状图：

.. code-block::  python
  :linenos:

  from hiibot_circle import hbc
  import time

  hbc.pixels.brightness = 0.1
  minLevel = hbc.soundLevel+10 # the ambient noise
  maxLevel = minLevel + 1000   # peak of sound level

  while True:
      time.sleep(0.05)
      soundLevel = hbc.soundLevel # get
      hbc.drawColorPillar( soundLevel,  minLevel, maxLevel, (100,0,200))

10) 显示“星星闪烁”的动画效果并持续指定的时间：showAnimation_star( ts )；输入参数“ts”是以秒为单位的持续时间。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc
  hbc.pixels.brightness = 0.1  # 将所有灯珠的亮度设置为20%

  while True:
      hbc.showAnimation_star(2)

11) 显示“旋转彩虹”的动画效果并持续指定的时间：showAnimation_rainbow( ts )；输入参数“ts”是以秒为单位的持续时间。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc
  hbc.pixels.brightness = 0.1  # 将所有灯珠的亮度设置为20%

  while True:
      hbc.showAnimation_rainbow(2)

12) 显示“彗星”的动画效果并持续指定的时间：showAnimation_comet( step_time, ts, dir )；输入参数“step_time”是以秒为单位的每步时长，
参数“ts”是以秒为单位的持续时间，参数“dir”为旋转方向，默认是True即顺时针旋转，否则逆时针旋转。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc
  hbc.pixels.brightness = 0.1  # 将所有灯珠的亮度设置为20%

  while True:
      hbc.showAnimation_comet(0.1, 2.0) # 默认顺时针旋转
      #hbc.showAnimation_comet(0.1, 2.0, False) # 逆时针旋转

13) 显示“刮擦”的动画效果并持续指定时间：showAnimation_wipe( step_time, ts, oncolor )；输入参数“step_time”是以秒为单位的每步时长，
参数“ts”是以秒为单位的持续时间(不少于step_time的20倍)，参数“oncolor”为颜色，即turple型，即(R, G, B)。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc
  hbc.pixels.brightness = 0.1  # 将所有灯珠的亮度设置为20%

  while True:
      hbc.showAnimation_wipe( 0.2, 4.0, (255,0,0) )


