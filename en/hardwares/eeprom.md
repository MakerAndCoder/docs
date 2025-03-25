# EEPROM

## Example

Write a variable to EEPROM and display it on the screen.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/eeprom/uiflow_block_eeprom_demo.svg"> 

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import nvs

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

label0 = MCLabel('label0', x=130, y=81, color=0x000, font=FONT_MONT_14, parent=None)

nvs.write(str('q'), '1')
while True:
  label0.set_text(str(nvs.read_str('q')))
  wait_ms(2)
```

## API
- Initialize EEPROM, set a variable, and assign a value.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/eeprom/uiflow_block_eeprom_write_str.svg"> 

```python
nvs.write(str(''), '')
```

<be><br>
- Read a variable from EEPROM.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/eeprom/uiflow_block_eeprom_read_str.svg"> 

```python
str(nvs.read_str('q'))
```

<be><br>
- Convert the variable from EEPROM to an integer and output it
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/eeprom/uiflow_block_eeprom_read_int.svg"> 

```python
str(nvs.read_int('q'))
```

.
