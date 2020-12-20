====================
按钮输入的API
====================

1) 更新编程圆的两个按钮的状态：buttonUpdate()；必须在主循环程序内调用该接口才能有效地更新按钮的状态。用法如下：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc

  while True:
      hbc.buttonUpdate()  # 更新两个按钮的状态
      time.sleep(0.1)

2) 获取按钮A的当前状态：buttonA；有效值为True或False，当A按钮被按下时为True，未按下时为False。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc

  while True:
      hbc.buttonUpdate()  # 更新两个按钮的状态
      if hbc.buttonA:     # 判断A按钮是否被按下
          hbc.redLED = 1  # 让红色LED亮
      else :
          hbc.redLED = 0  # 让红色LED灭

3) 检查A按钮是否已被按下：buttonA_wasPressed；有效值为True或False，如果A按钮已被按下则为True，否则为False。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc

  while True:
      hbc.buttonUpdate()  # 更新两个按钮的状态
      if hbc.buttonA_wasPressed: # 判断A按钮是否已按下
          hbc.redLED_toggle()    # 切换红色LED亮灭

4) 检查A按钮是否已被释放：buttonA_wasReleased；有效值为True或False，如果A按钮已被释放则为True，否则为False。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc

  while True:
      hbc.buttonUpdate()  # 更新两个按钮的状态
      if hbc.buttonA_wasPressed:  # 判断A按钮是否已按下
          print("pressed")
      if hbc.buttonA_wasReleased: # 判断A按钮是否已释放
          print("released")

执行上面示例程序时，请打开串口控制台，按下和释放A按钮时分别会在控制台输出“pressed”和“released”信息。

5) 检查A按钮是否被长按且超过指定的时长：buttonA_pressedFor( t_s )；输入参数“t_s”是以秒为单位的长按时长阈值；当长按时间超过设定时长后，
该接口将返回True，且仅返回一次。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc

  while True:
      hbc.buttonUpdate()  # 更新两个按钮的状态
      if hbc.buttonA_wasPressed:  # 判断A按钮是否已按下
          print("pressed")
      if hbc.buttonA_wasReleased: # 判断A按钮是否已释放
          print("released")
      if hbc.buttonA_pressedFor(2.0): # 判断A按钮是否长按并超过2.0秒
          print("longly pressed")

6) 获取按钮B的当前状态：buttonB；有效值为True或False，当B按钮被按下时为True，未按下时为False。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc

  while True:
      hbc.buttonUpdate()  # 更新两个按钮的状态
      if hbc.buttonB:     # 判断B按钮是否被按下
          hbc.redLED = 1  # 让红色LED亮
      else :
          hbc.redLED = 0  # 让红色LED灭

7) 检查B按钮是否已被按下：buttonB_wasPressed；有效值为True或False，如果B按钮已被按下则为True，否则为False。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc

  while True:
      hbc.buttonUpdate()  # 更新两个按钮的状态
      if hbc.buttonB_wasPressed: # 判断B按钮是否已按下
          hbc.redLED_toggle()    # 切换红色LED亮灭

8) 检查B按钮是否已被释放：buttonB_wasReleased；有效值为True或False，如果B按钮已被释放则为True，否则为False。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc

  while True:
      hbc.buttonUpdate()  # 更新两个按钮的状态
      if hbc.buttonB_wasPressed:  # 判断B按钮是否已按下
          print("pressed")
      if hbc.buttonB_wasReleased: # 判断B按钮是否已释放
          print("released")

执行上面示例程序时，请打开串口控制台，按下和释放B按钮时分别会在控制台输出“pressed”和“released”信息。

9) 检查B按钮是否被长按且超过指定的时长：buttonB_pressedFor( t_s )；输入参数“t_s”是以秒为单位的长按时长阈值；当长按时间超过设定时长后，
该接口将返回True，且仅返回一次。用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc

  while True:
      hbc.buttonUpdate()  # 更新两个按钮的状态
      if hbc.buttonB_wasPressed:  # 判断B按钮是否已按下
          print("pressed")
      if hbc.buttonB_wasReleased: # 判断B按钮是否已释放
          print("released")
      if hbc.buttonB_pressedFor(2.0): # 判断B按钮是否长按并超过2.0秒
          print("longly pressed")




