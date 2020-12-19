============================
触摸盘
============================

HiiBot Circle具有7个触摸盘：A1、A2、A3、A4、A5、A6和A7。当触摸盘A1被触摸时，对应hbc.touch_A1的值
就会变成True，否则为False。


示例1：A1-A7触摸屏触碰时，分别打印输出信息。

.. code-block:: python

   from hiibot_circle import hbc
   
   while True:
      if hbc.touch_A1:
         print('Touched pad A1')
      if hbc.touch_A2:
         print('Touched pad A2')
      if hbc.touch_A3:
         print('Touched pad A3')
      if hbc.touch_A4:
         print('Touched pad A4')
      if hbc.touch_A5:
         print('Touched pad A5')
      if hbc.touch_A6:
         print('Touched pad A6')
      if hbc.touch_A7:
         print('Touched pad A7')

