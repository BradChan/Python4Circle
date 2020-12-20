====================
产生声音的API
====================

1) 允许或禁止喇叭输出(音频放大器的使能控制)：enableSpeaker( enable )；输入参数“enable”为True时允许音频输出，否则禁止输出。用法如下：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc
  hbc.enableSpeaker( True )   # 允许音频输出
  hbc.enableSpeaker( False )  # 禁止音频输出

2) 开始(在后台)输出指定频率的音调：startTone( frequency )；输出参数“frequency”是以Hz为单位的频率；在后台输出音调指的是，
该接口是非阻塞式的，启动频率信号输出后立即返回，直到调用“stopTone()”接口时才停止输出。用法如下：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc
  hbc.enableSpeaker( True )   # 允许音频输出
  hbc.startTone( 262 )  # 开始产生262Hz的频率信号
  time.sleep(2)
  hbc.stopTone() # 停止输出
  hbc.enableSpeaker( False )  # 禁止音频输出

3) 停止(在后台)输出频率信号：stopTone()。用法见上例。

4) 播放指定频率和时长的音调：playTone( frequency, duration )；输出参数“frequency”是以Hz为单位的频率，参数“duration”是以秒为单位的时长；
该接口是阻塞式的，执行该接口需要耗费时长由参数“duration”确定。用法如下：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc
  pitchs = [523, 587, 659, 698, 784, 880, 988]
  for f in pitchs:
      hbc.playTone( f, 0.5)
      time.sleep(0.25)

5) 播放指定MIDI号的音节和节拍：playMIDI( midi, beats, spacetl )；参数“midi”为MIDI号，有效值为0或24~111，0:表示静音；
参数“beats”表示节拍数，有效值为1~64；参数“spacetl”指定播放后静音的时长，单位是秒。注意，该接口是阻塞式的，执行该接口耗费的时长为“60/bpmMIDI/beats”秒。
用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc
  midiN = [72, 74, 76, 77, 79, 81, 83]
  for midi in midiN:
      hbc.playMIDI( midi, 4, 0.25)

6) 播放MIDI音节的速度bpm(每分钟的拍数)属性：bpmMIDI；有效值为30～360，默认值为120，即每分钟120拍。用法如下：

.. code-block::  python
  :linenos:

  import time
  from  hiibot_circle  import  hbc
  midiN = [72, 74, 76, 77, 79, 81, 83]
  bpm = [30, 60, 120, 240, 360]
  
  for b in bpm:
      hbc.bpmMIDI = b     # 改变bpm参数
      for midi in midiN:
          hbc.playMIDI( midi, 4, 0.25)
      time.sleep(1.0)

7) 播放指定(路径和名称)的Wav文件：playWaveFile( waveFile )；参数“waveFile”是带有绝对路径的wave格式文件，采用字符串形式指定文件路径和名称。
用法如下：

.. code-block::  python
  :linenos:

  from  hiibot_circle  import  hbc
  waeFile = "/sound/Coin.wav"
  hbc.playWaveFile( waeFile )
  hbc.playWaveFile( "/sound/Boing.wav" )
