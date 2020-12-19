===========================
数字麦克风
===========================

HiiBot Circle集成数字麦克风，可以播放音调和wav文件。

播放音调
------------------------

通过函数play_tone(frequency, duration)播放音调。该具有2个参数，第一个参数frequency是音调的频率，第二个参数duration是播放时长，单位秒。

示例1：通过检测按钮A和按钮B的点击状态，分别播放不同的音调。

.. code-block:: python

   from hiibot_circle import hbc
   
   while True:
      if hbc.button_a:
         hbc.play_tone(262, 1)
      if hbc.button_b:
         hbc.play_tone(294, 1)



播放WAV文件
------------------------

通过函数play_file(file_name)播放磁盘上的wav文件。该函数具有1个参数，file_name对应磁盘上待播放的wav文件名。


示例2：检测按钮A和按钮B的点击状态，分别播放不同的wav文件。

.. code-block:: python

   from hiibot_circle import hbc

   while True:
      if hbc.button_a:
         hbc.play_file("dip.wav")
      if hbc.button_b:
         hbc.play_file("rise.wav")


.. _dip.wav下载: http://www.hibottoy.com:8080/static/files/circle/wavs/dip.wav

.. _rise.wav下载: http://www.hibottoy.com:8080/static/files/circle/wavs/rise.wav

.. note:: `dip.wav下载`_ 和 `rise.wav下载`_