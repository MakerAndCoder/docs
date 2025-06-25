# Microphone

Use the Microphone to listen

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/adc/uiflow_block_microphone_init.svg"> 

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import MicrophonePDM as MIC

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

MIC.begin(pin_ws=0, pin_data=34, sample_rate_hz=16000, buffer_length_ms=1000, block_length_ms=100)
```
