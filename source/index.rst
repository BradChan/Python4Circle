.. Python for Circle documentation master file, created by
   sphinx-quickstart on Mon Oct 21 14:39:53 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

HiiBot Circle帮助文档
=============================================

HiiBot Circle(编程圆)是一种mini型可编程计算机系统，支持MakeCode和Scratch图形化编程语言、Python脚本编程语言、
C/C++编译型编程语言等；编程圆具有丰富的拟人化的传感器输入，包括温度、人体触摸、按钮等触觉感知输入，环境光亮度和颜色等视觉感知输入，
数字麦克风等听觉感知输入，以及运动姿态感知等；10颗环形分布的可编程彩色LED(颜色多达16,777,216种)


准备工作
-----------------------------------------------

.. toctree::
   :maxdepth: 1
   
   intro/circle_intro.rst
   intro/install_mu.rst
   intro/install_circuitPython.rst
   intro/the_circuitpy_drive.rst
   intro/create_editing_code.rst
   intro/interacting_with_the_serial_console.rst
   intro/the_repl.rst

使用功能模块
-----------------------------------------------

.. toctree::
   :maxdepth: 1

   circle/circle_intro.rst
   circle/circle_red_led.rst
   circle/circle_btn.rst
   circle/circle_touch.rst
   circle/circle_pixels.rst
   circle/circle_temperature.rst
   circle/circle_acceleration.rst
   circle/circle_speak.rst
   circle/circle_shake.rst

Python API
-----------------------------------------------

.. toctree::
   :maxdepth: 1

    python_api/api.rst
