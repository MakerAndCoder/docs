# Speaker

#>Speaker Frequency Setting:| Since the hearing range of the average person in the 20~20KHz, so when you set the frequency is too low, or too high, it is not heard!

## Speaker For MC4.0

### Example

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/speaker/uiflow_block_speaker_example.svg"> 


```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)


speaker.setVolume(90)
speaker.sing(220, 1)
speaker.tone(1800, 200)
```

### API
- Setting the playback sound frequency and duration
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/speaker/uiflow_block_speaker.svg"> 

```python
speaker.tone(1800, 200)
```



<br><br>
- Setting the Playback Volume
  - Volume range: 0-100
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/speaker/uiflow_block_speaker_volume.svg"> 

```python
speaker.setVolume(1)
```



<br><br>
- Play the specified tone and beat

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/speaker/uiflow_block_speaker_tone.svg"> 

```python
speaker.sing(220, 1)
```



## Speaker For MC4.0

### Example

- Control playtone

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/speaker/uiflow_block_core2_speaker_play_tone_example.svg"> 

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

speaker.playTone(554, 1, volume=6)
speaker.playTone(554, 1, volume=6)
```

<br><br>
- Control playback of local wav files

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/speaker/uiflow_block_core2_speaker_play_local_wav_example.svg"> 

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

speaker.playWAV("res/ding.wav", volume=6)
wait(1)
speaker.playWAV('res/ding.wav', rate=44100, data_format=speaker.F16B, channel=speaker.CHN_LR, volume=6)
```


### API

- Play the specified tone (frequency) and set the playback volume.
  - Volume range: 0-6
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/speaker/uiflow_block_core2_speaker_play_freq.svg"> 

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/speaker/uiflow_block_core2_speaker_play_tone.svg"> 


```python
speaker.playTone(554, 1, volume=6)
```


<br><br>
- Play wav files in the local file system, and set the playback volume.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/speaker/uiflow_block_core2_speaker_play_wav_file.svg"> 

```python
speaker.playWAV("res/ding.wav", volume=6)
```


<br><br>
- Play the wav file in the local file system `res/filename.wav` or SD card `/sd/filename.wav`, and specify the sample rate and audio data format and channel at the same time.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/speaker/uiflow_block_core2_speaker_play_local_wav_file_path.svg"> 

```python
speaker.playWAV('res/ding.wav', rate=44100, data_format=speaker.F16B, channel=speaker.CHN_LR, volume=6)
```


<br><br>
- Provide an interface to upload wav files to the device in online programming mode, click the + sign to upload operation.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/speaker/uiflow_block_core2_speaker_play_upload_wav_file.svg"> 

```python
speaker.playWAV("res/ding.wav", volume=0)
```




<br><br>
- Fill in the URL to play the wav file in the cloud

#>Note: | Only WAV type files are supported with a maximum size of 500KB, to prevent the file from being too large, it is recommended to use 16000 sampling frequency, 16 Bit WAV files.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/speaker/uiflow_block_core2_speaker_play_url_wav_file.svg"> 

```python
speaker.playCloudWAV('https://xxxxx.wav', volume=6)
```




