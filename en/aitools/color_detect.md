# Color detection

## Example
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/aitools/colordetect/ex.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
from MCLab.ai_tools import *


screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)


unitv_base = UnitVBase()
color_detect = ColorDetect(unitv_base)


color_detect.init()
while True:
  if (color_detect.get_discover_color()) == 'red':
    rgb.setColorAll(0xff0000)
    screen.set_screen_bg_color(0xff0000)
  elif (color_detect.get_discover_color()) == 'green':
    rgb.setColorAll(0x33cc00)
    screen.set_screen_bg_color(0x33cc00)
  elif (color_detect.get_discover_color()) == 'blue':
    rgb.setColorAll(0x00cccc)
    screen.set_screen_bg_color(0x00cccc)
  else:
    rgb.setColorAll(0x000000)
    screen.set_screen_bg_color(0xcccccc)
  wait_ms(2)
```

## API

- Initialize the color detection module

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/aitools/colordetect/1.svg">

```python
color_detect.init()
```

- Sends the color name (or "No color detected") over UART based on the following thresholds:

Red: (12, 71, 30, 70, 2, 50)

Green: (0, 100, -128, -20, 20, 127)

Blue: (0, 100, -128, 0, -128, -20)

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/aitools/colordetect/2.svg">

```python
color_detect.get_discover_color()
```

