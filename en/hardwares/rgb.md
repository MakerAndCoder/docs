# RGB

##  Example

Driving RGB light strip flashing

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/rgb/uiflow_block_RGB_demo.svg"> 


```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

R = None
G = None
B = None
i = None

import random

while True:
  R = random.randint(0, 255)
  G = random.randint(0, 255)
  B = random.randint(0, 255)
  for i in range(0, 256, 10):
    rgb.setColorFrom(6, 10, (R << 16) | (G << 8) | B)
    rgb.setColorFrom(1, 5, (G << 16) | (R << 8) | B)
    rgb.setBrightness(i)
  for i in range(255, -1, -10):
    rgb.setColorFrom(6, 10, (R << 16) | (G << 8) | B)
    rgb.setColorFrom(1, 5, (G << 16) | (R << 8) | B)
    rgb.setBrightness(i)
  wait_ms(2)
```

## API
- Setting the color of all lights
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/rgb/uiflow_block_rgb_bar_color.svg"> 

```python
rgb.setColorAll(0xff0000)
```

<br><br>
  
- Setting the color RGB value of all lamp beads
  - (R:0-255  G:0-255 B:0-255)
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/rgb/uiflow_block_rgb_bar_color_value.svg"> 

```python
rgb.setColorAll(0x000000)
```
<br><br> 

- Setting the color data type
  - `Palette`: Directly select the color panel to switch the strip color
  - `RGB`: Input the RGB value to switch the strip color
  - `HEX`: Input color-converted hexadecimal values for switching lamp bead colors.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/rgb/uiflow_block_rgb_bar_color_option.svg"> 

```python
rgb.setColorAll(0x000000)
```
<br><br>
- numerical value
  - "6":Sixth lamp bead
  - "10":The tenth lamp bead
  - "0xff0000":RGB

#>Description|The right bead is the first to the fifth bead, the left represents the sixth to the tenth bead.


<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/rgb/uiflow_block_rgb_bar_side_color.svg"> 

```python
rgb.setColorFrom(6, 10, 0xff0000)
```
<br><br>

- Select lamp beads on different sides and switch colors by RGB values
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/rgb/uiflow_block_rgb_bar_side_color_value.svg"> 

```python
rgb.setColorFrom(6, 10, 0xff0000)
```

<br><br>

- Setting the color data type
  - `Palette`: Directly select the color panel to switch the strip color
  - `RGB`: Input the RGB value to switch the strip color
  - `HEX`: Input color-converted hexadecimal values for switching lamp bead colors.


#>Instructions|Select different sides of the light strip and switch the adjustment mode to switch the color
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/rgb/uiflow_block_rgb_bar_side_color_option.svg"> 

```python
rgb.setColorFrom(6, 10, 0xff0000)
```
<br><br>

- numerical value
  - "1":Setting up individual specific lamp beads for color switching (1-10)
  - "0xff0000": Color values
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/rgb/uiflow_block_rgb_bar_index_color.svg"> 

```python
rgb.setColor(1, 0xff0000)
```

<br><br>

- Setting the color RGB value of a specific lamp bead
  - (R:0-255  G:0-255 B:0-255)

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/rgb/uiflow_block_rgb_bar_index_color_value.svg"> 

```python
rgb.setColor(1, 0xff0000)
```
<br><br>

- Setting the single bead color data type
  - `Palette`: Directly select the color panel to switch the strip color
  - `RGB`: Input the RGB value to switch the strip color
  - `HEX`: Input color-converted hexadecimal values to switch lamp bead colors.

#>Description|Select a single lamp bead and switch the adjustment mode to switch the color.

<div class="tip"><div class="tip-title">Description</div> <div class="tip-content">Select a single lamp bead and switch the adjustment mode to switch the color.</div></div>
<br>
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/rgb/uiflow_block_rgb_bar_side_color_option.svg"> 

```python
rgb.setColor(1, 0xff0000)
```
<br><br>

- Set lamp bead brightness (0-255)
  - The larger the value, the brighter the lamp bead
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/rgb/uiflow_block_rgb_bar_brightness.svg"> 

```python
rgb.setBrightness(10)
```


